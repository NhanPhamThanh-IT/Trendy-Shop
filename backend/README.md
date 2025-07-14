# Trendy Shop - Backend API

A comprehensive Node.js REST API backend for the Trendy Shop e-commerce platform, built with Express.js and MongoDB. This backend supports a multi-role system with Admin, Retailer, and Customer functionalities.

## 🚀 Features

### Authentication & Authorization

- JWT-based authentication system
- Role-based access control (Admin, Retailer, Customer)
- Secure password hashing with bcrypt
- Token-based middleware for protected routes

### Core Functionalities

- **User Management**: Registration, login, profile management
- **Product Management**: CRUD operations for products with categories
- **Order Management**: Complete order lifecycle management
- **Voucher System**: Create and apply discount vouchers
- **Feedback System**: Customer reviews and ratings
- **Dashboard Analytics**: Real-time data for admins and retailers

### Multi-Role Support

- **Admin**: System-wide management, retailer oversight, analytics
- **Retailer**: Product and inventory management, order fulfillment
- **Customer**: Shopping, order tracking, reviews

## 🛠️ Technology Stack

- **Runtime**: Node.js
- **Framework**: Express.js
- **Database**: MongoDB with Mongoose ODM
- **Authentication**: JSON Web Tokens (JWT)
- **Security**: bcrypt for password hashing
- **Development**: Nodemon for auto-reloading

## 📋 Prerequisites

- Node.js (v14 or higher)
- MongoDB database (local or cloud)
- npm or yarn package manager

## 🔧 Installation

1. **Clone the repository**

   ```bash
   git clone https://github.com/NhanPhamThanh-IT/Trendy-Shop.git
   cd Trendy-Shop/backend
   ```

2. **Install dependencies**

   ```bash
   npm install
   ```

3. **Configure database**

   - Update the MongoDB connection string in `config/db.config.js`
   - Ensure your MongoDB instance is running

4. **Start the server**

   ```bash
   npm start
   ```

   The server will start on `http://localhost:8080`

## 📁 Project Structure

```
backend/
├── config/
│   └── db.config.js          # Database configuration
├── controllers/              # Business logic controllers
│   ├── CategoryController/
│   │   └── category.js       # Category management
│   ├── FeedbackController/
│   │   └── feedbackController.js # Reviews and ratings
│   ├── OrderController/
│   │   └── order.controller.js   # Order processing
│   ├── ProductController/
│   │   └── product.js        # Product CRUD operations
│   ├── UserController/
│   │   └── user.controller.js    # User management & auth
│   └── VoucherController/
│       └── voucher.Controller.js # Discount vouchers
├── models/                   # Database schemas
│   ├── categoryModel.js      # Product categories
│   ├── feedbackModel.js      # Customer feedback
│   ├── orderModel.js         # Order structure
│   ├── productModel.js       # Product details
│   ├── userModel.js          # User profiles
│   ├── voucherModel.js       # Discount vouchers
│   └── index.js              # Model exports
├── routes/                   # API route definitions
│   ├── customerRoutes.js     # Customer-specific routes
│   ├── retailerRoutes.js     # Retailer-specific routes
│   ├── userRoutes.js         # Authentication routes
│   └── routes.js             # Main route configuration
├── middleware.js             # JWT authentication middleware
├── server.js                 # Application entry point
└── package.json              # Dependencies and scripts
```

## 🔗 API Endpoints

### Authentication

- `POST /api/auth/signup` - User registration
- `POST /api/auth/login` - User login
- `GET /api/user/profile` - Get user profile (protected)
- `PUT /api/user/profile` - Update user profile (protected)

### Products

- `GET /api/customer/products` - Get all products
- `GET /api/customer/product/:id` - Get product details
- `POST /api/retailer/products` - Create new product (retailer only)
- `PUT /api/retailer/products/:id` - Update product (retailer only)
- `DELETE /api/retailer/products/:id` - Delete product (retailer only)

### Orders

- `POST /api/customer/orders` - Create new order
- `GET /api/customer/orders` - Get user orders
- `GET /api/retailer/orders` - Get retailer orders
- `PUT /api/retailer/orders/:id` - Update order status

### Categories

- `GET /api/customer/categories` - Get all categories
- `POST /api/admin/categories` - Create category (admin only)
- `PUT /api/admin/categories/:id` - Update category (admin only)

### Vouchers

- `GET /api/customer/vouchers` - Get available vouchers
- `POST /api/retailer/vouchers` - Create voucher (retailer only)
- `POST /api/customer/apply-voucher` - Apply voucher to order

### Feedback

- `POST /api/customer/feedback` - Submit product review
- `GET /api/customer/feedback/:productId` - Get product reviews

### Admin Dashboard

- `GET /api/admin/dashboard` - Get admin analytics
- `GET /api/admin/retailers` - Manage retailers
- `PUT /api/admin/retailers/:id` - Update retailer status

## 🔐 Authentication

The API uses JWT (JSON Web Tokens) for authentication. Include the token in the Authorization header:

```
Authorization: Bearer <your-jwt-token>
```

### Middleware Protection

Protected routes require a valid JWT token. The `middleware.js` file handles token validation and user authorization.

## 👥 User Roles

### Customer

- Browse and search products
- Add products to cart and place orders
- Leave reviews and ratings
- Track order status
- Apply vouchers and discounts

### Retailer

- Manage product inventory
- Create and update products
- Process customer orders
- Create discount vouchers
- View sales analytics

### Admin

- Oversee entire platform
- Manage retailer accounts
- View system-wide analytics
- Manage product categories
- Monitor platform activity

## 🗄️ Database Models

### User Model

```javascript
{
  name: String,
  email: String (unique),
  password: String (hashed),
  role: ["admin", "customer", "retailer"],
  birthday: String,
  gender: String,
  avatar: String,
  region: String,
  order_list: [ObjectId] // References to orders
}
```

### Product Model

```javascript
{
  name: String,
  description: String,
  price: Number,
  user_id: ObjectId, // Retailer who owns the product
  category_id: ObjectId,
  size: String,
  stock_quantity: Number,
  rating: Number (0-5),
  image_url: String
}
```

### Order Model

```javascript
{
  customer_id: ObjectId,
  products: [{
    product_id: ObjectId,
    quantity: Number,
    price: Number
  }],
  total_amount: Number,
  status: String,
  shipping_address: String,
  voucher_applied: ObjectId
}
```

## 🚦 Getting Started

1. **Start the development server**

   ```bash
   npm start
   ```

2. **Test the API**

   - Use Postman or any API client
   - Start with user registration: `POST /api/auth/signup`
   - Login to get JWT token: `POST /api/auth/login`
   - Use the token for protected endpoints

3. **Seed initial data** (optional)
   - Create admin user through signup with role "admin"
   - Add initial product categories
   - Create test products and orders

## 🔍 Environment Variables

Create a `.env` file for environment-specific configurations:

```env
PORT=8080
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_secret_key_here
NODE_ENV=development
```

## 🧪 Testing

To test the API endpoints:

1. **User Registration**

   ```bash
   POST /api/auth/signup
   {
     "name": "John Doe",
     "email": "john@example.com",
     "password": "password123",
     "role": "customer"
   }
   ```

2. **User Login**

   ```bash
   POST /api/auth/login
   {
     "email": "john@example.com",
     "password": "password123"
   }
   ```

3. **Create Product (Retailer)**
   ```bash
   POST /api/retailer/products
   Authorization: Bearer <token>
   {
     "name": "T-Shirt",
     "description": "Cotton T-Shirt",
     "price": 25.99,
     "category_id": "category_object_id",
     "stock_quantity": 100
   }
   ```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the ISC License - see the LICENSE file for details.

## 📞 Support

For support and questions:

- Create an issue in the GitHub repository
- Contact the development team
- Check the documentation for troubleshooting

## 🔄 Version History

- **v1.0.0** - Initial release with core functionality
- User authentication and authorization
- Product and order management
- Multi-role system implementation
- Dashboard analytics

---

**Built with ❤️ for the Trendy Shop e-commerce platform**
