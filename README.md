<p align="center">
  <img src="https://github.com/user-attachments/assets/52b484c0-3e86-420a-a6c3-5402ed9606cd" alt="Sync Watch Studio preview" height="360" />
</p>

<h1 align="center">Sync Watch Studio</h1>

<p align="center">
  A desktop watch-party app for synchronized video playback, playlist viewing, and real-time chat with friends.
</p>

<p align="center">
  <a href="https://github.com/Ryukotsuki/SyncWatchStudio/releases"><img src="https://img.shields.io/github/v/release/Ryukotsuki/SyncWatchStudio?style=for-the-badge&label=Latest%20Release" alt="Latest release"></a>
  <a href="https://github.com/Ryukotsuki/SyncWatchStudio/releases"><img src="https://img.shields.io/github/downloads/Ryukotsuki/SyncWatchStudio/total?style=for-the-badge" alt="Downloads"></a>
  <a href="https://github.com/Ryukotsuki/SyncWatchStudio/stargazers"><img src="https://img.shields.io/github/stars/Ryukotsuki/SyncWatchStudio.svg?style=for-the-badge" alt="Stars"></a>
  <a href="https://github.com/Ryukotsuki/SyncWatchStudio/issues"><img src="https://img.shields.io/github/issues/Ryukotsuki/SyncWatchStudio.svg?style=for-the-badge" alt="Issues"></a>
</p>

---

## ✨ Features

- 🎥 **Synchronized Playback**  
  Keep viewers matched to the host's media, playback state, seek position, and stop events.

- 🌐 **Host and Join Sessions**  
  Create a room as host or join with a shareable WebSocket address.

- 🔒 **Tailscale-Friendly Networking**  
  Designed for private watch sessions without router port forwarding.

- ▶️ **Local Video Playback**  
  Plays local media through mpv and libmpv.

- 🌍 **Online Media Support**  
  Supports compatible online media through yt-dlp and FFmpeg tools.

- 💬 **Built-In Room Chat**  
  Chat with usernames, avatars, timestamps, emoji, GIF, and sticker support.

- 📃 **Playlist Viewing**  
  Queue local files or supported URLs for shared playback.

- 🎯 **Automatic Sync Correction**  
  Helps viewers recover when playback drifts from the host.

- 🎧 **Audio and Subtitle Preferences**  
  Configure preferred audio and subtitle languages.

- 🔄 **External Tool Management**  
  Can download or update required playback tools when needed.

---

## 📸 Preview

<p align="center">
  <img width="1920" height="1032" alt="Sync Watch Studio screenshot" src="https://github.com/user-attachments/assets/d9a87797-b051-4420-96dc-c713114e1f5f" />
</p>

---

## 🚀 Getting Started

### ⬇️ Download

Download the latest release from the [Releases page](https://github.com/Ryukotsuki/SyncWatchStudio/releases).

### ⚡ Quick Start

1. Download the latest release archive.
2. Extract it to a folder you can write to.
3. Run **Sync Watch Studio** from the extracted folder.
4. If prompted, allow the app to download missing external tools.
5. Restart the app if the tool setup asks you to.

---

## 🖥️ Hosting a Session

1. Open Sync Watch Studio.
2. Go to the `Settings` tab.
3. Set your username, room name, Tailscale host address, and port.
4. Go to the `Network` tab.
5. Click `Start as Host`.
6. Copy the generated address and send it to your viewers.
7. Open a local file, paste a media URL, or start a playlist item.

---

## 👥 Joining a Session

1. Open Sync Watch Studio.
2. Go to the `Settings` tab and set your username.
3. Go to the `Network` tab.
4. Paste the host address into the `Host address` field.
5. Click `Connect to Host`.

Once connected, viewers automatically follow the host's current media, playback state, seek position, and stop events.

---

## 📋 Requirements

- 🪟 Windows
- 🔒 Tailscale for remote private-network sessions

### 🧰 External Tools

Sync Watch Studio uses the following tools for playback and online media support:

- `mpv.exe`
- `libmpv-2.dll`
- `yt-dlp.exe`
- `ffmpeg.exe`
- `ffplay.exe`
- `ffprobe.exe`

The app can download missing external tools on startup. Bundled or downloaded tools are stored with the application files.

---

## 🔒 Tailscale Notes

Sync Watch Studio is designed to work well over Tailscale. Hosts and viewers should be connected to the same Tailscale network.

### For Hosts

- Use your Tailscale IPv4 address or device name in the app's Tailscale host setting.
- Keep the configured TCP port available.
- Allow inbound TCP traffic for Sync Watch Studio in Windows Firewall.
- If the preferred port is busy, share the alternate address shown by the app.

### For Viewers

Paste the exact address shown by the host, such as:

```text
ws://100.x.y.z:8765
```

---

## ⚙️ Configuration

User settings are saved locally with the application files.

Settings include:

- 👤 Username and avatar
- 🏠 Room name
- 🌐 Tailscale host address and port
- 🔤 Chat font size
- 🕒 Timestamp and join/leave visibility
- 🎧 Audio and subtitle language preferences
- 💬 Subtitle startup behavior

---

## 🛠 Troubleshooting

### ❌ External Tools Are Missing

- Use the in-app external tools download prompt.
- Delete incomplete files under `External/` and let the app download them again.

### ❌ Viewers Cannot Connect

- Make sure Tailscale is running on both devices.
- Confirm the host address was copied exactly from the app.
- Allow inbound TCP traffic through Windows Firewall.
- Confirm the host is still running and has not clicked `Stop Hosting`.

### ❌ Online Media Does Not Start

- Make sure yt-dlp is installed.
- Make sure FFmpeg is installed.
- Update both tools if the source website recently changed.

### ❌ Local Files Do Not Load for Viewers

When the host opens a local file, Sync Watch Studio serves it from the host machine through the session address.

- Confirm viewers can reach the host over Tailscale.
- Confirm the displayed port is allowed through Windows Firewall.

---

## 📜 License

Sync Watch Studio is licensed under the **GNU Lesser General Public License v3.0**.

See the `LICENSE` file for the full LGPLv3 license text.

---

## 💖 Support

If Sync Watch Studio helps you, a star on GitHub goes a long way.

- ⭐ Star the repository
- 🐛 Report bugs through [Issues](https://github.com/Ryukotsuki/SyncWatchStudio/issues)
- 💡 Suggest improvements or new features
- 💸 [Donate via PayPal](https://paypal.me/Ryukotsuki?country.x=US&locale.x=en_US)

### 💬 Community

Have questions, feedback, or ideas? Join the Discord:

<p align="center">
  <a href="https://discord.gg/HdfjKbPNc9">
    <img src="https://github.com/user-attachments/assets/09fb5822-5e82-431b-b9cc-bbd4111ba48b" alt="Join Discord" />
  </a>
</p>

---

<p align="center">
  Built for watch parties that stay in sync. ✨
</p>
