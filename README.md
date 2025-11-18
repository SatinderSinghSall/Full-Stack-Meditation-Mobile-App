# 🧘‍♂️ Meditation and Affirmations App

Welcome to the **Meditation and Affirmations App**, a full-stack mobile application designed to help users relax, meditate, and improve their mental well-being through guided audio sessions and positive affirmations.

This app is built with **React Native (Expo)** on the frontend, and **Node.js + Express** on the backend. It features user authentication, meditation sessions, affirmation galleries, and much more.

---

## 📚 Table of Contents

1. [Introduction](#introduction)
2. [Tech Stack](#tech-stack)
3. [Project Structure](#project-structure)
4. [Backend Setup](#backend-setup)
5. [Frontend Setup](#frontend-setup)
6. [API Documentation](#api-documentation)
7. [Available Screens](#available-screens)
8. [State Management](#state-management)
9. [How to Run Locally](#how-to-run-locally)
10. [Future Roadmap](#future-roadmap)
11. [Author](#author)

---

## <a name="introduction">🤖 Introduction</a>

The Meditation and Affirmations App provides a calming and immersive experience through soothing meditation audio and picturesque affirmation visualizations. Whether you're new to meditation or an experienced practitioner, this app offers a simple way to focus on your mental health.

> "Relax your mind. Breathe. Focus."

---

## <a name="tech-stack">⚙️ Tech Stack</a>

### Frontend (Mobile)

- React Native
- Expo
- TypeScript
- NativeWind (Tailwind CSS)
- Expo Router
- Context API
- Expo AV

### Backend

- Node.js
- Express
- MongoDB (Mongoose)
- JWT Authentication
- bcrypt.js

---

## <a name="project-structure">📂 Project Structure</a>

```
Meditation App/
├── backend/
│   ├── config/
│   ├── routes/
│   ├── models/
│   └── index.js
└── frontend/
    ├── app/
    ├── components/
    ├── constants/
    ├── context/
    ├── assets/
    └── App.js
```

### Key Architecture Decisions

- Modular folder structure for scalability.
- Shared assets and reusable components.
- TypeScript models to enforce strong typing.

---

## <a name="backend-setup">🔧 Backend Setup</a>

### Features

- User Authentication (Register/Login)
- Protected Routes with JWT
- Meditation and Affirmation Endpoints

### Install Dependencies

```bash
cd backend
npm install
```

### Environment Variables (`.env`)

```
MONGO_URI=<your_mongodb_connection_string>
JWT_SECRET=<your_jwt_secret_key>
PORT=5000
```

### Run Server

```bash
npm start
```

### File Overview

- `config/db.js`: Database connection logic
- `middleware/auth.js`: JWT auth middleware
- `routes/authRoutes.js`: Handles user auth
- `routes/meditationRoutes.js`: Returns meditation data

---

## <a name="frontend-setup">📱 Frontend Setup</a>

### Features

- Onboarding Screen with Gradient Background
- Meditation List with FlatList
- Audio Playback with Meditation Timer
- Tab Navigation for Meditation and Affirmations
- Modal Screen for Custom Duration
- Responsive UI with NativeWind

### Install Dependencies

```bash
cd frontend
npm install
```

### Run App

```bash
npx expo start --clear
```

Scan the QR code using the Expo Go app (iOS or Android).

### Important Files

- `app/`: File-based routing logic
- `components/`: Reusable UI components
- `constants/`: Static data like colors, meditation/affirmation lists
- `context/TimerContext.tsx`: Provides countdown timer via React Context

---

## <a name="api-documentation">📡 API Documentation</a>

Base URL: `http://localhost:5000/api`

### 🔐 Auth Routes

#### POST `/auth/signup`

Create a new user

> Request Body

```
{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "123456"
}
```

> Response

```
{
  "_id": "64d12345ab12cd34",
  "name": "John Doe",
  "email": "john@example.com",
  "token": "jwt_token_here"
}
```

#### POST `/auth/login`

Authenticate a user

> Request Body

```
{
  "email": "john@example.com",
  "password": "123456"
}
```

> Response

```
{
  "_id": "64d12345ab12cd34",
  "name": "John Doe",
  "token": "jwt_token_here"
}
```

---

### 🧘 Meditation Routes

#### GET `/meditations`

Fetch all meditation sessions (requires token)

> Response

```
[
  {
    "id": 1,
    "title": "Relax by the River",
    "duration": "5 min",
    "audio": "river.mp3",
    "image": "river.webp"
  },
  ...
]
```

---

## <a name="available-screens">📱 Available Screens</a>

| Screen            | Description                                   |
| ----------------- | --------------------------------------------- |
| Onboarding        | Welcome with branding and start button        |
| Login / Signup    | User authentication pages                     |
| Meditation List   | Scrollable list of guided meditations         |
| Meditation Player | Audio player with timer and controls          |
| Affirmations      | Gallery of affirmation categories and visuals |
| Profile           | User details (in progress)                    |

---

## <a name="state-management">🧠 State Management</a>

The frontend uses React Context for managing shared global state:

- **TimerContext** → Manages meditation duration and countdown

> Example usage:

```tsx
const { minutesLeft, setDuration } = useContext(TimerContext);
```

---

## <a name="how-to-run-locally">🏃 How to Run Locally</a>

1. Clone the repository:

```bash
git clone https://github.com/SatinderSinghSall/Meditation-Mobile-App.git
```

2. Setup backend (see [Backend Setup](#backend-setup))
3. Setup frontend (see [Frontend Setup](#frontend-setup))
4. Start both servers and the app

> Make sure the backend is running on port 5000 or update `api.ts` accordingly.

---

## <a name="future-roadmap">🚀 Future Roadmap</a>

- Add push notifications for practice reminders
- More meditation tracks and personalized playlists
- Full profile customization with streak tracking
- Dark mode
- Option to download sessions for offline use

---

## <a name="author">👨‍💻 Author</a>

Built with ❤️ by **[Satinder Singh Sall](https://satinder-portfolio.vercel.app/)**

📧 Email: [satinderssall@gmail.com](mailto:satinderssall@gmail.com)

---

Feel free to open an issue or submit a pull request if you'd like to contribute!
