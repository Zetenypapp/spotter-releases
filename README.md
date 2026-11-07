# Spotter

Race control for your F1® 25 league broadcast. Live race cards, timing, tyre strategy, driver pages and a stewards' log for free; the track map, telemetry, camera director and OBS overlays with Spotter Pro.

**[Download the latest version](https://github.com/Zetenypapp/spotter-releases/releases/latest)**: get `Spotter_x.y.z_x64-setup.exe` from the release.

## Quick start

### 1. Install

Run the setup file and follow the steps. No admin rights are needed.

Windows may say "Windows protected your PC", because Spotter is a new app. Click **More info**, then **Run anyway**.

On first start, Windows asks whether Spotter may use the network. Allow it on **private networks**: that's how the game's telemetry reaches Spotter, and how phones and OBS open its pages.

### 2. Turn on telemetry in F1 25

In the game: **Settings → Telemetry Settings**.

| Setting | Set it to |
| --- | --- |
| UDP Telemetry | On |
| UDP Broadcast Mode | Off |
| UDP IP Address | `127.0.0.1` if Spotter runs on the same PC; otherwise the Spotter PC's IP address |
| UDP Port | `20777` |
| UDP Send Rate | 60 Hz |
| UDP Format | 2025 |
| Your Telemetry | Public (so others in the lobby see your tyres and damage) |

Start any session. Spotter switches from "Waiting for telemetry" to the race within a second or two.

**Using SimHub too?** SimHub usually takes port 20777. In SimHub, forward the F1 25 data to another port (for example `20778`). Then in Spotter, **Settings → Open settings folder**, open `config.toml`, set `port = 20778` under `[udp]`, and restart Spotter.

### 3. Unlock Spotter Pro

After buying, your key arrives by email. In Spotter: **Settings → Spotter Pro**, paste the key, click **Use key**. Pro switches on straight away.

The key is checked online when Spotter starts, and keeps working for 14 days without internet. If a monthly key runs out, Pro switches off the next time Spotter starts, never during a race.

### 4. Your league's look

**Settings → Look**: choose your league's logo (PNG or JPEG) and team colour, and a light, dark or league theme.

### 5. Phones, tablets and OBS

- **Phone or tablet:** click **Share** in the menu and scan the QR code. Anyone on your network can follow the race in their browser.
- **OBS map overlay (Pro):** add a **Browser Source** with `http://localhost:8080/broadcast`. The map-building view is `http://localhost:8080/builder`.
- **Pop-out map (Pro):** open it from the Track map screen and add it to OBS with **Window Capture**. It keeps running with Spotter minimised.
- **OBS scene switching:** in `config.toml` (Settings → Open settings folder), fill in the `[obs]` section with your OBS WebSocket port and password, and set `enabled = true`.

### 6. Camera director (Pro)

In **Settings → Director**, set the keys your game uses to move the camera to the next and previous car, then switch the camera on. **Go** on a card cuts to that car; **Auto** follows the action by itself. Keep the game window in front: Spotter only presses your camera keys, and never while it has focus itself.

## Something not working?

| What you see | What to do |
| --- | --- |
| Stuck on "Waiting for telemetry" | Check UDP Telemetry is On and the IP and port match (step 2). If the game is on another PC, allow Spotter through Windows Firewall on private networks. |
| "Wrong UDP format" | Set UDP Format to 2025 in the game. |
| Spotter says the port is taken | Another program (often SimHub) has 20777. Forward from it to another port (step 2). |
| A driver's tyres and damage are blank | That driver has Your Telemetry set to Restricted. Only they can change it. |
| Your key isn't accepted | Check it's pasted whole, with the dashes. Each key works on a limited number of PCs; contact us to move it to a new one. |

Your settings, maps and key are kept in `%APPDATA%\Spotter`. Updating or uninstalling never removes them.

---

Spotter is not affiliated with or endorsed by Formula 1, the FIA, Codemasters or Electronic Arts. F1® 25 is a trademark of its respective owners.
