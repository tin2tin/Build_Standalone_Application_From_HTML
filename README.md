# Build Standalone Application From HTML

A simple web-based tool to generate a complete Electron project ZIP file, ready for building cross-platform desktop applications (Windows, macOS, and Linux). This generator allows you to customize app details, select project files, and configure build options—all in your browser.

## Try it!

<div align="left">
  <a href="https://tin2tin.github.io/build_html_to_standalone/">Start the app</a><br><br>
</div>

## Features
- Generate a ZIP file with a fully configured Electron project.
- Supports Windows, macOS, and Linux builds.
- Customizable window styles (Standard, Maximized, Fullscreen).
- Drag-and-drop folder support for project files (optimized for Chrome/Edge).
- Save and load configuration settings.
- Includes build scripts for one-click compilation.

## Requirements
- **Node.js**: v20+ (LTS recommended, download from [nodejs.org](https://nodejs.org/)).
- A modern web browser (Chrome or Edge recommended for full functionality).

## Usage

### 1. Generate the Project
1. Download and open `generator.html` in a compatible browser.
2. Fill in the **App Name** and **App ID** (e.g., `com.company.appname`).
3. Select a **Target Platform(s)** (Windows, macOS, Linux) and **Window Style**.
4. Drag and drop a folder containing an `index.html` file, or click to select it.
5. Upload an app icon (`.png`, `.ico`, or `.icns`).
6. Click **Generate Project ZIP** to download `electron-project.zip`.

### 2. Build the Project
1. Extract `electron-project.zip` to a folder.
2. Follow the platform-specific instructions below:

#### For Windows
- Right-click `electron-project.zip`, select "Properties," and unblock if needed.
- Extract the ZIP.
- Open Command Prompt in the extracted folder (shift + right-click > "Open command window here").
- Type `build.bat` and press Enter.

#### For macOS/Linux
- Unzip `electron-project.zip` (double-click or run `unzip electron-project.zip` in Terminal).
- Open Terminal in the extracted folder.
- Run `chmod +x build.sh && ./build.sh`.

3. The built app(s) will appear in the `dist` folder (e.g., `My Awesome App Setup 1.0.0.exe` for Windows).

### 3. Troubleshooting
- If the build fails, run `npm install` and `npx electron-builder --win` (for Windows) in the terminal, then check the output for errors.
- Ensure the icon file is valid and matches the platform requirements (`.ico` for Windows, `.icns` for macOS, `.png` for Linux).

### 4. Save and Load Configuration
- Use the **Save Configuration** button to export your settings as `electron-config.json`.
- Use the **Load Configuration** button to import a previously saved configuration (re-select folder and icon afterward).

### 5. Reset
- Click **Reset Selections** to clear all inputs and start fresh.

## Project Structure
The generated ZIP includes:
- `main.js`: Electron main process script.
- `preload.js`: Preload script for security.
- `package.json`: Project configuration with Electron and electron-builder dependencies.
- `build.bat`: Windows build script.
- `build.sh`: macOS/Linux build script.
- `build/` folder: Contains the app icon.
- Project files from the selected folder (e.g., `index.html`).

## Dependencies
- **Electron**: v37.4.0
- **electron-builder**: v26.0.12
- **JSZip**: v3.10.1 (for ZIP generation in the browser)
