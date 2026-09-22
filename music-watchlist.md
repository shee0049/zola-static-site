# Music Release Watchlist

This file drives the daily "New Music Releases" report on the Zola site
(`/reports/music/`). Add or remove a band name on its own line and the next
day's report will check for new/upcoming releases by them.

The list is seeded from the local FLAC/MP3 library (~/Music) plus Spotify
interests (the "New Noise: Noise Rock / Sludge / Punk / Post-Punk" playlist,
recently played). Edit freely — one band per line, plain names, no markup.

## Core watchlist (genre lanes)

### Hardcore / post-hardcore
Knocked Loose
Go It Alone
Speed
Drug Church
The Chisel

### Noise rock / sludge
Chat Pile
Geese
Windhand
Kowloon Walled City
Prostitute

### Post-punk / art-punk / post-rock
Viagra Boys
Home Front
DEADLETTER
Squid
Model/Actriz

### Indie / acoustic / spoken-word-punk
Front Porch Step

### Ancestry / classic acts still releasing
Nirvana
Black Sabbath
Refused
Misfits

### Rap / hip-hop
Eminem

## Notes for the report cron
- Always also scan the genre lanes above via bandcamp/punknews/Exclaim/Google
  News RSS for notable releases by *sibling* acts, not just exact name matches.
- "Interested" = noise rock, sludge, hardcore/post-hardcore, post-punk,
  indie/acoustic, plus rappers/classics that match the above.