<p align="center">
  <img src="https://github.com/user-attachments/assets/6e8bd922-a446-4b33-a184-e5e89493a4b1" alt="Sajda App Screenshot" width="720">
</p>

<h1 align="center">Sajda</h1>

<p align="center">
  A minimalist, native prayer times app for your Mac menu bar.
  <br />
  <a href="https://ikoshura.gumroad.com/l/sajda"><strong>Download</strong></a> &middot; <a href="https://github.com/ikoshura/Sajda/releases"><strong>Releases</strong></a> &middot; <a href="https://github.com/ikoshura/Sajda/issues"><strong>Report a Bug</strong></a>
</p>

---

## About

As a Muslim working on a Mac, I wanted a prayer app that felt as clean and calm as macOS itself. Many of the options available felt cluttered or didn't fit the native experience I was looking for.

Sajda is a simple and beautiful prayer times app for your menu bar. It delivers accurate schedules and gentle reminders directly on your desktop -- present when you need it, invisible when you don't. It helps you integrate moments of prayer into your day without distraction.

This project is fully open-source and built with SwiftUI. I made it to solve my own problem, and I hope you find it useful too.

---

## Features

### Native macOS Experience
- **Menu bar native** -- lives entirely in the menu bar, no dock icon, no clutter.
- **Light and dark mode** -- automatically adapts to your system appearance.
- **System accent color** -- highlights the next prayer using your Mac's own accent color, turning red when a prayer is imminent.
- **Polished onboarding** -- a guided welcome flow to get you set up in seconds.
- **Compact layout** -- optional narrower popover for smaller screens.

### Accurate Prayer Times
- **Automatic location** -- detects your location via macOS Location Services for precise times.
- **Manual location** -- search any city worldwide or paste latitude/longitude coordinates directly.
- **20 calculation methods** -- Muslim World League, ISNA, Umm al-Qura, Kemenag, Diyanet, JAKIM, Egyptian General Authority, and many more.
- **Hanafi madhhab** -- dedicated toggle for Hanafi Asr calculation.
- **Per-prayer time correction** -- adjust each of the five daily prayers individually, from -60 to +60 minutes, to match your local mosque.
- **Smart timezone handling** -- automatically resolves the correct timezone for any manually set location.
- **Optional Sunnah prayers** -- show or hide Tahajud and Dhuha times.

### Customizable Menu Bar
Choose what the menu bar displays:
| Mode | Example |
|------|---------|
| Icon only | A simple moon icon |
| Countdown | `Asr in 24m` |
| Exact time | `Maghrib at 6:05 PM` |
| Minimal | `Asr -2h 4m` |

Additional display options: 12-hour or 24-hour time format, and the ability to hide the icon when text is shown.

### Notifications and Sounds
- **Native macOS notifications** for each prayer time.
- **Three sound modes** -- default system beep, no sound, or a custom audio file of your choice.
- **Prayer timer alert** -- configurable break reminder that fires a set number of minutes after a prayer begins, with a dedicated alert window.

### System Integration
- **Launch at login** -- starts automatically and silently with your Mac.
- **Three languages** -- full localization for English, Arabic (with RTL support), and Indonesian.
- **Configurable animations** -- fade, slide, or instant transitions between views.

---

## Installation

**[Download Sajda Pro on Gumroad](https://ikoshura.gumroad.com/l/sajda)** or grab the latest build from the [Releases page](https://github.com/ikoshura/Sajda/releases).

### First-time launch

Because the app is distributed outside the Mac App Store, macOS will block it on first launch. The simplest fix: **right-click** the Sajda app in your Applications folder and select **Open**.

<details>
<summary><strong>Other methods (click to expand)</strong></summary>

#### Method 1: Right-click to open

1. Drag **Sajda** into your **Applications** folder.
2. Right-click (or Control-click) the app icon and select **Open**.
3. A warning dialog will appear with an **Open** button. Click it.

The app is now trusted and will open normally from this point on.

#### Method 2: System Settings

1. Double-click **Sajda**. A warning will appear -- click **OK**.
2. Open **System Settings > Privacy & Security**.
3. Scroll to the **Security** section. You'll see a message that Sajda was blocked.
4. Click **Open Anyway** and authenticate if prompted.

#### Method 3: Terminal

If the above methods don't work, remove the quarantine flag manually:

```
xattr -r -d com.apple.quarantine /Applications/Sajda.app
```

</details>

---

## System Requirements

- **macOS Ventura 13.0** or later
- **Apple Silicon** (M1, M2, etc.) and **Intel** Macs

Sajda was developed and tested on a 2012 MacBook Pro running Ventura via OpenCore Legacy Patcher. It is extremely lightweight and will not slow down your machine.

---

## Calculation Methods

Sajda supports 20 calculation methods covering regions worldwide:

| Method | Fajr / Isha angles |
|--------|-------------------|
| Muslim World League | 18° / 17° |
| ISNA (North America) | 15° / 15° |
| Umm al-Qura (Makkah) | 18.5° / 90 min |
| Egyptian General Authority | 19.5° / 17.5° |
| Kemenag (Indonesia) | 20° / 18° |
| JAKIM (Malaysia) | 20° / 18° |
| Diyanet (Turkey) | 18° / 17° |
| Karachi | 18° / 18° |
| Dubai | 18.2° / 18.2° |
| Kuwait | 18° / 17.5° |
| Qatar | 18° / 90 min |
| Singapore | 20° / 18° |
| Tehran | 17.7° / 14° |
| Moonsighting Committee | 18° / 18° |
| Algeria | 18° / 17° |
| France (12°) | 12° / 12° |
| France (18°) | 18° / 18° |
| Germany | 18° / 16.5° |
| Russia | 16° / 15° |
| Tunisia | 18° / 18° |

---

## Localization

| Language | Prayer names | UI | RTL |
|----------|-------------|-----|-----|
| English | Fajr, Dhuhr, Asr, Maghrib, Isha | Full | -- |
| Arabic | الفجر, الظهر, العصر, المغرب, العشاء | Full | Yes |
| Indonesian | Subuh, Zuhur, Asar, Magrib, Isya | Full | -- |

Contributions for additional languages are welcome.

---

## Security and Privacy

Sajda runs in a **macOS sandbox** with only four entitlements:

| Entitlement | Purpose |
|-------------|---------|
| `network.client` | Location search via OpenStreetMap Nominatim |
| `files.user-selected.read-only` | Custom adhan sound file selection |
| `personal-information.location` | Automatic prayer time calculation |
| `app-sandbox` | Sandboxed execution |

**No analytics, no tracking, no accounts, no cookies.** The only network call is to [OpenStreetMap Nominatim](https://nominatim.openstreetmap.org/) when you manually search for a city. No other data leaves your device.

A full security audit has been completed and all findings remediated. See [`SECURITY_AUDIT.md`](SECURITY_AUDIT.md) for the detailed report.

---

## Building from Source

1. Clone the repository:
   ```
   git clone https://github.com/ikoshura/Sajda.git
   ```
2. Open `Sajda.xcodeproj` in Xcode 15 or later.
3. Swift Package Manager will automatically resolve dependencies (`Adhan` and `NavigationStack`).
4. Build and run (Cmd+R).

---

## Contributing

Contributions are welcome. If you have a suggestion or bug fix, please fork the repo and open a pull request. You can also open an [issue](https://github.com/ikoshura/Sajda/issues) with the tag "enhancement."

---

## License

Distributed under the MIT License. See [`LICENSE`](LICENSE) for details.

---

## Acknowledgements

- [Adhan](https://github.com/batoulapps/Adhan) -- prayer time calculation engine.
- [FluidMenuBarExtra](https://github.com/lfroms/fluid-menu-bar-extra) -- dynamically resizing menu bar window.
- [NavigationStack](https://github.com/indieSoftware/NavigationStack) -- flexible view navigation system.
