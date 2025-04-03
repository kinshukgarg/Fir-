# FIR Management System

A comprehensive system for managing First Information Reports (FIRs) in police departments.

## Features

- User Authentication (Operator/Viewer roles)
- FIR Management (Create, Read, Update)
- Multiple Accused Management
- Recovery Information (Photo, Text, Audio)
- Challan Management
- Overdue Challan Notifications
- Report Generation (Excel format)

## Prerequisites

- Node.js (v14 or higher)
- MongoDB
- npm or yarn

## Setup

1. Clone the repository
2. Install dependencies:
   ```bash
   npm install
   ```
3. Create a `.env` file in the root directory with the following variables:
   ```
   PORT=5000
   MONGODB_URI=mongodb://localhost:27017/fir-system
   JWT_SECRET=your-secret-key-here
   EMAIL_FROM=noreply@fir-system.com
   ADMIN_EMAIL=admin@fir-system.com
   NODE_ENV=development
   ```
4. Start MongoDB
5. Start the server:
   ```bash
   npm run dev
   ```

## API Endpoints

### Authentication
- POST `/api/auth/login` - Login user
- POST `/api/auth/forgot-password` - Request password reset
- POST `/api/auth/reset-password` - Reset password

### FIR Management
- GET `/api/fir` - Get all FIRs (paginated)
- POST `/api/fir` - Create new FIR (Operator only)
- GET `/api/fir/:id` - Get single FIR
- PUT `/api/fir/:id` - Update FIR (Operator only)
- GET `/api/fir/overdue` - Get overdue challans
- POST `/api/fir/:id/recovery` - Add recovery information (Operator only)

### Reports
- GET `/api/reports` - Generate FIR report (Excel format)

### Notifications
- GET `/api/notifications` - Get all notifications
- POST `/api/notifications/send-reminder` - Send email reminders (Operator only)

## Security

- JWT-based authentication
- Role-based access control
- Password hashing
- Secure API endpoints

## Contributing

1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Create a new Pull Request 