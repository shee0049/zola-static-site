# Music Release Watchlist

This file drives the daily "New Music Releases" report on the Zola site
(`/reports/music/`). Add or remove a band name on its own line and the next
day's report will check for new/upcoming releases by them.

The list is seeded from the local FLAC/MP3 library (~/Music) plus Spotify
interests (the "New Noise: Noise Rock / Sludge / Punk / Post-Punk" playlist,
Liked Songs, saved albums, other playlists). Edit freely — one band per line,
plain names, no markup.

## Core watchlist (genre lanes)

### Hardcore / post-hardcore
Knocked Loose
Go It Alone
Speed
Drug Church
The Chisel
Crippling Alcoholism
Billy Talent

### Noise rock / sludge
Chat Pile
Geese
Windhand
Kowloon Walled City
Prostitute
Whores
DITZ
Lip Critic
My Wife's an Angel
Low Estate
Sprain
Drowse
King Woman
Ragana
Kayo Dot
Sannhet

### Post-punk / art-punk / post-rock
Viagra Boys
Home Front
DEADLETTER
Squid
Model/Actriz
IDLES
Have a Nice Life

### Indie / acoustic / punk
Front Porch Step
Jeff Rosenstock
Prince Daddy & the Hyena

### Ancestry / classic acts still releasing
Nirvana
Black Sabbath
Refused
Misfits
Danzig
Nine Inch Nails

### Rap / hip-hop
Eminem
Death Grips
Rage Against The Machine
Run The Jewels
Denzel Curry
KNEECAP
Joey Valence & Brae

## Notes for the report cron
- Always also scan the genre lanes above via bandcamp/punknews/Exclaim/Google
  News RSS for notable releases by *sibling* acts, not just exact name matches.
- "Interested" = noise rock, sludge, hardcore/post-hardcore, post-punk,
  indie/acoustic, plus rappers/classics that match the above.