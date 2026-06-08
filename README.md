# klpt — turn presentations into pictures and text

> A quiet macOS app that captures slides and transcribes the speaker — entirely on your Mac.

**Preview build · WWDC 2026.** This repository hosts binary releases of klpt. It is **not** open source at this time; no source code is published here.

- Website · <https://klpt.app>
- Releases · <https://github.com/klptapp/macos/releases>
- Bugs · <https://github.com/klptapp/macos/issues>
- Contact · `beta@klpt.app`

---

## What klpt does

klpt watches your screen during a talk, captures slide changes as images, transcribes the speaker on-device, and assembles a clean, searchable record of the session.

- **Capture** — automatic, deduplicated slide images
- **Transcribe** — on-device speech recognition, aligned to slides
- **Recall** — searchable archive, copy fragments, export to Markdown

---

## What klpt does *not* do

- No accounts. No servers. No telemetry in this preview build.
- No data leaves your Mac. Verify with Little Snitch, Lulu, or `nettop`.
- No cloud sync. Your sessions live under `~/Library/Application Support/klpt`.

See the full [privacy policy](https://klpt.app/privacy.html) for details.

---

## Install

> ⚠️ **Pre-release software, provided AS IS with NO WARRANTY.** To the best of our knowledge it is not harmful, but it has not been independently audited and it is **not signed or notarized by Apple**. Users beware.

1. Download the latest `klpt-x.y.z.dmg` from [Releases](https://github.com/klptapp/macos/releases).
2. Open the `.dmg` and drag **klpt.app** into `/Applications`.
3. Because the build is unsigned, macOS Gatekeeper will block it on first launch. To open it:
   - In Finder, **right-click** `klpt.app` and choose **Open**.
   - Confirm the dialog that warns the developer cannot be verified.
   - After this one-time bypass, klpt opens normally from then on.
4. Grant **Screen Recording** and **Microphone** permissions when prompted (`System Settings → Privacy & Security`). klpt does not function without them.

### If macOS still refuses to open it

On recent macOS versions Gatekeeper may simply move the app to the Trash on the first attempt. Recover it from the Trash, then:

```sh
xattr -dr com.apple.quarantine /Applications/klpt.app
```

…and try the right-click → Open step again. This removes the quarantine attribute applied to downloads; it does not modify the app itself.

---

## System requirements

| Requirement | Detail                                       |
| ----------- | -------------------------------------------- |
| OS          | macOS 14 Sonoma or later                     |
| CPU         | Apple Silicon (M1 or later)                  |
| Disk        | ~250 MB free for on-device speech models     |
| Permissions | Screen Recording, Microphone                 |

Intel Macs are not supported in this preview.

---

## Quick start

1. Click the klpt icon in the menu bar.
2. Choose **Start session**, pick the screen showing the talk, and pick your audio input.
3. Sit back. klpt detects slide changes automatically and transcribes the room in the background.
4. Click **End session** when the talk finishes. Your session opens in the main window — slides on the left, aligned transcript on the right.
5. Use `⌘F` to search, drag a slide to copy as image, or **Export → Markdown** for the full record.

---

## Releases

Builds are published to [Releases](https://github.com/klptapp/macos/releases) as a notarization-free `.dmg`. Each release includes:

- `klpt-x.y.z.dmg` — the app
- `klpt-x.y.z.dmg.sha256` — checksum (verify with `shasum -a 256 -c`)
- Release notes describing what changed and what is still broken

There is no auto-updater in this preview. Check the Releases page manually.

---

## Reporting bugs

We want field reports from WWDC. The best ones include:

- macOS version and Mac model
- klpt version (visible in **klpt → About klpt**)
- What you were doing (which session, which slide, which moment in the audio)
- A screenshot or short screen recording if possible
- Whether the issue is reproducible

File at [github.com/klptapp/macos/issues](https://github.com/klptapp/macos/issues) or email `beta@klpt.app`.

When filing publicly, **do not paste confidential transcripts or screenshots of NDA content** — Apple's WWDC sessions are public, but your own work product is not. Redact before posting.

---

## Privacy at a glance

| Question                                     | Answer                                            |
| -------------------------------------------- | ------------------------------------------------- |
| Does klpt require an account?                | No.                                               |
| Does klpt send screen captures off the Mac?  | No.                                               |
| Does klpt send audio or transcripts anywhere?| No.                                               |
| Does klpt include analytics or telemetry?    | No (in this preview build).                       |
| Where is my data stored?                     | `~/Library/Application Support/klpt`              |
| How do I delete everything?                  | Delete that folder.                               |

Full policy: <https://klpt.app/privacy.html>.

---

## Legal

- This software is provided **AS IS, WITH NO WARRANTY** of any kind. See the [Terms of Service](https://klpt.app/terms.html).
- klpt is published by the **klpt partnership**, an unincorporated partnership operating informally during the preview period.
- "Apple" and "WWDC" are trademarks of Apple Inc. klpt is not affiliated with, sponsored by, or endorsed by Apple Inc.

---

© 2026 klpt partnership · `beta@klpt.app`
