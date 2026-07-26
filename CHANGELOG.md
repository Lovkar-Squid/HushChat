# Changelog

All notable changes to Hush Chat.

## v2.5.0
- **Voice calls** — tap the phone icon in a direct chat to start an end-to-end encrypted voice call. Media is DTLS-SRTP encrypted by WebRTC, and the call setup (SDP/ICE) travels *inside* the encrypted message envelope, so the server only relays it and never sees it. Runs over your own self-hosted TURN/STUN (coturn) — no third-party servers. Includes an incoming-call screen (accept/decline), in-call timer, mute, and speaker toggle.
- **Incoming calls ring even when the app is closed** — a high-priority "Incoming call" push (via your self-hosted ntfy) wakes the phone; tap it to answer.
- Works on Android and Windows desktop.

## v2.4.3
- **Fixed replies** — a reply now shows the message it's replying to (quoted) on both sides, instead of just saying "message". Reply/reaction targets now use the shared message id so they resolve on every device.
- **Fixed reactions** — reactions now attach to the correct message across devices.
- **Fixed chat lag** — history is saved with a debounce (rapid reactions/receipts/messages coalesce into one write) and the view only auto-scrolls on new messages, so reacting and scrolling stay smooth even with photos in the chat.

## v2.4.2
- **Desktop fix** — the conversation options panel (⋮ → mute / disappearing / clear chat / remove friend) now scrolls and is height-capped, so all options are reachable even when the window isn't maximized.

## v2.4.1
- **Clear-for-everyone is now inline** — instead of a system popup, the request appears as a card *inside the conversation* with **Yes / No** buttons right there. The asker sees a "waiting for everyone to agree" note in the same chat; once everyone accepts it clears for all, and a No cancels it for everyone.
- **Manager: connect two users as friends** — admins can pick any two people in the Manager (USERS → *Connect 2 as friends*) and link them so they can message each other, without either sending a request.
- **Remove friend** — a conversation's ⋮ menu now has *Remove friend* (unfriend), which clears the friendship on both sides.

## v2.4.0
- **Encrypted cross-device backup** — set a backup passphrase (Settings → *Chat Backup*) and your history is encrypted on-device (AES-256-GCM, PBKDF2) and stored on the server as ciphertext only. On another device, tap *Restore*, enter the same passphrase, and your chats come across. The server can never read them, and the passphrase never leaves your device.
- **Clear chat** — from a conversation's ⋮ menu: *Clear for me only* (removes it from this device) or *Clear for everyone* (sends a yes/no request — in a group everyone present must agree — and once accepted it's deleted for all sides).
- **Desktop auto-relaunch after update** — the installer now reopens Hush Chat automatically when a silent in-app update finishes.

## v2.3.0
- **Voice messages** — tap the mic in the composer to record, then send. Delivered end-to-end encrypted like everything else, with an in-bubble player and progress bar.
- **Reactions** — long-press any message to react with 👍 ❤️ 😂 😮 😢 🙏. Reactions ride *inside* the encrypted envelope, so the server never sees them.
- **Reply** — long-press → *Reply* to quote a specific message. Works for text, photos, and voice notes, in both direct and group chats.
- **Fix — "Delete after seen"** now waits until the recipient actually *leaves* the conversation, instead of vanishing the instant they open it.
- **Invite screen** now shows your role and how many invites you have left (with a Copy button).

## v2.2.0
- **New app icon** across phone and desktop.
- **Verify a contact** — compare a Signal safety number to confirm no one is intercepting the chat (open a chat → ⋮ → *Verify security code*).
- **Tap a photo to enlarge** it with pinch-to-zoom, plus a **download** button that saves to your gallery (phone) or Downloads (desktop).
- **No more constant "Listening for messages" notification** on Android — background delivery now runs purely through the private push channel.
- **Manager** shows a **Roles & Permissions** legend.
- Settings shows the current app version, and desktop Settings has a **Check for updates** button.

## v2.1.1
- **Desktop in-app updater** — the desktop app now downloads and installs updates itself, with a progress bar, then relaunches. No more manual download.

## v2.1.0
- **Mute conversations** — per person or group, for 15 min / 1 h / 8 h / 24 h, or until you turn it off. Muted chats stay silent everywhere (phone push, desktop beep + toast).
- **Disappearing messages** — per conversation: *Keep in chat*, *Delete after 24 hours*, or *Delete after seen*. The setting applies to everyone in the chat.
- **Photo preview before sending** — pick a photo and review it, then tap Send (no more instant send).
- **Desktop notification sounds** — choose Cryptic, Blip, Chime, Pulse, Ping, or Silent in Settings.
- Chat-list previews now show "📷 Photo" for images instead of raw data.

## v2.0.0
- **Real end-to-end encryption** — the Signal protocol (X3DH + Double Ratchet). The server only ever relays ciphertext; it can't read messages.
- **Send photos** — end-to-end encrypted images in direct and group chats.
- **8 themes** — Cyber, Cute, Matrix, Hacker, Vaporwave, Blood, Midnight, and Default.
- **In-app update alerts** — get notified when a newer version is available.
- **Windows desktop app** — with a system-tray icon and close-to-tray (keeps receiving in the background until you quit).
- **Private push notifications** when the app is fully closed — no Google/Firebase.
- Server address baked in and hidden from users; login persists across restarts.

## v1.0.0
- Initial release: invite-only accounts, direct and group messaging, friends, read receipts and presence, local message history, and a neon cyber theme.
