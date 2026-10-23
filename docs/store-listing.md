# EJG Home: App Store and Google Play listing drafts

Draft dated 2026-10-22, for the owner's review. Nothing here has been submitted. Placeholders in double braces must be filled in by the owner. The privacy-label and export-compliance answers need the owner's confirmation (and, where flagged, a lawyer's).

Wording follows `docs/WORDING-RULES.md`.

---

## Shared text

**App name:** EJG Home
**Subtitle (30 characters max, App Store):** Control your EJG-OS home
**Company / seller name:** EJG Technologies Inc.
**Copyright:** (c) 2026 EJG Technologies Inc.
**Support URL:** https://ejgos.com/support (publish this page first; until then https://ejgos.com/contact)
**Marketing URL:** https://ejgos.com
**Privacy Policy URL:** https://ejgos.com/privacy-policy
**Keywords (100 characters max, App Store):**
`smart home,home automation,z-wave,lights,thermostat,security,camera,lock,skip assistant,ejg`

## Description (App Store, 4000 characters max; also usable as the Google Play full description)

```
EJG Home is the companion app for EJG-OS, a smart home system designed and installed by EJG Technologies Inc. in Calgary, Alberta. It needs an EJG-OS hub in your home. It does not work without one.

WHAT IT CONTROLS
- Lights, dimmers and plugs: on, off and brightness
- Smart locks: lock and unlock, and see lock and unlock events
- Thermostats: set the temperature and manage schedules
- Scenes: one tap for Good Morning, Away, Movie or Sleep
- Automations: turn on or off the routines your installer set up
- Cameras: watch your cameras on your phone, with live view and recorded video from your recorder
- Alerts: phone alerts for lock, door and motion events. EJG-OS is self-monitored: alerts come to you. There is no monitoring centre and nobody is dispatched.

RUNS ON A HUB IN YOUR HOME
Your lights, locks, thermostats, scenes and automations are controlled by the EJG-OS hub in your house, and they keep working with the internet unplugged. At home the app talks to your hub directly over your home network. Your device history, scenes and automations stay on the hub.

SKIP, THE VOICE ASSISTANT
Skip is the voice assistant built into EJG-OS. Say "Hey Skip" for lights, locks, the thermostat, scenes, timers, reminders and lists. Skip understands a defined set of home commands. It is not a general chatbot, and it is still being tuned. Skip runs on your hub, and nothing you say to Skip is sent to EJG or to any AI service. On iPhone, Skip is off until you turn it on. Speech is turned into text on the phone itself, in English, on phones that have the on-device speech model installed, and only the text goes to your hub. Unlocking by voice is off unless you turn it on, and Skip always asks you to confirm.

AWAY FROM HOME
Secure remote access through EJG Secure Link. Traffic between your phone and your hub is encrypted end to end. EJG runs a small service that helps your devices find each other and a relay that passes encrypted data it cannot read.

SIGN-IN AND SECURITY
You stay signed in on your phone. Two-step verification is available, the owner can see every trusted device and remove any of them, and the hub cannot be opened in a web browser.

PRIVACY
No ads, no analytics and no trackers in the app. We never sell your data. A few features use outside services: phone alerts pass through Expo, Apple and Google as a plain "new alert" notice, app updates come from Expo, and the optional weather and Spotify extras are off until you turn them on. Every service is named in our privacy policy at ejgos.com/privacy-policy.

REQUIRES AN EJG-OS HUB
EJG-OS is installed by EJG Technologies Inc. in Calgary and the surrounding area. Visit ejgos.com to book a free consultation.
```

Conditions to check before submitting this text:
- The camera line ("watch your cameras on your phone, with live view and recorded video from your recorder") is true only for the app build that contains the camera screens and recorder control. Remove it if the submitted build does not.
- "Stay signed in" and the trusted-device wording are true only for the build and hub release that contain them.
- Do not add anything about a Skip button. Skip is voice and wake word only.

## What's New (draft)

```
Stay signed in on your phone until you sign out. Camera screens and recorder playback. Fixes and improvements.
```
(Edit to match the build. State only what is in it.)

## Google Play

**Short description (80 characters max):**
`Control your EJG-OS smart home: lights, locks, scenes, cameras and Skip.`

**Full description:** use the description above (the Play text limit is 4000 characters).

**Data safety form (draft answers, owner to confirm):**
| Question | Answer |
|---|---|
| Does the app collect or share user data? | Yes, a push token and an app-update install ID go to Expo (and through it to Google) so alerts and updates work. |
| Data type: Device or other IDs | Collected: push token and install ID. Purpose: app functionality. Not used for advertising. Not shared for advertising. |
| Data type: Location, contacts, photos, audio, financial, health | Not collected by EJG. (Microphone is used on the device for Skip; speech is turned into text on the device and only the text goes to the user's own hub.) |
| Is data encrypted in transit? | Yes |
| Can users request deletion? | Yes. Contact info@ejgos.com. Data on the hub can be erased on request. |
| Ads / tracking | None |

---

## App Privacy label (App Store Connect), draft answers

Do **not** answer "Data Not Collected". The app sends a push token to Expo and Apple, and an install ID to Expo's update service. Apple counts data as collected when it leaves the device and the developer or a partner can access it beyond the real-time request.

| Data type | Collected? | Purpose | Linked to the user? | Used to track? | Notes |
|---|---|---|---|---|---|
| Identifiers: Device ID | Yes | App functionality | Owner to confirm (the token is tied to the user's own hub, not to an EJG account) | No | Expo push token (relayed by Expo to Apple and Google) and the Expo update install ID |
| Diagnostics | Confirm | | | | Answer Yes if the app sends any crash or performance report anywhere. As far as this draft is aware it does not. |
| User content, location, contacts, health, financial, browsing, search, usage data | No | | | | No analytics or telemetry. Skip text goes only to the user's own hub. |
| Audio data | No | | | | iPhone speech recognition is on the device and requires an on-device model. Confirm in the shipped build. |

- **Data used to track you:** None.
- Review the answers against the shipped build before submitting, and again whenever a new service is added.

## Export compliance (ITSAppUsesNonExemptEncryption): needs the owner's decision

**Current setting:** `ITSAppUsesNonExemptEncryption: false` in the app config.

**Why this is probably the wrong answer.** Remote access uses EJG Secure Link, which embeds a WireGuard-based VPN implementation inside the app. That is standard encryption in addition to the encryption iOS already provides, not just HTTPS through the operating system. Apple's export questions treat that as "uses encryption" that is not covered by the simple exemption for OS-provided encryption.

**Likely correct answer (to be confirmed):**
- "Does your app use encryption?" Yes.
- "Does it use encryption other than, or in addition to, what the operating system provides?" Yes (standard, published algorithms inside the Secure Link component; nothing proprietary).
- The app is likely to qualify for the mass-market exemption for publicly available encryption software. If so, set `ITSAppUsesNonExemptEncryption` to `true`, supply the export-compliance documentation Apple asks for if required, and file the annual self-classification report with the US Bureau of Industry and Security (due each year by 1 February) for the previous calendar year.
- This applies to the phone app and the tablet app.

**Why flagged:** the correct classification depends on exactly what the shipped binary contains and on the owner's own export position. Confirm with a lawyer or the export-control adviser before submitting. Do not ship the current `false` without a decision.

---

## Notes for Apple App Review (App Store Connect "Notes" field), draft

```
EJG Home is the companion app for EJG-OS, a smart home system installed by EJG Technologies Inc. in Calgary, Canada. It controls an EJG-OS hub inside the customer's home, so it needs a hub to do anything.

To review the app, use the demo hub we have set up for you:
  Hub address / invitation: {{REVIEW_DEMO_HUB}}
  Username: {{REVIEW_DEMO_USER}}
  Password: {{REVIEW_DEMO_PASSWORD}}
If the demo hub is not reachable, contact info@ejgos.com and we will respond the same business day.

Skip (the voice assistant):
- Skip is OFF by default on iPhone. The first time the user turns it on, the app shows a consent sheet explaining that the microphone and speech recognition are used, and nothing is listened to until the user agrees.
- Skip runs on the user's own EJG-OS hub, in their home. On iPhone, speech is converted to text on the device using Apple's on-device speech recognition (requiresOnDeviceRecognition is true; no online speech service is used), and only the text is sent to the user's hub. No audio and no text from Skip is sent to EJG or to any AI service.
- Skip understands a defined set of home commands (lights, locks, thermostat, scenes, timers, reminders, lists). Unlocking by voice is off unless the homeowner enables it and always asks for confirmation.

Network use:
- Notifications: the hub sends a plain "you have a new alert" notice through Expo's push service to Apple's push service. Details are fetched from the user's own hub when the app opens.
- Remote access: EJG Secure Link (end-to-end encrypted between the phone and the hub; EJG operates a coordination server and relay that cannot read the traffic).
- The app checks Expo's update service for app updates.
- No advertising, analytics or tracking SDKs.

Camera permission is used only to scan a setup QR code. Local network permission is used to reach the hub directly on the home network.
```

Items to verify before submitting this note: the consent sheet and the "off by default" behaviour are present in the submitted iPhone build; the demo hub is reachable from Apple's review network; no button anywhere starts listening.
