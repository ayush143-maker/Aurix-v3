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

For visible app content and presentation, inspect the relevant screens and components under `src/` and supporting files in `assets/` before editing; the root listing does not identify individual screen or asset filenames. Keep existing asset references intact when moving or renaming files, and update every corresponding reference if a move is necessary.

For app-level identity or platform-specific settings, review the existing configuration in `app.json`, `eas.json`, and the platform files before changing them. Do not assume these files are interchangeable or edit service configuration without checking its purpose.

## Configuration and data handling

The root file list includes `google-services.json` and a `supabase/` directory, but this README does not verify their contents or describe a configured service. Inspect their purpose and contents locally before changing, sharing, or deploying them; do not copy their values into documentation or examples. Treat tracked configuration as public. A configuration file shipped with a mobile or web client cannot protect values from users of that client. In particular, never bundle private keys, passwords, or privileged service credentials in the app. If a credential is found in a tracked file, remove or replace it and rotate it where applicable; deleting a value from the latest revision alone may not remove it from repository history.

No `.env.example` is listed in the repository root, and this README does not define environment-variable names or backend configuration. Do not assume or invent them. If you add a template, include placeholders only, explain its purpose, and keep real local credentials out of tracked files. Treat local app data as data on the user's device; do not place real sensitive information in test content or logs.

## Browser, platform, and asset review checklist

These are review actions, not verified results or performance measurements. No compatibility testing is recorded here.

- [ ] Start the project with `npm start`. For web changes, review the web experience in current browsers relevant to the intended audience. For native changes, review on the affected Android or iOS development environment; browser testing does not verify native behavior.
- [ ] In browser developer tools, inspect the Console and Network panel for errors, failed requests, and unexpected warnings. Check native logs or diagnostics in the relevant development environment when investigating native-only behavior.
- [ ] Inspect image, audio, video, and font references in `src/`, `assets/`, and relevant configuration. Confirm local paths match files in the project, including any platform-specific references. Verify remote resource URLs and consider what happens if a remote resource is unavailable.
- [ ] Check that assets in `assets/` are still referenced before removing them. Search their uses in source and configuration first.
- [ ] Compare a narrow phone-sized layout with a wider tablet or desktop-sized layout where supported. Check that content and controls remain readable and usable; also check the relevant native device layouts for native changes.
- [ ] Try the player or library controls present on the screens under review. Do not assume a music catalogue or streaming service is connected.
- [ ] Review configuration changes for accidental credentials or sensitive user data before committing. Check what values are bundled into client builds and treat them as visible to app users.

## Accessibility review checklist

These are future checks on relevant screens and platforms, not compliance claims or verified results:

- [ ] Use a hardware keyboard where supported to reach interactive controls and check keyboard order and operation.
- [ ] Check visible focus, meaningful accessible names, and text and control contrast on the screens under review.
- [ ] For meaningful images, check text alternatives; identify decorative imagery accordingly. If motion is present, check reduced-motion behavior on each relevant platform.

No review results are recorded here; complete the checks in the relevant development environment after making changes.