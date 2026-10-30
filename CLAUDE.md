# Zoom Tilawa - Project Brief

Fork of Gramophone (GPLv3). An ad-free, offline Android audio player focused on fast listening: playback speed 1x/2x/3x/4x/5x. Audio only.

## Rules (non-negotiable)
- No ads, no analytics, no trackers. Do not add the INTERNET permission.
- Keep the GPLv3 license and credit to the original Gramophone project in the README.
- Keep pitch natural at all speeds (speed changes, pitch stays 1.0).
- Smallest change that works. No refactors, no new dependencies unless asked.
- Do NOT run local builds. GitHub Actions builds the APK; I test on my phone.
- Work on one branch per phase, open a PR on MY repo (ahmadkandeel/zoom-tilawa) only, never on the upstream Gramophone repo. Wait for my approval before merging.
- Read only the files you need. Do not explore the whole repo.
- The user is NOT technical: explain everything in plain language, give exact copy-paste commands, no jargon.

## Feature decisions
- Speed is GLOBAL: choose once (1x/2x/3x/4x/5x), it persists across tracks AND app restarts.
- Default speed on first launch is 1x (normal). The 1x button must always be available.
- Speed buttons live on the Now Playing screen.
- Tempo and pitch are INDEPENDENT. "Lock tempo and pitch" is OFF by default. Locking them together makes fast audio sound like a child, so it must never be the default.
- Library views: Folders, All tracks, Playlists. Fast search.
- Playlists: multi-select tracks, then add to a new or existing playlist. Create a playlist from a whole folder.

## User library facts
- Files are NOT organized in any fixed folder structure.
- Some files have tags (title, artist/reciter); some do NOT (the user's own voice recordings, files downloaded from the web). So NEVER depend on tags alone, and NEVER ignore tags either: use ALL available info together (tags + file name + folder), and when a tag is missing fall back to the file name.
- A playlist holds at most 114 tracks, so no performance concern.
- Principle: the user wants MORE THAN ONE way to organize and find files (by tags, by file name, by folder, by date added, and by manual playlists). Do not remove or replace one with another.
- Priority: building a playlist and adding to a playlist must be very easy (few taps).

## Phases
0. DONE. Rename app to "Zoom Tilawa", change applicationId, set up GitHub Actions APK build.
1. DONE. Playback-speed dialog overhaul + disable StrictMode dialog in debug builds + fixed debug signing key.
2. Library + search + exit button.
3. Easy custom playlists (multi-select, add to new/existing, create from whole folder).
4. Smart grouping by artist/reciter (depends on file tags; fall back to folder/file name; test on my real files first).
5. Cleanup, permissions audit, icon, v0.1 release.
AFTER v0.1 (backlog): appear in Android's Share / "Open with" menu for audio files.

## After each phase
Tell me in 3 lines: what changed, what to test on my phone, any risk. Mention approximate token usage so I can track my $20 budget.
