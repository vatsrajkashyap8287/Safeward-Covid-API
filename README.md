# 🏥 SafeWard: COVID-19 Patient Management API

A REST API for doctors at government-designated COVID-19 hospitals to register patients, record test results, manage quarantine and track patient well-being, all in one place.

![Node.js](https://img.shields.io/badge/Node.js-339933?logo=nodedotjs&logoColor=white)
![Express](https://img.shields.io/badge/Express.js-000000?logo=express&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?logo=mongodb&logoColor=white)
![Swagger](https://img.shields.io/badge/Swagger-85EA2D?logo=swagger&logoColor=black)

---

## ⭐ Introduction

SafeWard helps hospitals handle the day-to-day workflow of COVID-19 patient care. Doctors can register and log in securely, add patients, create test reports and check patient status at any time. The goal is to keep records organised, reduce paperwork and help control the spread of the virus.

The API follows the **REST pattern** and ships with an interactive **Swagger UI**, so every endpoint can be tested right from the browser.

## ✨ Features

- 🔐 Secure doctor registration and login with **JWT authentication**
- 🧑‍⚕️ Patient registration and record management
- 🧪 Create and track COVID-19 test reports for each patient
- 🏷️ Filter reports by patient status (e.g. negative, quarantined, positive)
- 📖 Interactive API documentation with **Swagger UI**
- ♻️ Clean, modular code (routes, controllers, models)

## 🛠️ Tech Stack

| Layer          | Technology            |
| -------------- | --------------------- |
| Runtime        | Node.js               |
| Framework      | Express.js            |
| Database       | MongoDB + Mongoose    |
| Auth           | JSON Web Tokens (JWT) |
| API Docs       | Swagger UI            |
| Dev Tool       | Nodemon               |

## 🚀 Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (v18 or above)
- A [MongoDB Atlas](https://www.mongodb.com/atlas) account or a local MongoDB installation

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/vatsrajkashyap8287/Safeward-Covid-API.git

# 2. Go to the project folder
cd safeward-covid-api

# 3. Install dependencies
npm install
```

### Environment Variables

Create a `.env` file in the root folder (see `.env.example`):

```env
PORT=5000
DB_URL=your_mongodb_connection_string
JWT_Secret=your_jwt_secret
JWT_Expire=7d
```

| Variable     | Description                                      |
| ------------ | ------------------------------------------------ |
| `PORT`       | Port on which the server runs                    |
| `DB_URL`     | MongoDB connection string                        |
| `JWT_Secret` | Long random string used to sign tokens           |
| `JWT_Expire` | Token validity, e.g. `1d`, `7d`, `1h`            |

### Run the Server

```bash
# Development (auto-restart with nodemon)
npm run dev

# Production
npm start
```

The server will start at `http://localhost:5000`.

## 📖 API Documentation

Once the server is running, open the Swagger UI in your browser:

```
http://localhost:5000/api-docs
```

From there you can view all endpoints, request bodies and responses, and test them directly.

## 🔗 API Endpoints

<!-- Update these routes to match your project -->

| Method | Endpoint                          | Description                          | Auth |
| ------ | --------------------------------- | ------------------------------------ | ---- |
| POST   | `/doctors/register`               | Register a new doctor                | No   |
| POST   | `/doctors/login`                  | Login and receive a JWT token        | No   |
| POST   | `/patients/register`              | Register a patient                   | Yes  |
| POST   | `/patients/:id/create_report`     | Create a test report for a patient   | Yes  |
| GET    | `/patients/:id/all_reports`       | Get all reports of a patient         | Yes  |
| GET    | `/reports/:status`                | Get all reports by patient status    | Yes  |

Protected routes need this header:

```
Authorization: Bearer <your_token>
```

## 🔒 Security Notes

- Passwords are never stored in plain text
- Secrets live in `.env`, which is excluded from Git
- Protected routes are accessible only with a valid JWT

## 🔮 Future Improvements

- Quarantine room and bed allocation
- Role-based access (admin, doctor, staff)
- Pagination and search for patient records
- Docker support and deployment on a cloud platform

## 👨‍💻 Author

**Vats Raj Kashyap**

- GitHub: [vatsrajkashyap8287](https://github.com/vatsrajkashyap8287)

---

⭐ If you found this project useful, consider giving it a star!
