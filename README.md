# Aurix-v3

Aurix-v3 is an Expo and React Native codebase for an Android and iOS music-listening app. The project is organised around a mobile app entry point, navigation, player and library state, native integrations, and supporting assets. Its dependencies include React Navigation, React Native Track Player, local storage, and Expo notifications.

## Getting started

Install the dependencies and start the Expo development server:

    npm install
    npm start

The package also provides platform commands:

    npm run android
    npm run ios
    npm run web

Android and iOS runs require the relevant native development tools and a compatible device or simulator. The web command is useful for checking the web target, but it is not a substitute for testing native playback.

## Working in the codebase

Start with App.tsx and index.ts, then follow the navigation and provider structure under src/. Keep playback, library, and notification behaviour within their existing boundaries. Native-player changes should be tested on a real device as well as in the development environment.
