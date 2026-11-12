# tuneder

Tinder for music, in a single HTML file. Swipe right to get more like a 30-second preview, left to skip. Swipe up for song info and Spotify / YouTube Music / Apple Music links. Swipe down to import or export your taste profile (max 5 MB).

Open `index.html` in a browser. There is no build step and no server. Taste data stays in your browser's localStorage.

## Taste engine
- Long-term profile: weights for artist, genre, genre family, decade and language.
- Short-term mood profile: decays quickly, so the current session steers the next songs.
- Graded feedback: how much of the preview you heard changes how strongly a like or skip counts.
- Adaptive exploration: the share of random songs and the pick temperature adjust to your recent hit rate.
- Diversity and novelty: recent artists and genres are penalised, and rarely seen features get an exploration bonus.
- Filters: tribute and cover tracks, disliked artists and disliked genres.

## Speed
- Leftover Apple tracks are cached in localStorage, so a repeat visit starts without waiting on the network.
- Song sources are fetched in parallel when the pool is low, and stalled requests time out after 5 seconds.
