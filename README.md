# FH2 Streaming Radio

![FH2 Streaming Radio](assets/banner.png)

A mod for **Forza Horizon 2 (Azimuth builds)** that takes over an in-game radio station, which is **XS Radio** by default, and plays your own music on it. Pick "Forza Horizon 2" from the Spotify devices list on any device on your network, including your computer, and whatever you play comes out of that station. When Spotify isn't connected, the station shuffles your own songs from the `MUSIC` folder.

Spotify streaming requires Spotify Premium, since Spotify only allows Connect speakers on Premium. Local music works without Premium and offline. Not affiliated with Spotify or Microsoft.

> [!NOTE]
> **Experimental (v0.1.2+):** the mod now mutes the DJ on your takeover station only (`mute_dj = true`), so you can leave the game's **DJ Voice** setting ON and keep DJs on the other stations. If the DJ still talks over your music, turn **OFF Radio DJ** in the game's **Audio settings**.

## Install

1. Download the latest zip from [Releases](../../releases).
2. Copy `D3DCompiler_47.dll` and the `spotify-radio` folder into your Azimuth folder, so that both the `D3DCompiler_47.dll` and the `spotify-radio` folder are next to `Azimuth.exe`.
3. Launch the game. When Windows asks, allow `Azimuth.exe` to use **Private networks**. In fullscreen, that prompt can hide behind the game, so Alt+Tab to it.
4. On any device with Spotify that's on the same network as the game PC, like your phone, a tablet, or the Spotify app on your computer, open the devices list and pick **Forza Horizon 2**. Then play something.
5. Leave the game's DJ Voice setting on. The mod mutes the DJ on your station only (experimental). If the DJ still talks over your music, turn **OFF Radio DJ** in the in-game **Audio settings**.
6. In-game, switch the radio to **XS Radio**, or whichever station you picked in the config.

After the first time, your login is saved and the game shows up in Spotify automatically whenever it's running.

## Local music

Drop your songs into `spotify-radio\MUSIC`. MP3, FLAC, OGG, WAV, and M4A files all work, and sub-folders are fine. Whenever Spotify isn't connected, they play on shuffle on the takeover station. Spotify can connect at any time, and if it disconnects, your local music picks back up. No song repeats until the whole shuffle has played, even across game sessions. If your local songs are louder or quieter than other stations, adjust `local_boost_db` in `config.ini`. Set `local_music = false` to turn local music off.

## Picking a different station

Set `station =` in `spotify-radio\config.ini` to a station's number or name, for example `station = Innovative Leisure` or `station = Ninja Tune`. The stations are Horizon Pulse (1), Bass Arena (2), Horizon XS (3, the default), Radio Levante (4), Hospital Records (5), Ninja Tune (6), and Innovative Leisure (7).

## Other settings

Edit `spotify-radio\config.ini` while the game is closed. You can change the device name, icon, bitrate, starting volume, and more. `boost_db` (0 to 12, default 5) raises the station's overall volume, and `replace_logo = false` keeps the station's original logo. To use your own logo, put `logo.png` or `logo.jpg` in `spotify-radio` (about 2:1, ideally 392x192 or 784x384). By default the music pauses when you leave the station or hit a menu and resumes where it left off; set `pause_when_silent = false` for live-radio behavior.

## Skip songs from your controller

Hold **LB + X** to skip to the next song (Spotify or local music). It works while the game is in front and playing your station. Change the buttons with `skip_combo` in `config.ini` (two or more of `A B X Y LB RB LT RT Back Start LS RS Up Down Left Right`, joined with `+`), or set `skip_combo = off` to disable it.

## Troubleshooting

- Check `spotify-radio\spotify-radio.log`.
- Set `test_tone = true` in `config.ini` to hear a beep on the station instead of music, which tests the game side by itself.
- If your Spotify device doesn't see Forza Horizon 2, make sure it's on the same network as the game PC and the network permission was allowed.
- To forget your Spotify login, delete `spotify-radio\cache`.

## Uninstall

Delete `D3DCompiler_47.dll` and the `spotify-radio` folder, or set `enabled = false` in `config.ini`.

## Credits

Built with [librespot](https://github.com/librespot-org/librespot) (MIT). See `THIRD-PARTY-LICENSES.txt`.
