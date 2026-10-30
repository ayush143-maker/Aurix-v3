# Aurix-v3

Aurix-v3 is an Expo and React Native codebase for an Android and iOS music-listening app. The root entry files are `App.tsx` and `index.ts`; application navigation and provider structure are under `src/`. The project includes player and library state, native integrations, and supporting assets in `assets/`, with dependencies including React Navigation, React Native Track Player, local storage, and Expo notifications. This README does not establish a connected music catalogue or streaming service.

## Getting started

Install dependencies and start the Expo development server:

```sh
npm install
npm start
```

Platform commands are also available:

```sh
npm run android
npm run ios
npm run web
```

Android and iOS runs require the relevant native development tools and a compatible device or simulator. The web command targets the web build; it does not replace reviewing native playback.

## Personalize

For visible app content and presentation, inspect the relevant screens and components under `src/` and the supporting files in `assets/` before editing; the root listing does not identify individual screen or asset filenames. Keep existing asset references intact when moving or renaming files, and update every corresponding reference if a move is necessary.

For app-level identity or platform-specific settings, review the existing configuration in `app.json`, `eas.json`, and the platform files before changing them. Do not assume these files are interchangeable or edit service configuration without checking its purpose.

## Manual review checklist

These are actions to perform, not verified results:

- [ ] Start the app with `npm start` and open it in the relevant development environment. For native-specific changes, review on the corresponding Android or iOS development environment; web review is not a substitute for native review.
- [ ] Check the screens you changed and inspect referenced files under `assets/` for missing images or other media. If a path has changed, confirm its references match the new location.
- [ ] Try the interactions described by the screens you are reviewing, including player or library controls where present. Do not assume a music catalogue or streaming service is connected.
- [ ] Inspect the layout on a narrow phone-sized viewport and a wider viewport or device, and check that visible content and controls remain usable.

No review results are recorded here; complete the checklist in the relevant development environment after making changes.