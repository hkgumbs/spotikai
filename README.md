Shuffle liked songs on Spotify (via [librespot](https://github.com/librespot-org/librespot)) to any browser that supports `<audio>`.
I created this initially to stream Spotify on my KaiOS feature phone.
It works... it's just not very usable ¯\_(ツ)_/¯

## Quick Start

```
git submodule update --init
npm install
cargo build --manifest-path librespot/Cargo.toml
SPOTIFY_CLIENT_ID=$SPOTIFY_CLIENT_ID \
  SPOTIFY_CLIENT_SECRET=$SPOTIFY_CLIENT_SECRET \
  npm run start:debug
```

## TODO

- Show something on the screen... anything...
- Playback contols—not sure how this would work since librespot seems to get pretty far ahead of Spotify Connect
- Stream PCM frames directly via WebSockets to avoid MP3 overhead and volatile connection
- Server should be in Rust and implement [Sink](https://docs.rs/librespot-playback/0.1.3/librespot_playback/audio_backend/trait.Sink.html) directly without subprocess overhead
