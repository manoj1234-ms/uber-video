# Uber Clone

A full-stack ride-hailing application built with React, Node.js, Socket.IO, and MongoDB.

## Features

- User and Captain authentication
- Real-time location tracking
- Ride booking and fare calculation
- OTP verification for ride starts
- Live ride status updates
- Multiple vehicle types (Car, Auto, Moto)

## Tech Stack

### Frontend
- React
- TailwindCSS
- GSAP (for animations)
- Socket.IO Client
- Axios
- React Router DOM
- Google Maps API

### Backend
- Node.js
- Express
- MongoDB
- Socket.IO
- JWT Authentication
- Google Maps API

## Environment Variables

### Frontend (.env)
```
VITE_BASE_URL=http://localhost:3000
VITE_GOOGLE_MAPS_API=your_google_maps_api_key
```

### Backend (.env)
```
PORT=3000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
GOOGLE_MAPS_API=your_google_maps_api_key
```

## API Routes

### User Routes
- POST `/users/register` - Register new user
- POST `/users/login` - User login
- GET `/users/profile` - Get user profile
- GET `/users/logout` - User logout

### Captain Routes
- POST `/captains/register` - Register new captain
- POST `/captains/login` - Captain login
- GET `/captains/profile` - Get captain profile
- GET `/captains/logout` - Captain logout

### Ride Routes
- POST `/rides/create` - Create new ride
- GET `/rides/get-fare` - Calculate ride fare
- POST `/rides/confirm` - Confirm ride by captain
- GET `/rides/start-ride` - Start ride with OTP
- POST `/rides/end-ride` - End ongoing ride

### Maps Routes
- GET `/maps/get-coordinates` - Get coordinates from address
- GET `/maps/get-distance-time` - Calculate distance and time
- GET `/maps/get-suggestions` - Get location suggestions

## Frontend Routes

### User Routes
- `/` - Start page
- `/login` - User login
- `/signup` - User registration
- `/home` - User dashboard
- `/riding` - Active ride view

### Captain Routes
- `/captain-login` - Captain login
- `/captain-signup` - Captain registration
- `/captain-home` - Captain dashboard
- `/captain-riding` - Captain's active ride view

## Socket Events

### User Events
- `join` - User joins socket room
- `ride-confirmed` - When captain accepts ride
- `ride-started` - When ride starts
- `ride-ended` - When ride ends

### Captain Events
- `join` - Captain joins socket room
- `update-location-captain` - Update captain's location
- `new-ride` - New ride request
- `error` - Socket error event

## Setup Instructions

1. Clone the repository
2. Install dependencies in both frontend and backend:
```bash
cd Frontend && npm install
cd ../Backend && npm install
```

3. Set up environment variables

4. Start the development servers:
```bash
# Root directory
npm run uber
```

This will start both frontend and backend servers concurrently.

Frontend runs on: http://localhost:5173
Backend runs on: http://localhost:3000

## Project Structure

```
├── Frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── context/
│   │   ├── pages/
│   │   └── main.jsx
│   └── package.json
├── Backend/
│   ├── controllers/
│   ├── models/
│   ├── routes/
│   ├── services/
│   ├── app.js
│   └── package.json
└── package.json
```
