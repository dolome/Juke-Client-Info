# Privacy

This document describes the current behavior of Juke Client. It is a technical disclosure, not a substitute for a publisher's legally reviewed privacy notice.

## Data stored on this computer

- Launcher settings, game profiles, installed game files, worlds, local friends data and the selected skin are stored in Electron's application data folder or the profile folders. Launcher diagnostic logs are kept locally in the app data `logs` folder, with a 5 MB per-session cap and rotation to the five newest files.
- The CurseForge API key and Microsoft refresh token are encrypted with Electron `safeStorage` when operating-system-backed encryption is available. Sign-in and CurseForge key storage are unavailable when secure storage cannot be used.
- Microsoft access tokens are held in the main process memory and passed to Java only when starting Minecraft.
- The launcher does not currently upload crash reports, logs, skins, worlds, profiles or friends data automatically. Copying a log only puts it on the local clipboard.

## Network connections

The launcher contacts Mojang's version and game-download services, Microsoft/Xbox/Minecraft Services during sign-in and token refresh, Fabric/Forge/NeoForge/Quilt metadata services when resolving loaders, Adoptium when a Java runtime is requested, and Modrinth or CurseForge when their catalog or pack-import features are used. Minecraft files and modpack files are downloaded from the providers or hosts listed in their metadata and checked against available hashes.

Using the Servers page opens a connection to the host and port entered by the user. That server sees the connection and the user's network address. No server address is sent to a Juke Client backend.

There is no analytics, telemetry, update-check, or release-download service configured in this project. Builds remain local or in access-controlled CI artifacts until a private distribution endpoint is configured.

## Data deletion

Use the profile deletion control to move a profile's game directory to the operating-system trash. Other launcher data can be removed by uninstalling the app and deleting its application data folder. Game worlds and logs may contain information the user entered while playing.

## Third-party services

Network requests are subject to the privacy terms of the relevant provider, including Microsoft, Mojang/Minecraft, Adoptium, Modrinth, CurseForge, and any Minecraft server the user chooses to ping. This project has no publisher contact address or support website configured yet.
