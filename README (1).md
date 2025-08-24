# NODO - NGO Management System MVP

NODO is a comprehensive NGO management system that provides a centralized dashboard for donations, volunteer management, project progress tracking, task assignment, and basic reporting with multi-language support.

## Features

- **Centralized Dashboard**: Overview of donations, volunteer activities, and project progress
- **Donation Management**: Track and manage donations with detailed reporting
- **Volunteer Management**: Register, manage, and assign volunteers to projects
- **Task Assignment & Tracking**: Create, assign, and monitor task progress
- **Basic Reporting**: Generate reports for donations, volunteers, and projects
- **Multi-language Support**: Available in multiple languages (English, Spanish)
- **Role-based Access Control**: Admin, Volunteer, and Donor roles

## Tech Stack

### Backend
- Node.js with Express.js
- MongoDB with Mongoose
- JWT Authentication
- i18next for internationalization

### Frontend  
- React.js
- React Router for navigation
- Axios for API calls
- Chart.js for data visualization
- Bootstrap for responsive design

## Installation

1. Clone the repository:
```bash
git clone https://github.com/your-org/nodo.git
cd NODO
```

2. Install dependencies for both backend and frontend:
```bash
npm run install-all
```

3. Create environment file:
```bash
cp server/.env.example server/.env
```

4. Configure your environment variables in `server/.env`:
- Database connection string
- JWT secret
- Email configuration (optional)

5. Start the development server:
```bash
npm run dev
```

## API Endpoints

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - User login
- `GET /api/auth/profile` - Get user profile

### Donations
- `GET /api/donations` - Get all donations
- `POST /api/donations` - Create new donation
- `GET /api/donations/:id` - Get donation by ID
- `PUT /api/donations/:id` - Update donation
- `DELETE /api/donations/:id` - Delete donation

### Volunteers
- `GET /api/volunteers` - Get all volunteers
- `POST /api/volunteers` - Register new volunteer
- `GET /api/volunteers/:id` - Get volunteer by ID
- `PUT /api/volunteers/:id` - Update volunteer
- `DELETE /api/volunteers/:id` - Remove volunteer

### Projects & Tasks
- `GET /api/projects` - Get all projects
- `POST /api/projects` - Create new project
- `GET /api/projects/:id/tasks` - Get project tasks
- `POST /api/tasks` - Create new task
- `PUT /api/tasks/:id` - Update task status

### Reports
- `GET /api/reports/donations` - Donation reports
- `GET /api/reports/volunteers` - Volunteer activity reports
- `GET /api/reports/projects` - Project progress reports

## Project Structure

```
NODO/
├── server/              # Backend API
│   ├── models/          # Database models
│   ├── routes/          # API routes
│   ├── middleware/      # Custom middleware
│   ├── config/          # Configuration files
│   ├── locales/         # Translation files
│   └── index.js         # Server entry point
├── client/              # Frontend React app
│   ├── src/
│   │   ├── components/  # React components
│   │   ├── pages/       # Page components
│   │   ├── services/    # API services
│   │   ├── utils/       # Utility functions
│   │   └── locales/     # Translation files
└── docs/                # Documentation

```

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## License

This project is licensed under the MIT License - see the LICENSE file for details.
