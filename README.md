# Aurix-v3

Aurix-v3 is an Expo and React Native music-listening app for Android and iOS. It includes local library and player state, music discovery, downloads, and native integrations. Its YouTube Music discovery provider uses InnerTube. This does not establish official API status, authorization, or guaranteed availability; InnerTube behavior and configured endpoints may change or become unavailable.

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

## Navigation and source map

- `App.tsx` and `index.ts` — application entry files.
- `src/` — navigation, providers, screens, and other application source.
- `assets/` — project assets; preserve referenced paths when moving files.
- `package.json` — dependencies and declared scripts.
- `app.json` and `eas.json` — configuration to review before platform changes.
- `docs/` and `scripts/` — project documentation and scripts.

Navigation waits for library state to load, then routes to `Main` when profile setup is complete or `ProfileSetup` otherwise. `NowPlaying` is registered as a full-screen modal. The navigator comments on library detail screens nested under the Library tab, but those screens are not included in the supplied code.

## Discovery and playback

Home presents sections such as recent plays, favorites, trending, new releases, and recommendations. It fetches search and album sections through `MusicService.search()`; failed requests become empty sections. Recently Played and Your Favorites use local library state. Based on Your Listening searches using a top taste artist, a recently played artist, or a fallback query. Pull-to-refresh repeats the content fetches.

Search and metadata use InnerTube first, with configured endpoint fallbacks in some paths. Fallback behavior varies by operation and is not guaranteed. Search defaults to 20 results per category. Track and album selections can start playback with their results as the queue; collection results use the corresponding album, artist, or playlist lookup. Playlist expansion follows at most five continuation requests and returns up to 200 tracks by default. Continuation failures or empty pages return the tracks collected so far.

Search offers recent terms stored in AsyncStorage under `note_recent_searches`, deduplicated case-insensitively and limited to four. The local library search history separately keeps up to 12 queries and ignores terms shorter than two characters. Home and Search show a mini-player when a current track exists and provide add-to-playlist sheets on track rows.

Playback tries, in order, a registered local download, an HTTP(S) audio URL already on the track, the native stream source, and configured Invidious, Piped, or custom resolver endpoints. The endpoint list starts empty unless populated from user settings, so endpoint playback may not be available without configuration. Playback endpoint requests use a 10-second timeout and no retries. Other constraints, including region restrictions and source availability, can prevent a track from playing; `canPlay` is not a guarantee that resolution will succeed. The code does not establish that any provider or endpoint is official, authorized, or reliable.

## Library, downloads, and player

Library data is stored locally rather than in a remote account or database. It includes likes, playlists, recents, listening history, settings, search history, and saved playback position. Local bounds include 50 recently played tracks and 300 listening-history entries. Expiring stream URLs are stripped from persisted likes, playlists, recents, history, and download records.

Downloads are saved under the app’s document `downloads` directory and registered as local playback sources for offline use. On startup, records whose files no longer exist are discarded. Removing a download removes its record and unregisters the local source, and deletes the file when possible.

NowPlaying provides playback controls, seeking, shuffle and repeat, lyrics and queue views, likes, downloads, and playlist actions. Its queue sheet supports jumping to, removing, and reordering upcoming tracks. With no current track, NowPlaying renders nothing.

## Provider and configuration notes

`TrackResolver` defines a provider contract for search, stream resolution, metadata, and playlists, with optional related methods. `ProviderRegistry` stores providers and selects a resolver using a track’s provider ID. The YouTube Music discovery provider is implemented separately from stream playback; discovery or metadata working does not guarantee a playable stream.

The repository includes `google-services.json` and a `supabase/` directory, but their presence does not establish a configured service. Inspect them before changing or sharing them. Treat tracked configuration and values bundled into client builds as public; do not include private credentials. No `.env.example` or documented environment-variable names are listed. Review the relevant native target after changes; web preview does not verify Android or iOS behavior.