# BookHeaven

BookHeaven is a full-stack e-commerce platform for buying and managing books. It features user authentication, book browsing, cart and favourites functionality, order placement, and admin capabilities for book management and order processing.

## Features

### User Features
- User registration and login
- Browse all books and recently added books
- View detailed book information
- Add books to cart and favourites
- Place orders
- View order history
- Update user profile and address

### Admin Features
- Add new books to the catalog
- Update existing book details
- Delete books from the catalog
- View all orders
- Update order status

## Tech Stack

### Backend
- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **MongoDB** - Database
- **Mongoose** - ODM for MongoDB
- **JWT** - Authentication
- **bcryptjs** - Password hashing
- **CORS** - Cross-origin resource sharing
- **dotenv** - Environment variables

### Frontend
- **React** - UI library
- **Vite** - Build tool and dev server
- **Redux Toolkit** - State management
- **Axios** - HTTP client
- **React Router** - Client-side routing
- **Tailwind CSS** - CSS framework
- **ESLint** - Code linting

## Installation and Setup

### Prerequisites
- Node.js (v14 or higher)
- MongoDB (local or cloud instance like MongoDB Atlas)
- npm or yarn

### Backend Setup
1. Navigate to the backend directory:
   ```bash
   cd backend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Create a `.env` file in the backend directory with the following variables:
   ```
   PORT=1000
   MONGODB_URI=your_mongodb_connection_string
   JWT_SECRET=your_jwt_secret_key
   ```

4. Start the backend server:
   ```bash
   npm run app
   ```

The backend will run on `http://localhost:1000`.

### Frontend Setup
1. Navigate to the frontend directory:
   ```bash
   cd frontend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start the development server:
   ```bash
   npm run dev
   ```

The frontend will run on `http://localhost:5173` (default Vite port).

## Usage

1. Open your browser and go to `http://localhost:5173`
2. Sign up for a new account or log in with existing credentials
3. Browse books on the home page or view all books
4. Add books to your cart or favourites
5. Proceed to checkout to place orders
6. View your profile for favourites, order history, and settings

### Admin Access
To access admin features, create a user account and manually set the role to "admin" in the database, or modify the user creation logic to allow admin registration.

## API Endpoints

### Authentication
- `POST /api/v1/sign-up` - User registration
- `POST /api/v1/sign-in` - User login

### Books
- `GET /api/v1/get-all-books` - Get all books
- `GET /api/v1/get-recent-books` - Get recently added books (limit 4)
- `GET /api/v1/get-book-by-id/:id` - Get book by ID
- `POST /api/v1/add-book` - Add new book (Admin only)
- `PUT /api/v1/update-book` - Update book (Admin only)
- `DELETE /api/v1/delete-book` - Delete book (Admin only)

### User
- `GET /api/v1/get-user-information` - Get user information
- `PUT /api/v1/update-address` - Update user address

### Cart
- `PUT /api/v1/add-to-cart` - Add book to cart
- `PUT /api/v1/remove-from-cart` - Remove book from cart
- `GET /api/v1/get-user-cart` - Get user's cart

### Favourites
- `PUT /api/v1/add-book-to-favourite` - Add book to favourites
- `PUT /api/v1/remove-book-from-favourite` - Remove book from favourites
- `GET /api/v1/get-favourite-books` - Get user's favourite books

### Orders
- `POST /api/v1/place-order` - Place an order
- `GET /api/v1/get-order-history` - Get user's order history
- `GET /api/v1/get-all-orders` - Get all orders (Admin only)
- `PUT /api/v1/update-status/:id` - Update order status (Admin only)

## Project Structure

```
bookheaven/
├── backend/
│   ├── models/
│   │   ├── book.js
│   │   ├── order.js
│   │   └── user.js
│   ├── routes/
│   │   ├── book.js
│   │   ├── cart.js
│   │   ├── favourite.js
│   │   ├── order.js
│   │   ├── user.js
│   │   └── userAuth.js
│   ├── conn/
│   │   └── conn.js
│   ├── app.js
│   ├── package.json
│   └── package-lock.json
└── frontend/
    ├── public/
    ├── src/
    │   ├── components/
    │   ├── pages/
    │   ├── store/
    │   ├── App.jsx
    │   ├── main.jsx
    │   └── index.css
    ├── package.json
    ├── package-lock.json
    ├── vite.config.js
    ├── tailwind.config.js
    ├── postcss.config.js
    └── eslint.config.js
```

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the ISC License.
