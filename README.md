# Sync Watch Studio
<img height="440" alt="SyncWatchStudio" src="https://github.com/user-attachments/assets/52b484c0-3e86-420a-a6c3-5402ed9606cd" />

Sync Watch Studio is a desktop watch-party application for synchronized video playback, chat, and playlist-based viewing. It combines a PySide6 interface with mpv playback and WebSocket networking so a host and viewers can stay in sync while watching local files or supported online media together.

# Preview
<img width="1920" height="1032" alt="Screenshot 2026-06-18 175403" src="https://github.com/user-attachments/assets/f623f63e-7064-46fe-a739-a9e5dca000a1" />


## Features

- Synchronized playback between a host and connected viewers
- Host and join workflow using a shareable WebSocket address
- Tailscale-friendly networking for private watch sessions without router port forwarding
- Local video playback through mpv and libmpv
- Online media support through yt-dlp and FFmpeg tools
- Built-in room chat with usernames, avatars, timestamps, emoji, GIF, and sticker support
- Viewer list with host/viewer presence
- Playlist support for local files and URLs
- Automatic sync correction when viewers drift from the host
- Host seek buffering so viewers can catch up after major seek changes
- Audio and subtitle language preferences
- Optional automatic download/update flow for required external tools

## Requirements

- Windows
- Tailscale for remote private-network sessions

Sync Watch Studio also uses these external tools:

- `mpv.exe`
- `libmpv-2.dll`
- `yt-dlp.exe`
- `ffmpeg.exe`
- `ffplay.exe`
- `ffprobe.exe`

The app can download missing external tools on startup. Bundled or downloaded tools are stored with the application files.

## Installation

1. Download the latest Sync Watch Studio release from GitHub.
2. Extract the release archive to a folder you can write to.
3. Run Sync Watch Studio from the extracted folder.
4. If prompted, allow Sync Watch Studio to download missing external tools, then restart the app if requested.

## Quick Start

### Hosting a Session

1. Open Sync Watch Studio.
2. Go to the `Settings` tab.
3. Set your username, room name, Tailscale host address, and port.
4. Go to the `Network` tab.
5. Click `Start as Host`.
6. Copy the generated address and send it to your viewers.
7. Open a local video file, paste a media URL, or start a playlist item.

### Joining a Session

1. Open Sync Watch Studio.
2. Go to the `Settings` tab and set your username.
3. Go to the `Network` tab.
4. Paste the host address into the `Host address` field.
5. Click `Connect to Host`.

When connected, the viewer automatically follows the host's current media, playback state, seek position, and stop events.

## Tailscale Setup Notes

Sync Watch Studio is designed to work well over Tailscale. Both the host and viewers should be connected to the same Tailscale network.

For the host:

- Use your Tailscale IPv4 address or device name in the app's Tailscale host setting.
- Keep the configured TCP port available, or share the alternate address shown by the app if the preferred port is busy.
- Allow inbound TCP traffic for the Sync Watch Studio executable in Windows Firewall.

Viewers should paste the exact address shown by the host, such as:

```text
ws://100.x.y.z:8765
```

## Configuration

User settings are saved locally with the application files.

Settings include:

- Username and avatar
- Room name
- Tailscale host address and port
- Chat font size
- Timestamp and join/leave visibility
- Audio and subtitle language preferences
- Subtitle startup behavior

## Troubleshooting

### External Tools Are Missing

If playback is unavailable or the app reports missing tools, use the in-app external tools download prompt. You can also delete incomplete files under `External/` and let the app download them again.

### Viewers Cannot Connect

Check that:

- Tailscale is running on both devices.
- The host address was copied exactly from the app.
- Windows Firewall allows inbound TCP traffic on the displayed port.
- The host is still running and has not clicked `Stop Hosting`.

### Playback Does Not Start for Online Media

Online media support depends on yt-dlp and FFmpeg. Make sure the external tools are installed and up to date.

### Local Files Do Not Load for Viewers

When the host opens a local file, Sync Watch Studio serves it from the host machine so viewers can load it through the session address. If viewers cannot load the file, confirm that they can reach the host over Tailscale and that the displayed port is allowed by the firewall.

## License

Sync Watch Studio is licensed under the GNU Lesser General Public License v3.0.

See the `LICENSE` file for the full LGPLv3 license text.
