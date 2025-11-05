# Firebase Deployment Guide

## Prerequisites

- Node.js >= 18.0.0
- npm
- Firebase CLI (`npm install -g firebase-tools`)
- Firebase project set up in `firebase-project/.firebaserc`

## Setup

1. Install dependencies:
   ```bash
   npm install
   ```

2. Set up Firebase configuration:
   - Update `firebase-project/.firebaserc` with your Firebase project ID
   - Configure your Firebase config in environment variables (see below)

## Environment Variables

Create a `.env` file in the root directory with your Firebase configuration:

```env
VITE_APP_FIREBASE_CONFIG='{"apiKey":"...","authDomain":"...","projectId":"...","storageBucket":"...","messagingSenderId":"...","appId":"..."}'
```

## Development

Run the development server:

```bash
npm start
```

The app will be available at `http://localhost:3000`

## Build

Build the app for production:

```bash
npm run build
```

This will:
1. Build all packages
2. Build the app
3. Generate version information

The built files will be in `excalidraw-app/build/`

## Deploy to Firebase

1. Navigate to the firebase-project directory:
   ```bash
   cd firebase-project
   ```

2. Deploy:
   ```bash
   firebase deploy
   ```

   Or deploy only hosting:
   ```bash
   firebase deploy --only hosting
   ```

   Or deploy Firestore rules and Storage rules:
   ```bash
   firebase deploy --only firestore:rules,storage
   ```

## Project Structure

- `excalidraw-app/` - Main application
- `packages/` - Core packages (common, element, excalidraw, math, utils)
- `firebase-project/` - Firebase configuration and deployment files
- `public/` - Static assets

