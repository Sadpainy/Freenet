# Freenet Android Client

A minimalist, pure Java, command-line built Android client for launching and managing a Freenet (Hyphanet) node on Android devices without requiring root access.

## Overview

Due to the restrictive background execution and cross-app communication policies introduced in Android 10 and higher, traditional methods of silently launching Termux services (e.g., via `RUN_COMMAND` broadcasts) are often intercepted and killed by the system.

To bypass these limitations, this application utilizes a "Physical Injection" method:
1. The App constructs the required Bash commands.
2. It copies the command to the system clipboard.
3. It forcefully launches the Termux application.
4. The user simply pastes the command and hits enter.

This ensures 100% reliability across different Android ROMs while respecting the system's security boundaries.

## Prerequisites

- Android 10 (API 29) or higher.
- [Termux](https://f-droid.org/en/packages/com.termux/) installed.
- "Display over other apps" (Floating Window) permission granted to Termux.
- Background power consumption allowed for both this App and Termux.

## Features

- **Setup Wizard**: Step-by-step guidance to install the Debian environment, OpenJDK, and the Freenet node.
- **Minimalist UI**: Pure white and Freenet blue colors, built entirely with native Java code (no XML layouts).
- **Foreground Service**: A built-in foreground service with notification support to keep the app alive.
- **Command Injection**: Seamlessly copies terminal commands to the clipboard and redirects to Termux.
- **Native Library Support**: Integrates `arm64-v8a` native libraries via JNI.

## Disclaimer

Running a heavy Java-based node inside a proot environment on a mobile device will consume significant battery and network data. Use with caution.

## License

This project is licensed under the _GNU General Public License v3.0._ See the LICENSE file for details.
