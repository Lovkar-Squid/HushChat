# Hush Chat

**A self-hosted, invite-only, end-to-end encrypted messenger for you and your friends** — built to stay private and *chat-control-proof*. Runs on **Windows, Linux, and Android** (no iOS).

Your server stores only ciphertext and public keys — a zero-knowledge relay. No phone number, no email harvesting, no ads, no data mining.

---

## ✨ Features

- **Invite-only** — no open sign-ups. New accounts need an invite code from an existing member.
- **Friend system** (Discord-style) — add by handle → request → accept. You only see your friends, not every user.
- **Direct messages + group chats** with live delivery (messages, friends, and groups appear without reopening the app).
- **Read receipts** — sent ✓ / delivered ✓✓ / seen, plus online + last-seen presence.
- **Roles** — Owner, Admin, Moderator, VIP, Member, with per-role invite quotas.
- **Push notifications when the app is closed** via **self-hosted UnifiedPush + ntfy** — no Google, no Firebase.
- **Local message history** that survives restarts.
- **Web admin dashboard ("Manager")** — manage users, invites (incl. role-granting codes), passwords, roles, bans, and groups.
- **Themes** — including a neon cyber look.
- **WAN access** over your own domain with HTTPS (Let's Encrypt).

## 🧩 Stack

- **Client:** Flutter (Android + Windows/Linux desktop)
- **Backend:** FastAPI + PostgreSQL, WebSocket relay
- **Push:** self-hosted [ntfy](https://ntfy.sh) via UnifiedPush
- Deployed as a container app on a home server.

## 📦 Downloads

Grab the latest **Android APK** and **Windows installer** from the [Releases](../../releases) page.

> Hush Chat is for private use among people who trust each other. Only invite people you truly trust, and never share the app or your invite codes with strangers.

## 📜 License

MIT.
