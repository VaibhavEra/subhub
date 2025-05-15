# SubHub - Subscription Management API

SubHub is a robust backend API service designed to help users track and manage their subscriptions. Built with Node.js and Express, this API provides comprehensive subscription management capabilities with secure user authentication.

## Tech Stack

- **Backend**: Node.js, Express.js
- **Database**: MongoDB with Mongoose ODM
- **Authentication**: JWT
- **Security**: Arcjet
- **Caching**: Upstash

## Project Structure

The project follows a modular architecture:

```
subhub/
├── config/           # Environment and configuration settings
├── database/         # Database connection and models
├── models/           # Mongoose schemas
│   ├── User.js
│   └── Subscription.js
├── routes/           # API route definitions
│   ├── auth.routes.js
│   ├── user.routes.js
│   └── subscription.routes.js
├── app.js            # Main application entry point
└── package.json
```

## API Endpoints

### Authentication

- `POST /api/v1/auth/sign-up` - Register a new user
- `POST /api/v1/auth/sign-in` - Authenticate a user
- `POST /api/v1/auth/sign-out` - End a user session

### Users

- `GET /api/v1/users` - Get all users
- `GET /api/v1/users/:id` - Get a specific user
- `POST /api/v1/users` - Create a new user
- `PUT /api/v1/users/:id` - Update a user
- `DELETE /api/v1/users/:id` - Delete a user

### Subscriptions

- `GET /api/v1/subscriptions` - Get all subscriptions
- `GET /api/v1/subscriptions/:id` - Get a specific subscription
- `POST /api/v1/subscriptions` - Create a new subscription
- `PUT /api/v1/subscriptions/:id` - Update a subscription
- `DELETE /api/v1/subscriptions/:id` - Delete a subscription
- `GET /api/v1/subscriptions/user/:id` - Get all subscriptions for a user
- `PUT /api/v1/subscriptions/:id/cancel` - Cancel a subscription
- `GET /api/v1/subscriptions/upcoming-renewals` - Get upcoming renewals

## Data Models

### User Model

- Basic user information with email validation
- Secure password storage
- Timestamp tracking

### Subscription Model

- Detailed subscription information
- Multiple currency support
- Automatic renewal date calculation
- Status tracking (active, cancelled, expired)
- Categorization

## Getting Started

1. Clone the repository:

   ```bash
   git clone https://github.com/VaibhavEra/subhub.git
   cd subhub
   ```

2. Install dependencies:

   ```bash
   npm install
   ```

3. Set up environment variables:
   Create a `.env.development.local` file with:

   ```
   PORT=3000
   NODE_ENV=development
   DB_URI=mongodb://localhost:27017/subhub
   ```

4. Run the development server:
   ```bash
   npm run dev
   ```

## Features

- User authentication and account management
- Comprehensive subscription tracking
- Multi-currency support
- Automatic renewal monitoring
- Subscription categorization
- Easily extensible API architecture
