# Changelog

Release history for Qivomo, newest first. Each entry describes what changed from a user's point of view — what you can see or feel, not how it was implemented.

**How versions are numbered**: the last digit always moves one step at a time (1.2.3 → 1.2.4 → … → 1.2.9 → 1.3.0). The middle digit only bumps once the last digit reaches 9, and the first digit is reserved for architectural changes.

---

## v1.4.6 — 2026-11-03

**Added**

- New **Support the developer** entry on the About page, with Bilibili, Alipay and WeChat. If the matching app is installed you are asked once before it opens; if not, the browser takes over, so a tap never does nothing.
- The Alipay and WeChat QR codes can be viewed and saved to your gallery inside the app, so you can scan them later.

**Improved**

- The four About page entries are reordered: About the developer → Support the developer → Disclaimer → Check for updates.
- **Check for updates** now takes you straight to the Gitee releases page (recommended in mainland China); the GitHub repository is still being set up.
- The download is much smaller: about 7.2 MB → 1.8 MB, so installing and launching are both faster.

**Notes**

- **This release is signed with a new key, so upgrading from an older version requires uninstalling first.** Android will not install it over a package signed differently. Uninstalling wipes your configuration and the "disclaimer accepted" state — export your configuration under **Settings → General → Export** in the old build, then import it after installing.
- This is a one-time change: from v1.4.6 onward all releases share the same key, and later upgrades install over the top.
- v1.4.5 remains the oldest version you can roll back to.

## v1.4.5 — 2026-11-02

**Improved**

- The disclaimer shown on first launch has clearer footer wording: "Please read the terms" until you reach the bottom, then "Agreeing means you have read them and accept the risk yourself".
- You still have to scroll all the way down before **Agree** lights up.

**Notes**

- As of v1.4.5, **v1.4.5 is the oldest installable version**: rolling back later is only possible to this release, and earlier builds are no longer published.
- A rollback requires **uninstalling** the current version first (Android will not install an older build over a newer one), and uninstalling wipes your configuration and the "disclaimer accepted" state. Export a backup beforehand.

## v1.4.4 — 2026-11-02

**Improved**

- First-launch order changed: the disclaimer comes first, and the overlay permission is only requested after you agree — no permission prompt out of nowhere.

**Fixed**

- The device list no longer shows internal on-board nodes such as "fingerprint" or "power key"; only real keyboards, mice and gamepads are listed.

## v1.4.3 — 2026-11-02

**Improved**

- Rewrote the explanation for **exclusive physical input**: once enabled, Qivomo takes over keyboard and mouse input and simulates touch, so Shizuku must be authorised or mapping will not work.

## v1.4.2 — 2026-11-02

**Removed**

- Removed the accessibility fallback. It could not read mouse movement, only supported single taps, and would abruptly interrupt camera drags — in practice it was barely usable.

**Improved**

- The overlay permission request on first launch is now a "go there?" confirmation, so you can answer no and grant it later instead of being asked repeatedly.
- The bottom button on the Activation & permissions page now guides you in order: it names whichever item is missing, and shows "All permissions granted" once everything is ready.
- The top status line shows "Activated" when everything is ready, or lists exactly what is still missing.
- Profiles now switch automatically when you move to a bound app — faster to detect and easier on the battery.

**Fixed**

- Injection failures now state the actual reason and stay disabled, instead of reporting a fallback that looked like it still worked.

## v1.4.1 — 2026-11-01

**Improved**

- The overlay permission request jumps straight to the system permission page, so you no longer have to dig through Settings.
- Each unfinished item on the Activation & permissions page has a **Go to settings** button on the right that opens the matching system page.

## v1.4.0 — 2026-11-01

**Added**

- New **About** page in Settings: version, check for updates, about the developer and the disclaimer all live there now.
- First launch now asks you to accept the disclaimer: **Agree** only becomes available at the bottom, and declining exits the app.

**Improved**

- The version number that used to sit in the Settings header has been replaced by the About entry.

---

## v1.3.9 — 2026-11-01

**Improved**

- The bottom navigation bar is more compact: icons and labels sit closer together and the whole strip no longer looks loose.
- The headers of the four secondary pages (New / Edit / Settings / Activation) are now consistent: the back button is icon-only and the title follows it in the top-left corner.
- Removed the caption under the title in the Settings header.
- When editing an existing profile the bottom button reads **Edit** rather than **New**; it still reads **New** for a new profile.

## v1.3.8 — 2026-11-01

**Fixed**

- Fixed a regression from the previous release: tapping **Scenes** in the bottom navigation did nothing.
- Fixed the navigation highlight getting stuck on an invisible page that could not be reached by any tap.

## v1.3.7 — 2026-11-01

**Fixed**

- Returning from a secondary page to Scenes used to leave the bottom navigation highlight waiting for the transition to finish; it now moves as soon as you tap.

**Improved**

- The system back key, **Done / Cancel** on the edit page and the back button in Settings all update the highlight immediately too.

## v1.3.6 — 2026-11-01

**Added**

- The bottom navigation is now a single sliding thumb: tapping **Settings** glides it over from **Scenes**, passing **New** visually without switching to it.
- You can also drag left and right along the capsule; releasing snaps to the nearest entry.

**Improved**

- Icons and labels change colour as the thumb passes over them, so light text never ends up on a light thumb.

## v1.3.5 — 2026-11-01

**Fixed**

- Fixed the path Scenes → New → Settings → tap Scenes landing back on New; the three entries are now equal-level tabs that switch independently.

**Improved**

- The share code prefix changed to **QVM.** to match the app. Share codes you exported earlier still import fine.

## v1.3.4 — 2026-10-31

**Added**

- New app logo in the top-left corner of the home screen.

**Improved**

- New app icon, sharper at every density; the status bar icon is no longer a white square.

**Fixed**

- The bottom navigation bar no longer disappears when you switch to **New**.
- Scrolling down the edit page no longer pushes the back button and title off screen — they stay pinned at the top.

## v1.3.3 — 2026-10-31

**Fixed**

- Fixed the **Settings** button becoming unresponsive, seemingly doing nothing, after switching between pages several times.

**Improved**

- Removed the caption below the scene list on the home screen.
- The import button now reads just **Import**, without the down-arrow icon.

## v1.3.2 — 2026-10-31

**Added**

- Page transitions are now a circular reveal: the new page expands from the button you tapped until it fills the screen, and collapses back to it when you go back.
- **Import** moved from the bottom navigation to a floating button in the bottom-right corner of the Scenes page.

**Improved**

- The bottom navigation is down to three entries: **Scenes / New / Settings**.

## v1.3.1 — 2026-10-31

**Added**

- New capsule-shaped floating navigation bar at the bottom, gathering Import / New / Settings into one strip.
- Settings categories can be swiped left and right, following your finger.

**Fixed**

- Fixed the primary colour set in the theme not matching what was displayed (it used to be blended with a dark base).

## v1.3.0 — 2026-10-29

**Fixed**

- Fixed the leftmost strip of the screen being unreachable in landscape — the mouse pointer could not enter it and mapping circles could not be dragged into it. The editing area now covers the whole screen.

## v1.2.9 — 2026-10-29

**Fixed**

- **Cancel / Done** on the phone's editing panel are no longer clipped off screen: the panel now has a fixed header and footer with a scrolling body.
- Same treatment for the floating ball menu, so **Settings** and **Exit** are no longer clipped on small screens or in landscape.
- The key capture window on tablets is a centred card instead of one extremely wide frame.

## v1.2.8 — 2026-10-29

**Fixed**

- Fixed the page flicker when going back, for good (the previous two releases only patched the symptoms).

## v1.2.7 — 2026-10-29

**Fixed**

- Fixed blank areas of the Settings page letting taps through to the home screen and accidentally starting mapping.
- Fixed a flicker during the back animation.

## v1.2.6 — 2026-10-29

**Fixed**

- Fixed going back having no animation, with the old page simply covered by the new one.

**Improved**

- Added a transition when switching Settings categories: the highlight fades and the content fades up from below.

## v1.2.5 — 2026-10-29

**Added**

- New **app transition animations** switch in Settings, controlled separately from the floating ball menu's animation switch.
- The **Activate** button in the top-right corner of the home screen is now a status badge: "Activated" when authorised, a red dot when not.
- New overall status bar at the top of the activation page, stating plainly whether the app is activated and what is still missing.
- Reference resolution gained an **Auto (this device)** option that reads the current resolution.
- Scene cards show the icon of the bound app on the left.

**Improved**

- The scene name is filled in with the app name once you pick a bound app; it is not overwritten if you have edited it by hand.
- The custom resolution field can be cleared and retyped properly, and now has a **Save** button with error hints.

## v1.2.4 — 2026-10-29

**Added**

- New **Settings** entry on the home screen, with a redesigned in-app settings page: navigation on the left on wide screens, category tabs on top on narrow ones, grouped cards for content.
- Settings mirror the floating ball menu one-to-one; either place can change them.


**Fixed**

- Fixed the overlapping, crammed content in the previous release's settings page.

**Notes**

- The version number was rolled back from a mistaken 1.3.0 to 1.2.4; devices running the previous build can still upgrade in place.

## v1.2.3 — 2026-10-29

**Improved**

- Colour roles are now separated: the primary colour only paints window backgrounds, the secondary colour only paints buttons and switches. Changing the primary colour no longer changes text with it.
- System widgets such as dropdown menus follow the primary colour instead of showing the default dark grey.

## v1.2.2 — 2026-10-29

**Fixed**

- Fixed the key capture window covering the mouse pointer, so the crosshair was invisible.

## v1.2.1 — 2026-10-28

**Fixed**

- Fixed clicking **Done / Cancel** with the mouse while editing doing nothing and instead opening a new mapping dialog.
- Fixed taps on empty space inside the capture dialog creating a mapping.

## v1.2.0 — 2026-10-28

**Added**

- **Add mapping** no longer opens a full-screen editor; editing happens in place on the floating ball, so only translucent control circles remain and the game stays visible.
- The panel next to the floating ball lists key bindings, changes control types, and saves or cancels.
- Tap an empty spot on screen, press a key, and a bound control appears right there.

**Improved**

- Position first, bind second: picking a type drops a control you can drag into place, and binding happens in the detail panel instead of a modal dialog.

## v1.1.0 — 2026-10-28

**Added**

- New **Settings** entry in the floating ball menu: peripherals, mouse, keyboard, gamepad, general and debugging, all adjustable with immediate effect.
- The device list shows device name, connection type (wired / Bluetooth / 2.4 GHz) and battery level.
- Mouse: sensitivity (global and per-axis), polling rate, smoothing, acceleration curve.
- Keyboard: repeat delay and rate, long-press threshold.
- Gamepad: brand detection, stick dead zone and outer-ring sensitivity, response curve, trigger threshold, rapid-fire interval, vibration strength.
- Theme: primary, secondary, text and outline colours, with colour wheel, HEX and RGB in sync; bold text is optional.
- The floating ball's shape, size, opacity and position lock are adjustable; when hidden it collapses into three dots at the top of the screen.
- New debug overlays: pointer crosshair, key event log, polling-rate statistics.

**Improved**

- The old **right-click to walk** became **combo**: every member key must be held, and releasing any one releases it. Existing profiles are unaffected.

## v1.0.1 — 2026-10-28

**Improved**

- The app was renamed from KeyMap to Qivomo, with a new icon and versioned APK file names.
- Version numbering is centralised, and the home screen shows the current version.

**Notes**

- The app identity changed, so this counts as a different app: **you cannot install it over the old version — uninstall first.** Export your configuration from the old build and import it into the new one.

## v1.0.0 — 2026-10-26

**Added**

- First release (called KeyMap at the time): Shizuku authorisation takes over the physical keyboard and mouse and translates key presses and mouse movement into touch input.
- Scene profiles with per-app auto switching, macro steps, multi-touch and gestures.
- Floating ball entry point and overlay editing: drag controls into place, learn keys.
- Configuration import/export and share codes.
