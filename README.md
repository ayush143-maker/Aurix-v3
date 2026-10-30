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

## Asset and loading review checklist

These are review actions, not verified results or performance measurements:

- [ ] Inspect image, audio, video, and font references in the relevant files under `src/` and `assets/`. Confirm local files exist at the paths used by the app, including any platform-specific references.
- [ ] Check that assets in `assets/` are still referenced and needed before removing them; search for uses across the app and configuration first.
- [ ] Review unusually large images, audio, or other media in relation to their intended display or playback. Consider a more suitable size or encoding where appropriate, and recheck quality and playback.
- [ ] Review external font, script, and other remote resource references in the app and configuration. Confirm each is intentional and necessary, and consider what the interface does if it is unavailable.
- [ ] Review loading and playback on the relevant Android or iOS development environment after asset changes; web review alone does not cover native behavior.

## Manual review checklist

These are actions to perform, not verified results:

- [ ] Start the app with `npm start` and open it in the relevant development environment. For native-specific changes, review on the corresponding Android or iOS development environment; web review is not a substitute for native review.
- [ ] Check the screens you changed and inspect referenced files under `assets/` for missing images or other media. If a path has changed, confirm its references match the new location.
- [ ] Try the interactions described by the screens you are reviewing, including player or library controls where present. Do not assume a music catalogue or streaming service is connected.
- [ ] Inspect the layout on a narrow phone-sized viewport and a wider viewport or device, and check that visible content and controls remain usable.

## Accessibility review checklist

These are future checks to perform on the relevant screens and platforms, not compliance claims or verified results:

- [ ] Use a hardware keyboard where supported to reach interactive controls, including player and library controls present on the screens under review. Check that keyboard order is sensible and controls can be operated without touch.
- [ ] Confirm keyboard focus is visibly indicated on interactive controls and remains distinguishable against each screen's background.
- [ ] Check that buttons, navigation items, player controls, and other interactive elements have meaningful accessible names; do not rely only on icons or visual context.
- [ ] Review text, icons, and control-state contrast against their backgrounds on the Android and iOS screens being reviewed.
- [ ] For album art or other meaningful images, check that an appropriate text alternative is available; identify decorative imagery so it is not announced as meaningful content.
- [ ] If transitions, animated artwork, or other motion are present, check how the app behaves with reduced-motion preferences enabled on each platform.

No review results are recorded here; complete the checklists in the relevant development environment after making changes.