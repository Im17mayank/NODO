# NODO Setup Guide

## Prerequisites

Make sure you have the following installed:
- Node.js (v16 or higher)
- MongoDB (local installation or MongoDB Atlas)
- Git

## Quick Start

1. **Install Backend Dependencies**
```bash
# Install backend dependencies
npm install

# Install frontend dependencies  
cd client
npm install
cd ..
```

2. **Database Setup**
- Make sure MongoDB is running locally on port 27017
- Or update the MONGODB_URI in `server/.env` to point to your MongoDB instance

3. **Environment Configuration**
- The `server/.env` file is already configured for development
- Update JWT_SECRET in production
- Configure email settings if needed

4. **Start the Application**
```bash
# Start both backend and frontend (from root directory)
npm run dev

# Or start separately:
# Backend only:
npm run server

# Frontend only:
npm run client
```

5. **Access the Application**
- Frontend: http://localhost:3000
- Backend API: http://localhost:5000
- API Health Check: http://localhost:5000/api/health

## Demo Accounts

Create these demo accounts by registering or use the API:

### Admin Account
- Email: admin@nodo.org
- Password: password123
- Role: admin

### Volunteer Account  
- Email: volunteer@nodo.org
- Password: password123
- Role: volunteer

### Donor Account
- Email: donor@nodo.org  
- Password: password123
- Role: donor

## Features

### ✅ Implemented (MVP)
- User authentication and authorization
- Role-based access control (Admin, Volunteer, Donor)
- Centralized dashboard with statistics
- Database models for all core entities
- Multi-language support (English/Spanish)
- Responsive React frontend
- RESTful API backend

### 🚧 Placeholder Features (Ready for Development)
- Donation management (CRUD operations)
- Volunteer registration and management  
- Project creation and tracking
- Task assignment and tracking
- Basic reporting system
- Advanced dashboard features

## Project Structure

```
NODO/
├── server/              # Backend API
│   ├── models/          # Database models
│   ├── routes/          # API routes  
│   ├── middleware/      # Auth & validation
│   ├── config/          # Database & i18n config
│   ├── locales/         # Translation files
│   └── index.js         # Server entry point
├── client/              # Frontend React app
│   ├── src/
│   │   ├── components/  # React components
│   │   ├── pages/       # Page components
│   │   ├── contexts/    # React contexts
│   │   ├── hooks/       # Custom hooks
│   │   └── services/    # API services
└── docs/                # Documentation
```

## API Endpoints

### Authentication
- `POST /api/auth/register` - Register user
- `POST /api/auth/login` - Login user  
- `GET /api/auth/profile` - Get user profile
- `PUT /api/auth/profile` - Update profile
- `POST /api/auth/change-password` - Change password

### Dashboard
- `GET /api/dashboard/stats` - Get overview statistics
- `GET /api/dashboard/my-summary` - Get personalized summary
- `GET /api/dashboard/notifications` - Get user notifications

### Data Management (Basic endpoints implemented)
- `GET /api/donations` - Get donations
- `GET /api/volunteers` - Get volunteers
- `GET /api/projects` - Get projects  
- `GET /api/tasks` - Get tasks
- `GET /api/reports/*` - Various reports

## Development

### Adding New Features
1. Create database model in `server/models/`
2. Add API routes in `server/routes/`
3. Create frontend pages in `client/src/pages/`
4. Add navigation links in sidebar component

### Database Models
All models are fully defined with:
- Validation rules
- Indexes for performance
- Virtual properties
- Static methods for queries
- Pre/post middleware

### Frontend Architecture
- React with functional components and hooks
- React Router for navigation
- Bootstrap for styling
- Axios for API calls
- Context API for state management

## Deployment

### Environment Variables (Production)
Update these in production:
- `JWT_SECRET` - Use a secure random string
- `MONGODB_URI` - Point to production database
- `NODE_ENV=production`
- Configure email settings for notifications

### Build Commands
```bash
# Build frontend for production
npm run build

# Start production server
npm start
```

## Support

For questions or issues:
1. Check the API health endpoint: `/api/health`
2. Review server logs for errors
3. Ensure MongoDB is running and accessible
4. Verify all dependencies are installed

## Next Steps

The MVP provides a solid foundation. Priority features to implement:
1. Complete donation management with payment integration
2. Advanced volunteer scheduling and time tracking
3. Project milestone tracking and progress visualization
4. Enhanced reporting with charts and exports
5. Email notifications and reminders
6. File upload and document management
