# 🎨 Trendy Shop Frontend

A modern, responsive React.js frontend application for the Trendy Shop e-commerce platform. Built with Vite, Tailwind CSS, and a comprehensive set of modern web technologies.

## 🌟 Features

### 🛍️ Customer Features

- **Product Catalog**: Browse products with advanced filtering and search
- **Shopping Cart**: Real-time cart management with quantity updates
- **Secure Checkout**: Multi-step checkout process with order summary
- **User Authentication**: Login/Register with JWT token management
- **Order History**: Track past purchases and order status
- **Product Reviews**: Read and write product reviews
- **Responsive Design**: Optimized for mobile, tablet, and desktop

### 🏪 Retailer Features

- **Dashboard Analytics**: Sales charts and performance metrics
- **Product Management**: CRUD operations for product inventory
- **Order Management**: Process and track customer orders
- **Voucher System**: Create and manage discount vouchers
- **Profile Management**: Update retailer information

### 👑 Admin Features

- **System Dashboard**: Overview of platform metrics
- **User Management**: Manage customers and retailers
- **Content Management**: Categories and system settings
- **Analytics**: Comprehensive reporting and insights

## 🚀 Tech Stack

### Core Technologies

- ⚛️ **React 18.3** - Modern React with hooks and concurrent features
- ⚡ **Vite 6.0** - Lightning-fast build tool and dev server
- 🎨 **Tailwind CSS 3.4** - Utility-first CSS framework
- 📦 **React Router DOM 7.0** - Client-side routing

### UI Components & Libraries

- 🎭 **Material-UI 6.3** - React component library
- 🐜 **Ant Design 5.22** - Enterprise UI components
- 📊 **Chart.js 4.4** - Data visualization
- 🔄 **React Chart.js 2** - React wrapper for Chart.js
- 🗓️ **React DatePicker** - Date selection components
- 📄 **React Paginate** - Pagination components
- 🎯 **React Icons** - Icon library

### Development Tools

- 📝 **ESLint 9.15** - Code linting and formatting
- 🎯 **PostCSS & Autoprefixer** - CSS processing
- 🔧 **SWC** - Fast JavaScript/TypeScript compiler

### HTTP & State Management

- 📡 **Axios 1.7** - HTTP client for API calls
- 🔄 **React Context API** - State management
- 🛡️ **JWT Authentication** - Secure token-based auth

## 📁 Project Structure

```
src/
├── auth/                   # Authentication components
│   ├── Authorization.jsx   # Role-based access control
│   └── PrivateRoute.jsx   # Protected route wrapper
├── components/            # Reusable UI components
│   ├── admin/            # Admin-specific components
│   │   ├── AdminAside.jsx
│   │   ├── DashboardView/
│   │   ├── Helper/
│   │   └── ManageRetailerView/
│   ├── customer/         # Customer-facing components
│   │   ├── CartDetails.jsx
│   │   ├── CheckoutForm.jsx
│   │   ├── CustomerFooter.jsx
│   │   ├── CustomerHeader.jsx
│   │   ├── ProductCard.jsx
│   │   ├── ProductInfo.jsx
│   │   └── SearchBar.jsx
│   ├── partials/         # Shared components
│   │   ├── ProfileHeader.jsx
│   │   └── ProfileMain.jsx
│   └── retailer/         # Retailer dashboard components
│       ├── RetailerAside.jsx
│       ├── DashboardView/
│       ├── OrderView/
│       └── VoucherView/
├── context/              # React Context providers
│   ├── AuthContext.jsx   # Authentication state
│   ├── CartContext.jsx   # Shopping cart state
│   └── DropdownContext.jsx # UI state management
├── pages/                # Page components
│   ├── admin/           # Admin pages
│   │   ├── AdminDashboard.jsx
│   │   ├── AdminLayout.jsx
│   │   └── AdminProfile.jsx
│   ├── authentication/ # Auth pages
│   │   ├── Login.jsx
│   │   └── Signup.jsx
│   ├── customer/       # Customer pages
│   │   ├── CustomerHome.jsx
│   │   ├── CustomerCart.jsx
│   │   ├── CustomerCheckout.jsx
│   │   └── CustomerAccount.jsx
│   └── retailer/       # Retailer pages
│       ├── RetailerDashboard.jsx
│       ├── RetailerOrders.jsx
│       └── RetailerProfile.jsx
├── routes/             # Route configuration
│   └── routes.jsx      # Main routing logic
├── services/           # API service layer
│   ├── authenticationService.js
│   ├── productService.js
│   ├── orderService.js
│   ├── categoryService.js
│   ├── userService.js
│   ├── retailerService.js
│   ├── adminService.js
│   ├── feedbackService.js
│   └── voucherService.js
├── App.jsx            # Main app component
├── main.jsx           # App entry point
├── App.css            # Global styles
└── index.css          # Base styles
```

## 🛠️ Installation & Setup

### Prerequisites

- **Node.js** (v16 or higher)
- **npm** or **yarn** package manager
- **Backend API** running on port 8080

### Quick Start

1. **Clone and navigate to frontend:**

   ```bash
   cd frontend
   ```

2. **Install dependencies:**

   ```bash
   npm install
   ```

3. **Create environment file:**

   ```bash
   # Create .env file in frontend root
   touch .env
   ```

4. **Configure environment variables:**

   ```env
   # .env
   VITE_API_URL=http://localhost:8080/api
   VITE_APP_NAME=Trendy Shop
   VITE_APP_VERSION=1.0.0
   ```

5. **Start development server:**

   ```bash
   npm run dev
   ```

6. **Open in browser:**
   Navigate to `http://localhost:5173`

## 📜 Available Scripts

| Command           | Description                              |
| ----------------- | ---------------------------------------- |
| `npm run dev`     | Start development server with hot reload |
| `npm run build`   | Build production-ready application       |
| `npm run preview` | Preview production build locally         |
| `npm run lint`    | Run ESLint for code quality checks       |

## 🔧 Configuration Files

### Vite Configuration (`vite.config.js`)

```javascript
import { defineConfig } from "vite";
import react from "@vitejs/plugin-react-swc";

export default defineConfig({
  plugins: [react()],
  server: {
    port: 5173,
    open: true,
  },
});
```

### Tailwind Configuration (`tailwind.config.js`)

```javascript
export default {
  content: ["./index.html", "./src/**/*.{js,ts,jsx,tsx}"],
  theme: {
    extend: {
      // Custom theme extensions
    },
  },
  plugins: [],
};
```

### ESLint Configuration (`eslint.config.js`)

Configured with React 18.3 support and modern JavaScript standards.

## 🌐 API Integration

### Service Layer Architecture

All API calls are organized in the `services/` directory:

- **Authentication**: Login, signup, logout
- **Products**: CRUD operations, search, filtering
- **Orders**: Create, track, manage orders
- **Categories**: Product categorization
- **Users**: Profile management
- **Retailers**: Seller operations
- **Admin**: System management
- **Feedback**: Reviews and ratings
- **Vouchers**: Discount management

### API Base Configuration

```javascript
// Example service structure
import axios from "axios";

const API_BASE = "http://localhost:8080/api";

const authService = {
  login: async (email, password) => {
    const response = await axios.post(`${API_BASE}/auth/login`, {
      email,
      password,
    });
    return response.data;
  },
};
```

## 🔐 Authentication Flow

### JWT Token Management

- Tokens stored in `localStorage`
- Automatic token inclusion in API requests
- Role-based route protection
- Automatic logout on token expiration

### User Roles

1. **Customer** - Shopping and order management
2. **Retailer** - Product and order management
3. **Admin** - System administration

### Protected Routes

```javascript
// Example protected route
<PrivateRoute roles={["admin"]}>
  <AdminDashboard />
</PrivateRoute>
```

## 🎨 Styling & UI

### Tailwind CSS

- Utility-first approach
- Responsive design system
- Custom color palette
- Dark mode support (configurable)

### Component Libraries

- **Material-UI**: Complex components and layouts
- **Ant Design**: Data tables and forms
- **React Icons**: Consistent iconography

### Responsive Breakpoints

```css
/* Tailwind default breakpoints */
sm: 640px   /* Mobile landscape */
md: 768px   /* Tablet */
lg: 1024px  /* Desktop */
xl: 1280px  /* Large desktop */
2xl: 1536px /* Extra large */
```

## 📊 State Management

### React Context Providers

1. **AuthContext**: User authentication state
2. **CartContext**: Shopping cart management
3. **DropdownContext**: UI component states

### Context Usage Example

```javascript
import { useContext } from "react";
import { AuthContext } from "../context/AuthContext";

const MyComponent = () => {
  const { isAuthenticated, user, login, logout } = useContext(AuthContext);
  // Component logic
};
```

## 🚀 Performance Optimizations

### Code Splitting

- Lazy loading for route components
- Dynamic imports for large dependencies

### Bundle Optimization

- Vite's automatic code splitting
- Tree shaking for unused code elimination
- Asset optimization and compression

### Caching Strategy

- Service worker implementation (configurable)
- API response caching
- Image lazy loading

## 🧪 Development Guidelines

### Code Style

- ESLint configuration for consistent code style
- Prettier integration recommended
- Component naming conventions (PascalCase)
- File organization by feature

### Best Practices

- Use functional components with hooks
- Implement proper error boundaries
- Follow accessibility guidelines (WCAG 2.1)
- Optimize for SEO with proper meta tags

### Component Structure

```javascript
// Recommended component structure
import { useState, useEffect } from "react";
import PropTypes from "prop-types";

const MyComponent = ({ prop1, prop2 }) => {
  // State and hooks
  const [state, setState] = useState(initialState);

  // Effects
  useEffect(() => {
    // Side effects
  }, [dependencies]);

  // Event handlers
  const handleEvent = () => {
    // Handle logic
  };

  // Render
  return <div className="component-styles">{/* JSX content */}</div>;
};

MyComponent.propTypes = {
  prop1: PropTypes.string.required,
  prop2: PropTypes.number,
};

export default MyComponent;
```

## 🔍 Debugging & Development Tools

### Browser DevTools

- React Developer Tools extension
- Redux DevTools (if needed)
- Network tab for API debugging

### Console Debugging

- Environment-based logging
- Error tracking and reporting
- Performance monitoring

## 📱 Browser Support

| Browser | Version           |
| ------- | ----------------- |
| Chrome  | Latest 2 versions |
| Firefox | Latest 2 versions |
| Safari  | Latest 2 versions |
| Edge    | Latest 2 versions |

## 🚢 Deployment

### Build for Production

```bash
npm run build
```

### Preview Production Build

```bash
npm run preview
```

### Deploy to Hosting Services

- **Vercel**: Zero-config deployment
- **Netlify**: Continuous deployment
- **GitHub Pages**: Static hosting
- **AWS S3 + CloudFront**: Scalable hosting

## 🤝 Contributing

### Development Workflow

1. Fork the repository
2. Create feature branch (`git checkout -b feature/amazing-feature`)
3. Make changes following code style guidelines
4. Test thoroughly across different devices
5. Commit with descriptive messages
6. Push to feature branch
7. Create Pull Request

### Code Review Process

- Ensure all tests pass
- Follow component and styling guidelines
- Update documentation if needed
- Get approval from maintainers

## 📚 Additional Resources

### Documentation

- [React Documentation](https://react.dev/)
- [Vite Documentation](https://vitejs.dev/)
- [Tailwind CSS Documentation](https://tailwindcss.com/)
- [Material-UI Documentation](https://mui.com/)

### Learning Resources

- React Hooks patterns
- Modern JavaScript (ES6+)
- CSS Grid and Flexbox
- Responsive web design principles

## 🐛 Troubleshooting

### Common Issues

**Port already in use:**

```bash
# Change port in vite.config.js or kill process
npx kill-port 5173
```

**Module not found errors:**

```bash
# Clear node_modules and reinstall
rm -rf node_modules package-lock.json
npm install
```

**Build errors:**

```bash
# Clear Vite cache
npx vite --force
```

## 📄 License

This project is licensed under the ISC License.

## 👨‍💻 Frontend Team

**NhanPhamThanh-IT** - Frontend Developer & Maintainer

---

🎯 **Happy Coding!** Star ⭐ this repository if you find it useful!
