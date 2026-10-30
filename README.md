# Aurix-v3

Aurix-v3 is an Expo and React Native codebase for an Android and iOS music-listening app. The root entry files are `App.tsx` and `index.ts`; application navigation and provider structure are under `src/`. The project also includes player and library state, native integrations, and supporting assets in `assets/`, with dependencies including React Navigation, React Native Track Player, local storage, and Expo notifications. The README does not establish a connected music catalogue or streaming service.

## Getting started

Install dependencies and start the Expo development server:

    npm install
    npm start

Platform commands are also available:

    npm run android
    npm run ios
    npm run web

Android and iOS runs require the relevant native development tools and a compatible device or simulator. The web command targets the web build; it does not replace reviewing native playback. The repository includes `app.json` and `eas.json`, but this README does not document a production build or deployment procedure.

## Working and reviewing changes

Start with `App.tsx` and `index.ts`, then follow the navigation and provider structure under `src/`. Keep playback, library, and notification behaviour within their existing boundaries. After a change, use `npm start` and review it in the relevant development environment; use the Android or iOS command when reviewing native-specific changes. If a platform command fails, check that its required native development tools and a compatible device or simulator are available.