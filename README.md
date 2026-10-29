# Aurix-v3

An Expo and React Native mobile-app codebase with navigation, player and library providers, notification initialization, and React Native Track Player integration. The repository includes Android-related configuration.

## Run locally

Install dependencies with npm install and start Expo with npm start. Use npm run android for Android, npm run ios for iOS, or npm run web for the web target. Native targets require the relevant development toolchain.

## App organization

The project uses an Expo/React Native structure. The entry component initializes shared app services and providers; navigation, screens, hooks, and service modules should remain organized in the source tree.

## Device testing

After starting Expo, test the target platform on a physical device for playback, permission prompts, file access, and background behavior. Native modules may need a development build and platform tooling; a web preview cannot validate every mobile feature.
