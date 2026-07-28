# Hush Chat

**A private, invite-only, end-to-end encrypted messenger for you and your friends** — built to stay private and *chat-control-proof*. Runs on **Android and Windows desktop** (a Linux build is planned; no iOS).

No phone number. No email harvesting. No ads. No data mining. Messages are end-to-end encrypted with the **Signal protocol** (X3DH + Double Ratchet), so no one in the middle — not even the server — can read them. The whole stack is **self-hosted**: your own server relays only ciphertext.

---

## 💬 Join the community

Questions, help, and release news live in our Discord:

**➡️ https://discord.gg/bfS674hZ**

---

## ✨ Features

### 💬 Messaging
- **Direct messages & group chats** — start a one-on-one or spin up a group.
- **Photos & files** 📷 — share images with captions and send E2EE file attachments.
- **Voice messages** 🎤 — record and send encrypted audio notes.
- **Reactions & replies** — react with emoji and reply to a specific message.
- **Edit & delete** — edit or delete your messages for everyone.
- **Forward** — pass a message along to another chat.
- **Search & pins** — search your messages and pin the important ones.
- **Typing indicators & receipts** — see typing, plus sent / delivered / seen.
- **Broadcast** — send one message to all your friends at once *(Supporter+)*.
- **Scheduled messages** — send later, or set a recurring Daily/Weekly message *(recurring is Supporter+)*.
- **Disappearing messages** — per-chat auto-delete: keep, 24h, or after-seen.
- **Archive & favourite** chats to keep your list tidy.

### 📞 Calls
- **1-on-1 voice calls** and **group voice calls** — a full peer-to-peer mesh so the server never hears the audio.
- End-to-end encrypted signaling over your **own self-hosted TURN/STUN**.
- Incoming-call ring (even when the app is closed), accept/decline screen, live participant grid, and mute / speaker / leave controls.
- **Pick your ringtone** from several options.

### 🔒 Privacy & security
- **Signal-protocol E2EE** on every message, with **contact verification** (safety number + QR).
- **Private push** — notifications even when the app is fully closed, through your own push channel (no Google/Firebase).
- **App lock** — PIN + biometric unlock, plus a registration lock.
- **Screenshot & screen-capture protection** on Android and Windows, with a consent flow.
- **Block users**, and **privacy toggles** to hide presence / last-seen and turn off read receipts and typing *(VIP+)*.
- **Your history stays on your device** — messages persist locally between restarts.
- **Encrypted cross-device backup & restore** of your private history.
- **Wipe chat** — clear for yourself, or wipe for everyone (with their consent).

### 🕵️ Stealth & duress
- **Decoy PIN** opens a harmless-looking version of the app.
- **Hidden chats** stay out of the main list.
- **Panic PIN / panic wipe** to clear sensitive data fast.

### 🎨 Profiles & personalization
- **Profiles** — avatar, display name and bio (E2EE), plus group avatar & description.
- **8 themes** — Cyber, Cute, Matrix, Hacker, Vaporwave, Blood, Midnight, and a clean Default.
- **Role perks** *(VIP+ / Supporter+)* — animated GIF avatar, coloured username & message accent, custom accent colour, profile banner, 50 MB file sharing, unlimited pins, and a custom Android app icon.

### 🛡️ Safety & moderation
- **Report a user, a group, or a specific message** — pick a reason, add a description, and attach evidence. Since screenshots are blocked, the offending message, image or **voice note** is captured automatically so staff can review (and play back) it.
- **Staff Manager** — a web dashboard to handle reports, manage users and invites, and set roles. Admins get a reduced, scoped view; the owner keeps full control.
- **Temporary bans** — ban for 1 hour up to permanent; the app shows the banned person how much time is left, and the ban lifts automatically.

### 🔔 Staying current
- **Automatic update checks** — the app checks for a newer version by itself (in the background or on pull-to-refresh) and prompts you when one is ready. The desktop app can update itself.
- **In-app Help & Tutorials** — a searchable guide that explains scheduled messages, hidden chats, decoy/panic PINs, disappearing messages, contact verification and every role perk, adapted to phone or desktop.

## 📦 Download

Get the latest **Android APK** and **Windows installer** (or portable zip) from the [Releases](../../releases) page.

- **Android:** download the APK and install it (you may need to allow installs from your browser/files).
- **Windows:** download `HushChat-Setup.exe` and run it — or grab the portable zip if you'd rather not install.

Then open the app, register with your **invite code**, pick a handle, and you're in.

## 🔒 A note on privacy & trust

Hush Chat is a private space for people who trust each other. **Only invite people you truly trust**, keep your invite codes to yourself, and don't share the app with strangers. Respect other people's privacy — don't screenshot or forward others' messages.

## 📄 License

[GNU GPL-3.0](LICENSE). Hush Chat's end-to-end encryption is built on [libsignal_protocol_dart](https://pub.dev/packages/libsignal_protocol_dart) (GPL-3.0), so the app as a whole is distributed under the GPL-3.0.
