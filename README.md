# Bible Display Pro — OBS Development Workspace

This repository currently contains two related but separate components:

1. **OBS Studio plugin template** — the native C/C++ plugin starter project in the repository.
2. **Bible Display Pro application package** — `Bible_Display_Pro_Quick_Go_Live_Fix.zip`, a Python/HTML/CSS/JavaScript application that presents KJV scripture through an OBS Browser Source.

## Important architecture note

The OBS plugin template is a starter framework, not a ready-made integration. The Bible Display Pro ZIP is currently a separate browser-based application. They have **not yet been merged into a working native OBS plugin**.

The existing Bible Display Pro application does not need a native plugin to work: it runs a local Python server, opens its controller in a browser, and supplies a transparent output page to OBS as a Browser Source.

For that reason, the safest current approach is to preserve the native plugin template unchanged while keeping the existing Bible Display Pro package intact. A native plugin should only be added later if a specific OBS-native feature is needed.

## Current contents

- Native OBS plugin-template source and build configuration in the repository root.
- `Bible_Display_Pro_Quick_Go_Live_Fix.zip` — the existing Bible Display Pro application package.
- This README — explains how the two components relate and prevents the template from being mistaken for a completed integration.

## Running the existing Bible Display Pro application

1. Download and extract `Bible_Display_Pro_Quick_Go_Live_Fix.zip`.
2. Open the extracted application folder on a Windows computer.
3. Run `start.bat` and allow first-time setup to finish.
4. Open the controller at `http://127.0.0.1:8765/index.html`.
5. In OBS, add a Browser Source using `http://127.0.0.1:8765/output.html`.
6. Keep the local server running while presenting.

The application uses a local Python server. GitHub Pages cannot run that server, so GitHub Pages alone cannot host the live controller/output workflow.

## Before building a native plugin

A future integration should be treated as a separate development task:

- Define the exact native OBS feature required.
- Review the template's build instructions and license.
- Implement the plugin in the template's expected C/C++ structure.
- Keep the existing browser-based Bible Display Pro working as a fallback.
- Build and test on the target Windows/OBS setup before calling it complete.

## Verification status

The repository structure and commit history have been inspected. The ZIP is present in the repository. The native plugin template and browser-based application have **not** been compiled or tested together, and no claim of a working native plugin integration is made.
