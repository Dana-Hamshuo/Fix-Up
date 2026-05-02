#  Fix-Up - On-Demand Repair Services Platform

A backend system for connecting users with nearby repair technicians for electronic and electrical issues.

##  Overview

Fix-Up is a location-based service platform that bridges the gap between customers facing technical issues and qualified repair technicians. Users can report problems, and the system intelligently matches them with the nearest available technicians.

###  The Problem
- Customers struggle to find reliable, nearby repair services
- Technicians miss job opportunities in their area
- No centralized platform for on-demand repair services

###  The Solution
- Users report issues via the platform
- System calculates proximity using geolocation
- Nearest technicians are notified and can respond
- Built-in communication channel for coordination

##  Features

### Core Functionality
-  **Dual Authentication**: 
  -  Traditional: Email/Password with JWT + Email Verification
  -  OAuth: Google Sign-In with secure token exchange
-  **Email Verification Flow**: 
  - Users receive verification link via email
  - Token-based confirmation with expiration
  - Auto-login after successful verification
-  **Role-Based Access**: Separate dashboards and permissions for `user` and `technician`
-  **Service Requests**: Create, update, and track repair requests with categories
-  **Geolocation Matching**: Find nearest technicians using MongoDB geospatial queries
-  **Real-time Communication**: Integrated chat system for coordination
-  **Status Tracking**: Full request lifecycle management
### Advanced Features
-  JWT + OAuth 2.0 with refresh tokens
-  Email verification with expiration & resend
-  Geospatial indexing for efficient location-based queries
-  RESTful API design for easy mobile app integration
-  Notification system for new requests and status updates
-  Technician rating and review system (ready for implementation)

##  Tech Stack

**Backend:**
- Node.js + Express.js
- MongoDB + Mongoose ODM
- JWT (JSON Web Tokens) for authentication
- Bcrypt.js for password hashing

**Geolocation:**
- MongoDB Geospatial Queries (`2dsphere` index)
- GeoJSON for location data

**Communication:**
- Integrated third-party chat solution (Socket.io / Firebase / etc.)

**Architecture:**
- MVC Pattern
- Middleware-based validation & auth
- Service-oriented business logic
  
- **Authentication:**
- JWT (JSON Web Tokens) with refresh logic
- Google OAuth 2.0 via Passport.js / google-auth-library
- Nodemailer for transactional emails (verification, reset)
- Bcrypt.js for password hashing

**Security:**
- Email verification tokens with expiration
- OAuth state parameter to prevent CSRF
- Rate limiting on auth endpoints

##  Project Structure
