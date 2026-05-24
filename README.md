# NepRide
“I am building a final-year project called NepRide AI, an intelligent ride-sharing and traffic analysis web application using MVC architecture. It includes real-time ride booking, driver-passenger tracking, AI-based traffic/demand prediction, voice assistant commands, and admin analytics dashboards.”
# NepRide AI 🚕

An intelligent ride-sharing and traffic analysis platform built for the Kathmandu Valley.
Final-year project using MVC architecture, real-time tracking, and AI-powered demand prediction.

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | React.js, Tailwind CSS, Chart.js |
| Backend | Node.js, Express.js, Socket.IO |
| Database | MongoDB Atlas (Mongoose) |
| AI/ML | Python, FastAPI, scikit-learn, Pandas |
| Maps | Google Maps JavaScript API |

## Project Structure

```
NepRideAI/
├── backend/        Node.js + Express MVC API
├── frontend/       React.js SPA
├── ml-service/     FastAPI + scikit-learn prediction service
└── docs/           Architecture diagrams, API specs, ERDs
```

## Quick Start

### Backend
```bash
cd backend
npm install
cp .env.example .env    # fill in your values
npm run dev             # starts on port 5000
```

### API Base URL
```
http://localhost:5000/api/v1
```

### Health check
```
GET http://localhost:5000/health
```

## API Endpoints

### Auth
| Method | Route | Access |
|---|---|---|
| POST | /api/v1/auth/register | Public |
| POST | /api/v1/auth/login | Public |
| POST | /api/v1/auth/refresh-token | Public |
| GET | /api/v1/auth/me | Protected |
| POST | /api/v1/auth/logout | Protected |

### Rides
| Method | Route | Access |
|---|---|---|
| POST | /api/v1/rides | Passenger |
| GET | /api/v1/rides | Passenger / Admin |
| GET | /api/v1/rides/:id | Protected |
| PATCH | /api/v1/rides/:id/accept | Driver |
| PATCH | /api/v1/rides/:id/status | Driver |
| PATCH | /api/v1/rides/:id/cancel | Passenger / Driver |

### Socket.IO Events
| Event | Direction | Description |
|---|---|---|
| `driver:available` | Client → Server | Driver goes online |
| `driver:locationUpdate` | Client → Server / Broadcast | GPS position |
| `ride:requested` | Server → Driver | New ride nearby |
| `ride:accepted` | Server → Passenger | Driver accepted |
| `ride:completed` | Server → Room | Ride ended |

## Running Tests
```bash
cd backend
npm test
```

## Build Phases
1. ✅ Project setup & MVC scaffolding
2. Auth & user management (JWT + roles)
3. Ride booking system
4. Real-time tracking (Socket.IO)
5. Dashboards (passenger, driver, admin)
6. AI/ML service (FastAPI)
7. Voice assistant (Web Speech API)
8. Polish, testing & deployment
