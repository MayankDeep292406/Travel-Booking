# Travel Booking Website — MERN starter

A premium, responsive travel booking platform built with React + Vite + Tailwind CSS on the frontend and Express + MongoDB on the backend.

## Features
- Responsive travel landing page with hero search, destination cards, offers and newsletter UI
- Destination listing and destination detail pages
- Register / login with JWT authentication
- Create and view bookings
- Admin-ready API structure for destinations and bookings
- MongoDB models, validation and error handling

## Requirements
- Node.js 20+
- MongoDB local instance or MongoDB Atlas connection string

## Run locally

### 1. Backend
```bash
cd server
cp .env.example .env
# Add your MongoDB URI and JWT secret to .env
npm install
npm run dev
```
The API runs at `http://localhost:5000`.

### 2. Frontend
Open another terminal:
```bash
cd client
npm install
npm run dev
```
Open the Vite URL shown in your terminal (normally `http://localhost:5173`).

## Environment
`server/.env`
```env
PORT=5000
MONGO_URI=mongodb://127.0.0.1:27017/travel_booking
JWT_SECRET=replace_with_a_long_random_secret
CLIENT_URL=http://localhost:5173
```

## API routes
- `GET /api/health`
- `GET /api/destinations`
- `GET /api/destinations/:id`
- `POST /api/auth/register`
- `POST /api/auth/login`
- `GET /api/auth/me` (JWT)
- `POST /api/bookings` (JWT)
- `GET /api/bookings/my` (JWT)
- `GET /api/bookings` (admin JWT)
- `POST /api/destinations` (admin JWT)
- `PUT /api/destinations/:id` (admin JWT)
- `DELETE /api/destinations/:id` (admin JWT)

## Create an admin user
Register a normal user, then set that user's `role` to `admin` in MongoDB. Admin endpoints require a valid JWT belonging to an admin account.

## Notes
- The destination images are remote Unsplash source URLs for demo presentation. Replace them with your licensed image assets before production.
- The booking flow creates a booking request; it does not charge a payment method. Connect a payment provider and implement server-side payment verification before accepting real payments.
- Add rate limiting, email verification, password reset, logging, tests, and production secrets before deployment.
