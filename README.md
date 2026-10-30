# Aurix-v3

Aurix-v3 is an Expo and React Native codebase for an Android and iOS music-listening app. It includes navigation, player and library state, native integrations, and supporting assets, with dependencies including React Navigation, React Native Track Player, local storage, and Expo notifications.

## Getting started

Install dependencies and start the Expo development server:

    npm install
    npm start

Platform commands are also available:

    npm run android
    npm run ios
    npm run web

Android and iOS runs require the relevant native development tools and a compatible device or simulator. The web command targets the web build; it does not replace testing native playback.

## Working in the codebase

Start with `App.tsx` and `index.ts`, then follow the navigation and provider structure under `src/`. Keep playback, library, and notification behaviour within their existing boundaries.