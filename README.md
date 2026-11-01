# OFFLINE TALKS 1.0.0-beta

An Android BLE messenger starter project. The app advertises a custom BLE service, discovers other phones advertising that service, connects with GATT, sends text writes, receives subscribed notifications, and stores a local message history.

## Build and install
1. Install Android Studio (recent stable version) and Android SDK Platform 35.
2. Open this project folder in Android Studio.
3. Allow Gradle sync to complete. Use Android Studio's bundled JDK.
4. Connect two real Android phones (USB debugging enabled) and install on both.
5. Enable Bluetooth and grant the requested Nearby Devices permission.
6. Keep both apps open. On one phone tap **Find nearby users**, then connect to the other phone.
7. Send a short text message. For a two-way test, establish a connection from the other phone as well if the phone/OS permits the simultaneous GATT roles.

## What is included
- Offline Talks branding and basic Android UI.
- BLE service advertising and nearby discovery.
- GATT server write handling.
- GATT client connection and text sending.
- Notification subscription and incoming notification handling.
- Local chat history in app-private preferences.
- Permission handling for Android 12+ and older Android versions.

## Important limitations — do not treat this beta as a public-ready secure messenger
This code is a functional starting point, but Bluetooth behavior varies by manufacturer and Android release. It has not been compiled or validated on physical devices in this environment.
- BLE range is environment- and device-dependent; 50 metres is not guaranteed.
- This beta is for short text payloads (180 UTF-8 bytes) and a basic one-peer chat flow.
- For dependable two-way chat, both phones may need to establish their own GATT client connection. Some phones restrict simultaneous central/peripheral roles.
- No end-to-end encryption, authenticated identity, spam protection, or secure key exchange is implemented. Do not send sensitive information.
- No groups, photos, files, multi-hop mesh relay, store-and-forward routing, background service, push notifications, or iOS build yet.
- Chat history is local to the device and is not synchronized or encrypted.
- The app needs to remain open during this beta test.

## Next work for a release candidate
1. Add a robust connection manager with serialized GATT operations, MTU negotiation and chunking.
2. Add authenticated pairing and end-to-end encryption (e.g. reviewed Noise-based protocol).
3. Add durable message IDs, acknowledgements, retries, duplicate suppression and delivery states.
4. Add multi-peer group transport and carefully bounded mesh relaying.
5. Add encrypted database, attachment transfer, background foreground-service behavior, and battery-aware scanning.
6. Run interoperability and range tests on a matrix of Android phones.
7. Complete security review, privacy policy, app icon, signing and Play Store compliance.
