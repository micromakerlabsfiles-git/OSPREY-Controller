# Osprey Controller - Readme & Operator Guide

Welcome to the **Osprey Controller**! This guide is written for everyday operators. It explains how to interact with the device, connect external equipment safely, and use the Web Controller manager to customize your setup.

---

## 1. Operating the Device

The Osprey Controller features a single tactile touch sensor and a high-contrast screen.

### Navigation Shortcuts:
- **Short Tap (Quick Touch)**: Advance to the next menu option. The selection will scroll and highlight the new mode on the screen.
- **Double Tap (Two Quick Touches)**: In Manual Modes (e.g. MANUAL CH 1, 2, 3, 4), double-tapping toggles the highlighted channel relay **ON** or **OFF**.
- **Long Press (Hold for 1.0 second)**: Immediately activate **STANDBY OFF** from any state. The screen will beep twice to confirm, and all relay outputs will shut off instantly.

### Manual Channel Control & Visual Status:
- **Visual Relay Status**:
  - **White Background + Black Text**: The highlighted manual channel is currently **ACTIVE (ON)**.
  - **Black Background + White Text**: The highlighted manual channel is currently **INACTIVE (OFF)**.
- **Multi-Channel Manual Persistence**: When you turn ON a manual channel (e.g., MANUAL CH 1) and navigate to another manual channel (e.g., MANUAL CH 2), Channel 1 **remains ON**. You can double-tap Channel 2 to turn it ON as well, allowing multiple manual channels to run simultaneously.
- **Safety Auto-Shutoff**: Navigating to **STANDBY OFF** or any **Auto Mode** (Modes 1–6) will automatically shut off all active manual relays.

### Relays Activation Delay (Auto Modes):
- When you select a new **Auto Mode**, the controller will wait **2 seconds** before turning the relays on. This safety delay allows you to scroll past multiple options without turning equipment on and off rapidly. Holding your finger on the touch sensor pauses the delay so relays stay off while navigating.

---

## 2. Connecting Equipment to the Relay Channels

The Osprey Controller features **4 independent high-capacity relay channels** (Channel 1 through Channel 4) designed for safe AC or DC electrical load switching.

### Relay Electrical Specifications:
- **Relay Model**: DC5V High-Performance Relays
- **AC Load Ratings**: 250V AC @ 10A / 125V AC @ 12A (50/60 Hz)
- **DC Load Ratings**: 30V DC @ 10A
- **Coil Voltage**: 5V DC
- **Contact Type**: SPDT / Dry Contact switching via Common (COM) and Normally Open (NO) / Normally Closed (NC) screw terminals.

### Wiring & Safety Guidelines:
- **Disconnect Power**: Always disconnect line power before connecting or adjusting terminal wire connections.
- **Single Leg Switching**: The relay switches only **one leg** of the power line (usually the Live / Positive wire). Neutral, ground, or return lines must bypass the controller and connect directly to your equipment.
- **Current Limits**: Ensure the load connected to any individual channel does not exceed **10A**.

### Generic Channel Wiring Steps:
1. Identify the Live / Positive power lead of your electrical load.
2. Connect one cut lead into the **Common (COM)** terminal of the designated Relay Channel (CH 1–4).
3. Connect the second lead into the **Normally Open (NO)** terminal of the same channel.
4. When the Osprey Controller activates the channel, the internal relay contacts close to complete the power circuit.

---

## 3. Using the Web Controller Manager

The Web Controller is a visual, dual-theme control dashboard that runs in your desktop web browser.

### Browser Compatibility:
- **Supported Desktop Browsers**: Open in **Google Chrome**, **Microsoft Edge**, or **Opera** on Windows, macOS, or Linux. Connect via standard USB cable.

### Logging In & Connecting:
1. Plug the Osprey Controller into your computer's USB port.
2. Open the Web Manager at **[OSPREY Web Controller](https://micromakerlabsfiles-git.github.io/OSPREY-Controller/)** in a compatible desktop browser.
3. Click the **Connect Controller** button.
4. A browser popup will prompt you to select the connected USB device ("ESP32 USB" or USB serial bridge).
5. Once connected, the dashboard opens for configuration management.

### Logging Out & Disconnecting:
- Click **Disconnect** on the top header to close the serial port safely.
- **Auto-Logout Security**: If the physical USB cable is unplugged at any point, the dashboard automatically detects the disconnection and returns to the login screen.

### Theme & Layout Customization:
- **Theme Toggle**: Click the circular toggle button in the header to switch between **Dark Mode** and **Light Mode**.
- **Controller Name (Boot Text)**: Type a custom title (up to 32 characters). This text will type out character-by-character on boot.
- **Channel Labels**: Rename channels (e.g. "CH 1" to "SPOTLIGHT").
- **Menu Layout Style**:
  - *Horizontal Flipper*: Displays the selected mode centered in a card with left/right navigation arrows.
  - *Vertical Carousel*: Displays three modes vertically with selection borders.
- **Device Font Family**: Toggle screen text look between Helvetica, Monospace, and Profont.

### Dynamic Menu Options Editor:
- **Reordering**: Use the **Up** and **Down** buttons to move options.
- **Deleting**: Click **Delete (✕)** next to any mode.
- **Adding Options**: Restore deleted modes via the "Add Mode" dropdown.

### Saving Your Settings:
- Click **Save & Sync** to persist configuration into flash memory (NVS).
- Click **Read Config** to fetch current board settings.
- Click **Reset Defaults** to restore factory default configuration.
