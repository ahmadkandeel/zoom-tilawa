# Zoom Tilawa — Project Brief

Fork of Gramophone (GPLv3). An ad-free, offline Android audio player focused on
fast listening: playback speed 1x/2x/3x/4x/5x. Audio only.

## Rules (non-negotiable)
- No ads, no analytics, no trackers. Do not add the INTERNET permission.
- Keep the GPLv3 license and credit to the original Gramophone project in the README.
- Keep pitch natural at all speeds (speed changes, pitch stays 1.0).
- Smallest change that works. No refactors, no new dependencies unless asked.
- Do NOT run local builds. GitHub Actions builds the APK; I test on my phone.
- Work on one branch per phase, open a PR, wait for my approval before merging.
- Read only the files you need. Do not explore the whole repo.
- The user is NOT technical: explain everything in plain language, give exact copy-paste commands, no jargon.

## Feature decisions
- Speed is GLOBAL: choose once (1/2/3/4/5x), it persists across tracks AND app restarts.
- Speed buttons live on the Now Playing screen.
- Library views: Folders, All tracks, Playlists. Fast search.
- Playlists: multi-select tracks -> add to new or existing playlist. Create playlist from a whole folder.

## Phases
0. Rename app to "Zoom Tilawa", change applicationId, set up GitHub Actions APK build.
1. Speed buttons + persistence + test at 5x.
2. Folder browsing + search + clear library layout.
3. Playlist workflow (multi-select, from folder).
4. Cleanup: permissions audit, icon, v0.1 release.

## After each phase
Tell me in 3 lines: what changed, what to test on my phone, any risk.
Mention approximate token usage so I can track the $20 budget.
- Default speed on first launch is 1x (normal). The 1x button must always be available to return to normal speed.
