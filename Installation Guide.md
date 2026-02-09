# 🚀 Flutter Installation Guide

A complete beginner-friendly guide to install Flutter on **Windows**, **Linux (Debian/Ubuntu)**, and **macOS**.

---

## 📋 Table of Contents

- [Prerequisites](#prerequisites)
- [Windows Installation](#-windows-installation)
- [Linux (Debian/Ubuntu) Installation](#-linux-debianubuntu-installation)
- [macOS Installation](#-macos-installation)
- [Verify Installation](#-verify-installation)
- [IDE Setup](#-ide-setup)
- [Troubleshooting](#-troubleshooting)

---

## Prerequisites

Before installing Flutter, ensure you have:

- **Stable internet connection** for downloading SDKs
- **At least 2.8 GB of disk space** (not including IDE/tools)
- **Git** installed on your system

---

## 🪟 Windows Installation

### Step 1: Install Git

1. Download Git from [git-scm.com](https://git-scm.com/download/win)
2. Run the installer and follow the setup wizard
3. Use all default options (just keep clicking **Next**)
4. Verify installation by opening **Command Prompt** and typing:
   ```cmd
   git --version
   ```

### Step 2: Download Flutter SDK

1. Go to [flutter.dev/docs/get-started/install/windows](https://docs.flutter.dev/get-started/install/windows)
2. Click the **Download Flutter SDK** button
3. Extract the downloaded `.zip` file to a location like:
   ```
   C:\flutter
   ```
   > ⚠️ **Important:** Do NOT install Flutter in `C:\Program Files\` (requires admin permissions)

### Step 3: Add Flutter to PATH

1. Press `Windows + S` and search for **"Environment Variables"**
2. Click **"Edit the system environment variables"**
3. Click the **Environment Variables** button
4. Under **User variables**, find and select **Path**, then click **Edit**
5. Click **New** and add:
   ```
   C:\flutter\bin
   ```
6. Click **OK** on all windows to save

### Step 4: Install Android Studio

1. Download Android Studio from [developer.android.com/studio](https://developer.android.com/studio)
2. Run the installer and follow the setup wizard
3. During installation, ensure these are checked:
   - ✅ Android SDK
   - ✅ Android SDK Platform
   - ✅ Android Virtual Device (AVD)
4. Complete the installation and launch Android Studio
5. Go to **More Actions** → **SDK Manager**
6. In the **SDK Tools** tab, ensure these are installed:
   - ✅ Android SDK Build-Tools
   - ✅ Android SDK Command-line Tools
   - ✅ Android Emulator
   - ✅ Android SDK Platform-Tools

### Step 5: Accept Android Licenses

Open **Command Prompt** and run:

```cmd
flutter doctor --android-licenses
```

Press `y` to accept all licenses.

---

## 🐧 Linux (Debian/Ubuntu) Installation

### Step 1: Install Required Dependencies

Open **Terminal** and run:

```bash
sudo apt update
sudo apt install -y curl git unzip xz-utils zip libglu1-mesa clang cmake ninja-build pkg-config libgtk-3-dev
```

### Step 2: Download Flutter SDK

**Option A: Using Git (Recommended)**

```bash
cd ~
git clone https://github.com/flutter/flutter.git -b stable
```

**Option B: Manual Download**

1. Go to [flutter.dev/docs/get-started/install/linux](https://docs.flutter.dev/get-started/install/linux)
2. Download the latest stable release
3. Extract to your home directory:
   ```bash
   cd ~
   tar xf flutter_linux_*.tar.xz
   ```

### Step 3: Add Flutter to PATH

1. Open your shell configuration file:

   ```bash
   nano ~/.bashrc
   ```

   > 💡 If you use **Zsh**, edit `~/.zshrc` instead

2. Add this line at the end of the file:

   ```bash
   export PATH="$HOME/flutter/bin:$PATH"
   ```

3. Save and exit (`Ctrl + X`, then `Y`, then `Enter`)

4. Apply the changes:
   ```bash
   source ~/.bashrc
   ```

### Step 4: Install Android Studio

1. Download Android Studio from [developer.android.com/studio](https://developer.android.com/studio)
2. Extract the downloaded file:
   ```bash
   cd ~/Downloads
   tar -xzf android-studio-*.tar.gz
   sudo mv android-studio /opt/
   ```
3. Launch Android Studio:
   ```bash
   /opt/android-studio/bin/studio.sh
   ```
4. Follow the setup wizard and install the recommended SDK components
5. Go to **More Actions** → **SDK Manager** → **SDK Tools** and install:
   - ✅ Android SDK Build-Tools
   - ✅ Android SDK Command-line Tools
   - ✅ Android Emulator
   - ✅ Android SDK Platform-Tools

### Step 5: Configure Android SDK Path

Add to your `~/.bashrc`:

```bash
export ANDROID_HOME=$HOME/Android/Sdk
export PATH=$PATH:$ANDROID_HOME/emulator
export PATH=$PATH:$ANDROID_HOME/tools
export PATH=$PATH:$ANDROID_HOME/tools/bin
export PATH=$PATH:$ANDROID_HOME/platform-tools
```

Apply changes:

```bash
source ~/.bashrc
```

### Step 6: Accept Android Licenses

```bash
flutter doctor --android-licenses
```

Press `y` to accept all licenses.

---

## 🍎 macOS Installation

### Step 1: Install Xcode Command Line Tools

Open **Terminal** and run:

```bash
xcode-select --install
```

Click **Install** when prompted.

### Step 2: Install Homebrew (if not installed)

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

### Step 3: Install Required Dependencies

```bash
brew install git
```

### Step 4: Download Flutter SDK

**Option A: Using Git (Recommended)**

```bash
cd ~
git clone https://github.com/flutter/flutter.git -b stable
```

**Option B: Manual Download**

1. Go to [flutter.dev/docs/get-started/install/macos](https://docs.flutter.dev/get-started/install/macos)
2. Download the latest stable release
3. Extract to your home directory:
   ```bash
   cd ~
   unzip flutter_macos_*.zip
   ```

### Step 5: Add Flutter to PATH

1. Determine your shell:

   ```bash
   echo $SHELL
   ```

2. Edit the appropriate config file:
   - For **Zsh** (default on newer macOS):
     ```bash
     nano ~/.zshrc
     ```
   - For **Bash**:
     ```bash
     nano ~/.bash_profile
     ```

3. Add this line:

   ```bash
   export PATH="$HOME/flutter/bin:$PATH"
   ```

4. Save and exit (`Ctrl + X`, then `Y`, then `Enter`)

5. Apply the changes:
   ```bash
   source ~/.zshrc   # or source ~/.bash_profile
   ```

### Step 6: Install Xcode (for iOS Development)

1. Open **App Store** and search for **Xcode**
2. Click **Get** and wait for installation (this takes a while, ~12 GB)
3. Open Xcode once to accept the license agreement
4. Run in Terminal:
   ```bash
   sudo xcodebuild -license accept
   sudo xcodebuild -runFirstLaunch
   ```

### Step 7: Install CocoaPods (for iOS)

```bash
sudo gem install cocoapods
```

### Step 8: Install Android Studio (for Android Development)

1. Download from [developer.android.com/studio](https://developer.android.com/studio)
2. Open the `.dmg` file and drag Android Studio to **Applications**
3. Launch Android Studio and follow the setup wizard
4. Go to **More Actions** → **SDK Manager** → **SDK Tools** and install:
   - ✅ Android SDK Build-Tools
   - ✅ Android SDK Command-line Tools
   - ✅ Android Emulator
   - ✅ Android SDK Platform-Tools

### Step 9: Accept Android Licenses

```bash
flutter doctor --android-licenses
```

Press `y` to accept all licenses.

---

## ✅ Verify Installation

After completing the installation for your platform, run:

```bash
flutter doctor
```

You should see output similar to:

```
Doctor summary (to see all details, run flutter doctor -v):
[✓] Flutter (Channel stable, 3.x.x)
[✓] Android toolchain - develop for Android devices
[✓] Xcode - develop for iOS and macOS (macOS only)
[✓] Chrome - develop for the web
[✓] Android Studio
[✓] VS Code
[✓] Connected device
[✓] Network resources

• No issues found!
```

> 💡 It's okay if some items show `[!]` or `[✗]` - you only need the tools for your target platform.

---

## 💻 IDE Setup

### Visual Studio Code (Recommended for Beginners)

1. Download VS Code from [code.visualstudio.com](https://code.visualstudio.com/)
2. Install the **Flutter** extension:
   - Open VS Code
   - Press `Ctrl + Shift + X` (Windows/Linux) or `Cmd + Shift + X` (macOS)
   - Search for **"Flutter"**
   - Click **Install** on the one by **Dart Code**
   - This automatically installs the **Dart** extension too

### Android Studio

1. Open Android Studio
2. Go to **File** → **Settings** (Windows/Linux) or **Android Studio** → **Preferences** (macOS)
3. Navigate to **Plugins**
4. Search for **"Flutter"** and click **Install**
5. Restart Android Studio

---

## 🔧 Troubleshooting

### Common Issues

| Issue                           | Solution                                              |
| ------------------------------- | ----------------------------------------------------- |
| `flutter: command not found`    | Restart your terminal or verify PATH is set correctly |
| Android licenses not accepted   | Run `flutter doctor --android-licenses`               |
| Android SDK not found           | Set `ANDROID_HOME` environment variable               |
| Xcode not found (macOS)         | Install Xcode from App Store                          |
| CocoaPods not installed (macOS) | Run `sudo gem install cocoapods`                      |

### Need More Help?

- 📖 Official Docs: [flutter.dev/docs](https://flutter.dev/docs)
- 💬 Community: [flutter.dev/community](https://flutter.dev/community)
- 🐛 Report Issues: [github.com/flutter/flutter/issues](https://github.com/flutter/flutter/issues)

---

## 🎉 You're Ready!

Create your first Flutter app:

```bash
flutter create my_first_app
cd my_first_app
flutter run
```

**Happy Coding! 🎯**
