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
0-2. DONE. Setup (name, app ID, APK build), speed dialog, library/search/selection/exit menu item.
3. Easy playlists: Exit button on player screen + "Add to playlist" from selection (in progress).
4. Resume position per file + show current speed on the player screen.
5. Playlist management: rename, delete, reorder, remove a track.
6. A-B repeat loop on a track (riskiest: touches player timing).
7. Bookmarks inside a track, with optional note.
8. Smart grouping (artist/reciter/name); never assume tags exist, file name is the fallback.
9. Optional skip-silence (OFF by default; recitation pauses matter) + verify the existing sleep timer works.
10. Cleanup, permissions audit, icon, release v0.1.
After v0.1: appear in Android's Share / Open-with menu for audio.

Working rule for every phase: one branch, one PR, GitHub Actions must pass, wait for my approval, smallest change that works.

## After each phase
Tell me in 3 lines: what changed, what to test on my phone, any risk. Mention approximate token usage so I can track my $20 budget.

## BACKLOG: feature ideas from research, waiting for my choice
(empty for now)
