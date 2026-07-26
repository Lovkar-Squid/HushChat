# Changelog

All notable changes to Hush Chat.

## v2.7.3
- **Owner & admin can screenshot freely** — accounts with the owner or admin role are exempt from screenshot blocking: no secure flag, no consent prompt, no 15-second window. Everyone else stays screenshot-protected by default. The role is picked up on login and refreshed live, so a promotion takes effect without reinstalling.

## v2.7.2
- **Crash fix** — fixed a crash on launch/resume on some Android 14+ phones. The new screenshot-attempt detection needs the `DETECT_SCREEN_CAPTURE` permission, which wasn't declared; that call is now also wrapped so it can never crash the app if a ROM gates it. Screenshot blocking itself was unaffected.

## v2.7.1
- **Desktop screenshot protection** — the Windows app now blocks screenshots and screen-recording of its window by default (via `SetWindowDisplayAffinity` / `WDA_EXCLUDEFROMCAPTURE`), matching the phone. The same consent flow applies: use "Ask to screenshot" and, once the other person approves, the window becomes capturable for 15 seconds. (It can't stop a photo of the monitor, and there's no auto-detect of attempts on desktop — the request is manual.)

## v2.7.0
- **Photo/media captions** — type a message while a photo (or file) is staged and it's sent as a caption underneath the media, in one encrypted message.
- **Smoother images** — sent images no longer lag or flicker: media bytes are decoded once and reused instead of on every refresh.
- **Screenshots blocked by default** — the app is screenshot-protected out of the box (FLAG_SECURE), including in the recents switcher, with no setting to silently turn it off.
- **Screenshot consent + 15-second window** — to capture, tap "Ask to screenshot" (or, on Android 14+, your phone's screenshot attempt triggers it). The other person gets an inline Allow / Deny card; on Allow you get a 15-second window with a countdown, then it re-locks. No screenshot is possible without the other person's approval.
- **Add friends by exact handle only** — the add-friend search no longer reveals people from a couple of letters; you must know someone's exact handle to add them.

## v2.6.0
Messaging polish + a security pack.
- **Typing indicators** — see when the other person (or a group member) is typing, sent ephemerally inside the E2EE channel (never stored).
- **Edit & delete messages** — long-press your own message to edit it or delete it for everyone; edits show an "edited" tag and deletes leave a "message was deleted" placeholder on both sides.
- **Forward** — long-press any message to forward it to another chat or group; the content is re-encrypted to the new recipient.
- **File attachments** — send any file (PDF, docs, archives…) up to 20 MB, encrypted end-to-end like everything else; tap a received file to save & open it.
- **App lock** — optional PIN or biometric lock that hides the app on every resume. The PIN is stored only as a salted PBKDF2 hash.
- **Block screenshots** — Android FLAG_SECURE toggle that blocks screenshots/recording and hides the app in the recents switcher.
- **Block user** — stop all messages and calls between you and someone, in both directions; unblock any time.
- **Registration lock** — set a PIN that's required to link a *new* device to your account, so a stolen password alone can't hijack it.

## v2.5.0
- **Voice calls** — tap the phone icon in a direct chat to start an end-to-end encrypted voice call. Media is DTLS-SRTP encrypted by WebRTC, and the call setup (SDP/ICE) travels *inside* the encrypted message envelope, so the server only relays it and never sees it. Runs over your own self-hosted TURN/STUN (coturn) — no third-party servers. Includes an incoming-call screen (accept/decline), in-call timer, mute, and speaker toggle.
- **Incoming calls ring even when the app is closed** — a high-priority "Incoming call" push (via your self-hosted ntfy) wakes the phone; tap it to answer.
- **Safety numbers now match across devices** — the verification code (⋮ → Verify security code) is computed over *all* of a user's device identity keys, so it's identical on both sides even when someone uses more than one device (phone + desktop).
- **No stray empty bubbles** — control messages (call setup, reactions, wipe requests) are never drawn as blank message bubbles, including on desktop during a call.
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
