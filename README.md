# Aurix-v3

Aurix-v3 is an Expo and React Native codebase for an Android and iOS music-listening app. Its root entry files are `index.ts` and `App.tsx`; navigation and provider structure are under `src/`. The project includes player and library state, native integrations, and supporting assets. Dependencies include React Navigation, React Native Track Player, local storage, and Expo notifications. This README does not establish a connected music catalogue or streaming service.

## Get started

Install dependencies and start the Expo development server:

```sh
npm install
npm start
```

Available platform commands:

```sh
npm run android
npm run ios
npm run web
```

Android and iOS runs require the relevant native development tools and a compatible device or simulator. The web target does not verify native playback behavior.

## Project files

- `App.tsx` and `index.ts` — application entry files.
- `src/` — navigation, providers, screens, and other application source.
- `assets/` — project assets; preserve referenced paths when moving files.
- `package.json` — dependencies and declared scripts.
- `app.json` and `eas.json` — configuration to review before making app or platform changes.
- `docs/` and `scripts/` — project documentation and scripts.

For visible content and presentation, locate the relevant screens and components under `src/` and assets under `assets/`. The repository overview does not identify individual screen or asset filenames.

## Configuration notes

The repository includes `google-services.json` and a `supabase/` directory, but their presence does not establish a configured service. Inspect their purpose before changing or sharing them. Treat tracked configuration and values bundled into client builds as public; do not include private credentials in the app. No `.env.example` or documented environment-variable names are listed.

Review the relevant target after changes: web preview does not verify Android or iOS behavior. In particular, do not infer that a catalogue or streaming service is connected from the player interface.