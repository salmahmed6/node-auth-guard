# node-auth-guard

Authentication and Authorization package for Node.js/Express applications.

## Features

- User registration & login
- JWT-based authentication
- Email verification
- Password reset & change
- Role-based access control
- Secure cookie handling
- Modular controllers, middleware, and helpers

## Installation

```bash
npm install node-auth-guard
```

Or use as a local package:

```bash
npm install /path/to/node-auth-guard
```

## Usage

### 1. Environment Variables

Create a `.env` file in your project root:

```env
PORT=8000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
CLIENT_URL=http://localhost:3000
USER_EMAIL=your_email@example.com
NODE_ENV=development
```

### 2. Import and Use Routes

```javascript
import express from "express";
import cookieParser from "cookie-parser";
import userRoutes from "node-auth-guard/src/routes/userRoutes.js"; // adjust path if needed

const app = express();

app.use(express.json());
app.use(cookieParser());

// Use auth routes
app.use("/api/auth", userRoutes);

app.listen(8000, () => {
  console.log("Server running on port 8000");
});
```

### 3. Connect to Database

```javascript
import connect from "node-auth-guard/src/db/connect.js";

connect();
```

## Folder Structure

- `controllers/` - Auth controllers
- `db/` - Database connection
- `helpers/` - Utility functions
- `middleware/` - Auth middleware
- `models/` - Mongoose models
- `routes/` - Express routes
