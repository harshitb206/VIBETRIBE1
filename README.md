# VibeTribe

VibeTribe is a modern, personality-driven social discovery platform designed to help individuals find their "tribe." By moving beyond traditional bios and focusing on shared "vibes," moods, and lifestyle preferences, the app fosters genuine connections in a playful, secure environment.

## 🚀 Overview

The application is built with **React** and **Vite**, utilizing **Firebase** for real-time authentication, database management, and chat functionality. It features a responsive design styled with **Tailwind CSS**, offering a seamless experience from landing to discovery.

## ✨ Key Features

* **Dynamic Landing Page**: A high-conversion introduction featuring smooth scroll animations and an integrated contact system.
* **Vibe-Based Discovery**: Users are matched based on shared interests ("vibes") such as "Quirky," "Creative," or "Chaotic," rather than just geographical proximity.
* **Intelligent Matching Logic**: A custom matching engine that filters profiles based on age range, gender preference, schedule (e.g., Early Bird vs. Night Owl), and pet friendliness.
* **Real-time Chat**: Instant communication with "VibeMates" powered by Firebase Firestore's real-time listeners.
* **Geolocation Services**: Optional location sharing using the Haversine formula to calculate distance between users.
* **Privacy & Control**: Comprehensive account management tools including profile deactivation (soft delete) and permanent account deletion.

## 🛠️ Tech Stack

* **Frontend**: React 18, Tailwind CSS, PostCSS
* **Build Tool**: Vite
* **Backend as a Service**: Firebase (Authentication, Firestore)
* **State Management**: React Hooks (Custom `useAuth` hook)

## 📂 Project Structure

```text
src/
├── components/       # Reusable UI components (Auth, Profile, Spinners)
├── firebase/         # Firebase configuration and initialization
├── hooks/            # Custom hooks for authentication state
├── pages/            # Main application views (Landing, Dashboard, Profile)
├── utils/            # Core matching logic and distance calculations
└── App.jsx           # Main routing and global state controller

```

## ⚙️ Core Logic

### Matching Engine

The matching algorithm uses a `collectionGroup` query to find users sharing at least one vibe with the current user. It then applies client-side filtering for:

* **Age Limits**: 18 to 60 years.
* **Vibe Score**: Minimum compatibility thresholds.
* **Geospatial Distance**: KM-based proximity via the Haversine formula.

### Authentication Flow

The app handles three distinct states for a secure onboarding experience:

1. **Unauthenticated**: Directed to the Landing Page.
2. **Authenticated (No Profile)**: Directed to the Profile Creation flow.
3. **Authenticated (Profile Complete)**: Access to the Discovery Dashboard.

## 🛠️ Getting Started

### Prerequisites

* Node.js (v18 or higher)
* Firebase Project Credentials

### Installation

1. Clone the repository.
2. Install dependencies:
```bash
npm install

```


3. Set up your `.env` with Firebase credentials (see `src/firebase/firebaseConfig.js`).
4. Start the development server:
```bash
npm run dev

```



## 📜 Scripts

* `npm run dev`: Starts the Vite development server.
* `npm run build`: Generates a production-ready build.
* `npm run lint`: Runs ESLint for code quality.
