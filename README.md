# AI Finance Tracker

AI Finance Tracker is a full-stack personal finance management application built with the MERN stack. It helps users track income and expenses, manage budgets, create savings goals, view analytics, upload receipts, receive notifications, and generate AI-powered financial insights.

## Features

- User registration, login, logout, and token refresh authentication
- Protected dashboard for authenticated users
- Transaction management for income and expenses
- Receipt upload support for images and PDFs
- Budget creation, updates, deletion, and recalculation
- Savings goal tracking with contribution updates
- Analytics dashboard with trends, categories, cash flow, and spending patterns
- AI-powered transaction categorization and financial insights
- Expense prediction and savings recommendations
- Notification center with read, delete, and clear-all actions
- Scheduled budget alert checks using cron jobs
- Responsive frontend built with React and Tailwind CSS

## Tech Stack

### Frontend

- **React 18** - UI library for building the client application
- **Vite 5** - Frontend build tool and development server
- **React Router DOM** - Client-side routing
- **Zustand** - Lightweight global state management
- **Axios** - HTTP client for API communication
- **Tailwind CSS** - Utility-first CSS framework
- **PostCSS** and **Autoprefixer** - CSS processing
- **Recharts** - Data visualization and charts
- **React Hot Toast** - Toast notifications
- **Lucide React** - Icon library
- **date-fns** - Date formatting and utilities

### Backend

- **Node.js** - JavaScript runtime
- **Express.js** - REST API framework
- **MongoDB** - NoSQL database
- **Mongoose** - MongoDB object modeling
- **JWT** - Access and refresh token authentication
- **bcryptjs** - Password hashing
- **cookie-parser** - Cookie parsing middleware
- **cors** - Cross-origin resource sharing
- **dotenv** - Environment variable management
- **express-validator** - Request validation
- **multer** - Multipart file upload handling
- **Cloudinary** - Receipt/media storage
- **multer-storage-cloudinary** - Cloudinary storage adapter
- **csv-parser** - CSV parsing support
- **node-cron** - Scheduled background jobs
- **Google Gemini API** - AI insights and transaction categorization
- **OpenAI SDK** - Installed AI SDK dependency

### Development Tools

- **Nodemon** - Backend auto-restart during development
- **Concurrently** - Run frontend and backend together from the root project
- **npm** - Package management
- **Vercel configuration** - Frontend deployment configuration

## Project Structure

```text
FinanceTracker/
|-- backend/
|   |-- controllers/         # Request handlers and business logic
|   |-- middleware/          # Authentication middleware
|   |-- models/              # Mongoose data models
|   |-- routes/              # Express API routes
|   |-- services/            # AI and notification services
|   |-- utils/               # JWT helper utilities
|   |-- package.json
|   `-- server.js            # Backend application entry point
|-- frontend/
|   |-- src/
|   |   |-- components/      # Reusable React components
|   |   |-- pages/           # Application pages
|   |   |-- services/        # API service helpers
|   |   |-- stores/          # Zustand stores
|   |   |-- utils/           # Frontend utilities
|   |   |-- App.jsx
|   |   |-- index.css
|   |   `-- main.jsx
|   |-- index.html
|   |-- package.json
|   |-- tailwind.config.js
|   |-- vite.config.js
|   `-- vercel.json
|-- package.json
`-- README.md
```

## Getting Started

### Prerequisites

Install the following before running the project:

- Node.js 18 or later
- npm
- MongoDB database, local or hosted
- Google Gemini API key
- Cloudinary account, if using receipt upload storage

### Installation

Clone the repository:

```bash
git clone https://github.com/jayantsingh-art/FinanceTracker.git
cd FinanceTracker
```

Install root, backend, and frontend dependencies:

```bash
npm run install-all
```

You can also install each app separately:

```bash
npm install
cd backend
npm install
cd ../frontend
npm install
```

## Environment Variables

Create a `.env` file inside the `backend` directory:

```env
PORT=5000
FRONTEND_URL=http://localhost:5173
MONGODB_URI=your_mongodb_connection_string

JWT_ACCESS_SECRET=your_access_token_secret
JWT_REFRESH_SECRET=your_refresh_token_secret
JWT_ACCESS_EXPIRY=15m
JWT_REFRESH_EXPIRY=7d

GEMINI_API_KEY=your_gemini_api_key

CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret
```

Create a `.env` file inside the `frontend` directory:

```env
VITE_API_URL=http://localhost:5000/api
```

## Running the Application

Run both frontend and backend from the root directory:

```bash
npm run dev
```

Run only the backend:

```bash
npm run server
```

Run only the frontend:

```bash
npm run client
```

Default local URLs:

- Frontend: `http://localhost:5173`
- Backend API: `http://localhost:5000/api`
- Health check: `http://localhost:5000/api/health`

## Available Scripts

### Root

```bash
npm run dev          # Run backend and frontend together
npm run server       # Start backend in development mode
npm run client       # Start frontend in development mode
npm run install-all  # Install dependencies for root, backend, and frontend
```

### Backend

```bash
npm run dev    # Start backend with nodemon
npm start      # Start backend with node
```

### Frontend

```bash
npm run dev      # Start Vite dev server
npm run build    # Build production frontend
npm run preview  # Preview production build locally
```

## API Overview

The backend exposes REST API routes under `/api`.

| Module | Base Route | Description |
| --- | --- | --- |
| Auth | `/api/auth` | Register, login, refresh token, logout, and current user |
| Transactions | `/api/transactions` | Create, read, update, delete, and upload receipts |
| Budgets | `/api/budgets` | Manage budgets and recalculate budget usage |
| Savings Goals | `/api/savings-goals` | Manage savings goals and add contributions |
| Analytics | `/api/analytics` | Dashboard, trends, categories, cash flow, and spending patterns |
| AI | `/api/ai` | Categorization, summaries, predictions, and recommendations |
| Notifications | `/api/notifications` | Read, delete, and clear notifications |
| Health | `/api/health` | Server health check |

## Authentication

The application uses JWT-based authentication with access and refresh tokens. Protected backend routes use authentication middleware and require a valid bearer token in the request headers.

## AI Capabilities

The AI service uses Google Gemini to:

- Categorize transactions from descriptions and amounts
- Explain spending changes between periods
- Predict upcoming expenses from historical data
- Generate financial summaries
- Recommend ways to reach savings goals faster

## Deployment Notes

- The frontend includes a `vercel.json` file and can be deployed to Vercel.
- The backend requires a Node.js hosting environment with access to MongoDB and the required environment variables.
- Set `FRONTEND_URL` on the backend to the deployed frontend URL.
- Set `VITE_API_URL` on the frontend to the deployed backend API URL.

## License

This project is licensed under the ISC License.
