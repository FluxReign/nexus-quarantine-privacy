# Nexus Quarantine Privacy Policy

Effective date: November 13, 2026 (updated for versions 0.5.0 and 0.6.0)

Nexus Quarantine is a local-first personal privacy and security hygiene companion. This policy applies to the Android app and to a possible iOS version. It explains what the app does with information on your device. Some features described below, such as the installed-app audit and the local firewall, exist only on Android.

Developer: Mackenzie Swim, Ottawa, Ontario, Canada.  
Contact: [thewhiskeywizard99@gmail.com](mailto:thewhiskeywizard99@gmail.com)

## 1. Data stays on your device, with one narrow exception

Almost all information the app uses stays on the phone or tablet where you installed it. There is no Nexus Quarantine developer server, cloud account, or backend that receives your entries, app list, or pasted messages.

If you choose to use the app, it can store on the device:

- A passphrase you create (used locally to encrypt data stored by the app; it is not sent to the developer)
- Hygiene checklist ticks, in-app lock settings, and an optional daily reminder preference
- Optional identifiers you type (for example names or emails you already use) to build self-search queries, opt-out letters, and a PIPEDA access-request letter on the device
- Optional trusted-contact name and check-in timer notes you type (nothing is sent automatically)
- Optional sleep, mood, and social notes you type yourself
- Text you paste into the secret scanner or the Canadian scam checker (processed on the device; you can clear it)
- Snapshots of permissions for apps you can open, so the app can show you what changed over time
- Local firewall preferences (from 0.6.0): whether the local DNS/app firewall is on, per-app block toggles, and an on-device count of blocked requests

On-device data is encrypted with your passphrase (AES-GCM), except for a few operational items that have to live in ordinary app storage so the Android service can read them (for example firewall on/off). If you forget the passphrase, the encrypted store cannot be recovered.

## 2. Installed apps, permissions, and trackers

When you start an app audit or tracker report, the Android app reads the list of *launchable* apps, their install source, and their permissions, using Android’s PackageManager and a narrow launcher query (not the QUERY_ALL_PACKAGES permission). Tracker matching compares the installed APK with a bundled snapshot of the public Exodus Privacy tracker list. That inventory and the scan results stay on your device. They are not uploaded to the developer or to Exodus.

## 3. Pwned Passwords (the only routine third-party request)

If you use the Pwned Passwords check, the app hashes the password you type with SHA-1 on the device, then sends **only the first five characters** of that hash to Have I Been Pwned’s public range API at `https://api.pwnedpasswords.com`. The password itself, and the rest of the hash, never leave the device. The field is cleared after the check. Have I Been Pwned is an independent service (Troy Hunt) with its own privacy policy. The developer does not receive the prefix or the password.

## 4. Local firewall (version 0.6.0 and later)

If you turn on the optional local firewall, the app uses Android’s VpnService to filter DNS and, if you choose, to block internet access for selected apps. This is a local tunnel only. There is no Nexus Quarantine VPN server and no remote hop. DNS lookups for allowed names are resolved using the DNS servers of your current network, through a protected socket. Blocked names are answered on the device. Request counts stay on the device. You can turn the firewall off at any time in the app.

## 5. What we do not do

- We do not run ads or analytics in the app
- We do not sell, rent, or share your information with third parties (the HIBP prefix is sent only at your request, as described above)
- We do not collect information on a developer server
- This version of the app does not include an encrypted health or notes vault, and it does not import data from Health Connect, HealthKit, Google Fit, or similar platforms
- The app does not scan other people’s accounts or your local network for devices you do not own
- A “Plus” plan may be described as coming soon; this version does not bill you or collect payment details
- Links to the official WireGuard app are only links. This app does not import or store your WireGuard private keys

## 6. Internet access

The app requests the standard Android INTERNET permission. Besides the Pwned Passwords check, it is used when you tap an external link you choose to open (for example official privacy opt-out forms, Play Protect settings, a search, or Canadian Anti-Fraud Centre pages). Those sites have their own privacy policies.

Android cloud backup for this app is turned off (`allowBackup` is false), so app data is not included in automatic device backups to Google.

## 7. How to delete your data

You can remove everything the app stored on the device by:

- Using the in-app “wipe local data” control, and/or
- Clearing the app’s storage in Android Settings, and/or
- Uninstalling the app

Because we do not keep a copy on a server, there is no additional copy for us to delete after you wipe or uninstall. Have I Been Pwned may retain range-query logs under its own policy; we cannot delete those on your behalf, and they do not include your password.

## 8. Children

Nexus Quarantine is not directed at children under 13 (or under 16 where that is the applicable age). We do not knowingly collect personal information from children.

## 9. Changes

If this policy changes, the updated text will be posted in this repository with a new effective date.

## 10. Contact

Questions about this policy: Mackenzie Swim, [thewhiskeywizard99@gmail.com](mailto:thewhiskeywizard99@gmail.com), Ottawa, Ontario, Canada.

---

This is not legal advice. It describes how this app is built to work.
