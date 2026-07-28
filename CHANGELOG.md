# Changelog

All notable changes to Hush Chat. Newest first.

## v2.14.2

- **Reporting a voice message** now attaches the audio itself, so staff can play it back in the Manager (images were already attached this way). Reported voice notes show up as an audio player on the report card.
- **Security hardening (server):** report evidence is now strictly validated to be an image/audio data URL before it's stored, and the Manager only renders evidence that passes the same check — closing a stored-XSS path where a crafted report could have run code in the Manager. Usernames are also restricted to a safe character set at registration.
- **More server hardening (audit follow-up):** login, staff (Manager) login, and the registration-lock PIN are now rate-limited (a short cool-down after 10 wrong tries per account) to stop password/PIN brute-forcing; a request body-size ceiling was added to block oversized-payload abuse. These are server-side only — no app update needed. A full authorization/injection/IDOR sweep found no other exploitable issues.
- **Manager: log out** — a Log out button in the Manager header clears the saved key/session and returns to the sign-in screen.
- **Fix — deleting a group in the Manager** returned HTTP 500 when the group had an active invite (or ban). Group deletion now clears the group's invites, bans, and retention/mute leftovers first, so it always succeeds.
- **Manager hardened for public access:** wrong admin-key guesses are now rate-limited (previously unlimited), the key is compared in constant time, Manager sign-ins expire after 12 hours instead of 30 days, banned staff can no longer sign in, and the dashboard sends strict security headers (CSP, anti-framing, no-referrer, no-index). The rate limit deliberately can't be side-stepped by forging forwarded-IP headers, and a correct key is never locked out by someone else's guessing.
- **Manager two-factor authentication (TOTP)** — the dashboard can now require a 6-digit code from an authenticator app (Google Authenticator, Authy…) on top of the owner key or staff password. With 2FA on, the key by itself no longer opens anything: it must be exchanged together with a code for a short-lived session. Long-lived phone app tokens can no longer be used to reach the Manager either, so 2FA can't be side-stepped.
- **More hardening:** cross-origin browser access is now an explicit allow-list instead of "any site" (native apps are unaffected), and group avatars and encrypted backups have size ceilings so they can't be used to fill the server's disk.

## v2.14.1

- **Desktop: right-click a message** to open its menu (reply, react, pin, forward, report…) instead of long-pressing. This also makes **reporting a message work on desktop**, which wasn't reachable before.
- Help & Tutorials: added a "Report a user, group or message" guide (with desktop right-click steps).

## v2.14.0

- **Temporary bans** — when banning a user in the Manager you now choose a duration (1 hour, 1 day, 7 days, 30 days, or permanent). The app shows the banned person a "you're banned — time remaining" notice, and the ban lifts automatically when it expires. The Manager shows the time left on each banned user.
- **Admins can manage invites** — admins can now create and revoke invite codes and set a user's invite count in the Manager, the same as the owner. (Deleting/renaming users, password resets, roles and group management remain owner-only.)

## v2.13.0

- **Report a group** — report a whole group (reason, description, evidence) from the group's options.
- **Report a specific message or image** — long-press a message → Report. Since screenshots are blocked, the offending message text or image is captured automatically and attached to the report for staff to review.
- **Admin-scoped Manager** — admins now sign in to the Manager with their own Hush Chat account (no shared key) and get a reduced set of tools: handle reports, ban/unban users, and grant/deny role requests. Everything else (invites, deleting/renaming users, password resets, roles, group management) stays owner-only. The owner keeps full access via the admin key.
- **Automatic update checks** — the app checks for a newer version by itself while it's open or in the background and notifies you when one is available, with a tap-to-update banner on the chat list.
- Manager: reports now cover users, groups, and messages (with the reported message shown inline).

## v2.12.0

Role perks that were staged in v2.11.0 are now fully working, plus an in-app help guide.

- **Animated GIF avatar (VIP+)** — use a moving GIF (up to 2 MB) as your profile picture.
- **VIP message accent (VIP+)** — your username shows in your role colour and your chat bubbles get a matching highlighted border, in both direct and group chats.
- **Profile banner (Supporter+)** — add a banner image to the top of your profile.
- **Broadcast (Supporter+)** — send one message privately to all of your friends at once from the chat-list menu.
- **Recurring scheduled messages (Supporter+)** — schedule a message to auto-send Daily or Weekly, not just once.
- **Custom app icon (Supporter+)** — switch the Android launcher icon between Default, Gold and Crimson from Settings.
- **Help & Tutorials** — a new searchable in-app guide (Settings → Help) explaining scheduled messages, hidden chats, decoy/panic PINs, disappearing messages, verifying contacts, and every role perk. The guide adapts to the platform (desktop shows click/right-click wording and hides phone-only items).
- **Report a user** — report another user from their profile or the chat options: pick a reason, add an optional description, and attach evidence images. Reports appear in the Manager with actions to contact the reporter, resolve, dismiss, or ban the reported user.
- **Manager** — the roles legend now includes a "Perks by tier" table listing what VIP+ and Supporter+ unlock, plus a new Reports panel.

## v2.11.0

- Role-exclusive perks framework: custom accent colour and exclusive themes (Aurora/Gold), 50 MB file sharing and unlimited pinned messages (VIP+); coloured username (Supporter+).
- Pull-to-refresh on the chat list plus automatic refresh every minute.

## v2.10.0

- Privacy toggles: hide presence / last-seen, and turn off read receipts and typing indicator (VIP+).
- Scheduled messages (send later).
- Group profile (avatar + description) and per-contact profile view.
- Archive and favourite chats.
- Invites auto-revoke and are removed 2 hours after they expire.
- Supporter role (between VIP and moderator) and refreshed Manager roles legend.

## v2.9.1

- Fixed stealth PINs so the real, decoy and panic PINs all work together.
- The server owner automatically gains owner/co-owner powers in every group.

## v2.9.0

- Group tools: roles, kick/ban, invite links, and polls.
- Stealth & duress: decoy PIN, hidden chats, and panic wipe.
- Profiles: avatar, display name and bio (E2EE relay).
- Message search and pinned messages.
- Typing indicators and type-only message previews.
- Selectable call ringtones.

## v2.8.1

- Portrait orientation lock.

Older releases: see the GitHub Releases page.
