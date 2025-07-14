<div align="justify">

# 🛍️ Trendy Shop

A modern full-stack e-commerce application built with React.js and Node.js, featuring a comprehensive shopping experience for customers, retailers, and administrators.

## 🌟 Features

### For Customers

- 🛒 Browse and search products
- 🛍️ Shopping cart management
- 💳 Secure checkout process
- 📦 Order tracking
- ⭐ Product reviews and ratings
- 👤 User profile management

### For Retailers

- 📊 Dashboard with sales analytics
- 📦 Product management (CRUD operations)
- 🎫 Voucher/discount management
- 📋 Order management
- 📈 Sales reporting

### For Administrators

- 👥 User management
- 🏪 Retailer management
- 📊 System analytics
- 🛠️ Platform administration

## 🚀 Tech Stack

### Frontend

- ⚛️ **React 18** - Modern React with hooks
- 🎨 **Tailwind CSS** - Utility-first CSS framework
- 🎭 **Material-UI** - React component library
- 🐜 **Ant Design** - Enterprise UI components
- 📊 **Chart.js** - Data visualization
- 🚦 **React Router** - Client-side routing
- 📡 **Axios** - HTTP client
- ⚡ **Vite** - Fast build tool

### Backend

- 🟢 **Node.js** - JavaScript runtime
- 🚀 **Express.js** - Web framework
- 🍃 **MongoDB** - NoSQL database
- 🦭 **Mongoose** - MongoDB object modeling
- 🔐 **JWT** - Authentication
- 🔒 **bcrypt** - Password hashing
- 🌐 **CORS** - Cross-origin resource sharing

## 📁 Project Structure

```
Trendy-Shop/
├── backend/                 # Node.js Express API
│   ├── config/             # Database configuration
│   ├── controllers/        # Route controllers
│   ├── models/             # Database models
│   ├── routes/             # API routes
│   ├── middleware.js       # Custom middleware
│   └── server.js           # Entry point
├── frontend/               # React application
│   ├── public/             # Static assets
│   ├── src/
│   │   ├── auth/           # Authentication components
│   │   ├── components/     # Reusable components
│   │   ├── context/        # React context providers
│   │   ├── pages/          # Page components
│   │   ├── routes/         # Route configuration
│   │   └── services/       # API service layer
│   └── package.json
└── README.md
```

## 🛠️ Installation & Setup

### Prerequisites

- Node.js (v16 or higher)
- MongoDB (local or cloud instance)
- npm or yarn package manager

### Backend Setup

1. Navigate to the backend directory:

   ```bash
   cd backend
   ```

2. Install dependencies:

   ```bash
   npm install
   ```

3. Create a `.env` file in the backend directory:

   ```env
   DB_URL=mongodb://localhost:27017/trendy-shop
   JWT_SECRET=your_jwt_secret_key
   PORT=5000
   ```

4. Start the backend server:
   ```bash
   npm start
   ```

The backend will run on `http://localhost:5000`

### Frontend Setup

1. Navigate to the frontend directory:

   ```bash
   cd frontend
   ```

2. Install dependencies:

   ```bash
   npm install
   ```

3. Create a `.env` file in the frontend directory:

   ```env
   VITE_API_URL=http://localhost:5000/api
   ```

4. Start the development server:
   ```bash
   npm run dev
   ```

The frontend will run on `http://localhost:5173`

## 🔌 API Endpoints

### Authentication

- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login
- `POST /api/auth/logout` - User logout

### Products

- `GET /api/products` - Get all products
- `GET /api/products/:id` - Get product by ID
- `POST /api/products` - Create new product (Retailer)
- `PUT /api/products/:id` - Update product (Retailer)
- `DELETE /api/products/:id` - Delete product (Retailer)

### Orders

- `GET /api/orders` - Get user orders
- `POST /api/orders` - Create new order
- `PUT /api/orders/:id` - Update order status

### Categories

- `GET /api/categories` - Get all categories
- `POST /api/categories` - Create category (Admin)

### Users

- `GET /api/users/profile` - Get user profile
- `PUT /api/users/profile` - Update user profile

## 🎯 User Roles

### Customer

- Browse products and categories
- Manage shopping cart
- Place and track orders
- Leave product reviews

### Retailer

- Manage product inventory
- View sales analytics
- Process orders
- Create discount vouchers

### Admin

- Manage all users and retailers
- System-wide analytics
- Platform configuration

## 🔐 Authentication

The application uses JWT (JSON Web Tokens) for authentication. Tokens are stored in localStorage and included in API requests via Authorization headers.

## 📱 Responsive Design

The application is fully responsive and works seamlessly across:

- 💻 Desktop computers
- 📱 Mobile devices
- 📊 Tablets

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the ISC License.

## 👨‍💻 Author

**NhanPhamThanh-IT**

## 🙏 Acknowledgments

- React.js community for excellent documentation
- Tailwind CSS for the utility-first approach
- MongoDB for the flexible database solution
- All contributors and users of this project

---

⭐ **Star this repository if you find it helpful!**

</div>
