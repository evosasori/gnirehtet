# Gnirehtet - Reverse USB Tethering for Arch Linux

Share your computer's internet connection with your Android device through USB using Rust-based Gnirehtet.

Based on the original project: [Genymobile/gnirehtet](https://github.com/Genymobile/gnirehtet)

## Debian Base
### Prerequisites

- Debian Linux system
- Android device with USB debugging capabilities
- USB cable

### Installation
#### 1. Install Required Dependencies

```bash
# Install dependensi
sudo apt install android-tools-adb android-tools-fastboot -y
```
#### 2. Clone and Build

```bash
# Clone the repository
git clone https://github.com/Genymobile/gnirehtet
cd gnirehtet

```
## Arch Base
### Prerequisites

- Arch Linux system
- Android device with USB debugging capabilities
- USB cable

### Installation

#### 1. Install Required Dependencies

```bash
# Install Rust compiler
sudo pacman -S rust

# Install Android debugging tools
sudo pacman -S android-tools
```

#### 2. Clone and Build

```bash
# Clone the repository
git clone https://github.com/evosasori/gnirehtet.git
cd gnirehtet

# Build the project (if needed)
cargo build --release
```

## Setup

### 3. Enable USB Debugging on Android

1. Go to **Settings** → **About phone**
2. Tap **Build number** 7 times to enable Developer options
3. Go to **Settings** → **Developer options**
4. Enable **USB debugging**

### 4. Connect and Verify Device

```bash
# Connect your Android device via USB
# Verify ADB can detect your device
adb devices
```

You should see your device listed. If prompted on your phone, allow USB debugging.

## Usage

### 5. Install Gnirehtet APK

```bash
# Install the Gnirehtet app on your Android device
gnirehtet install
```

### 6. Start Reverse Tethering

```bash
# Begin sharing your computer's internet connection
gnirehtet run
```

Your Android device should now use your computer's internet connection.

## Troubleshooting

### Connection Issues

If the connection drops or becomes unstable:

```bash
# Restart the reverse tethering connection
gnirehtet restart
```

### Common Problems

- **Device not detected**: Ensure USB debugging is enabled and you've authorized the computer on your phone
- **Permission denied**: Try running commands with `sudo` if needed
- **Connection unstable**: Use a high-quality USB cable and avoid USB hubs

## Optional: Desktop Integration

Create a desktop entry for easy access:

```bash
sudo nano /usr/share/applications/gnirehtet.desktop
```

Add the following content (adjust the `Exec` path to match your gnirehtet installation):

```ini
[Desktop Entry]
Name=Gnirehtet
Comment=Reverse USB Tethering
Exec=/path/to/gnirehtet run
Icon=network-wired
Terminal=true
Type=Application
Categories=Network;System;
```

## Commands Reference

| Command | Description |
|---------|-------------|
| `gnirehtet install` | Install APK on connected device |
| `gnirehtet run` | Start reverse tethering |
| `gnirehtet restart` | Restart the connection |
| `adb devices` | List connected Android devices |

## License

This project maintains the same license as the original Gnirehtet project.

## Contributing

Issues and pull requests are welcome. Please ensure your contributions follow the project's coding standards.
