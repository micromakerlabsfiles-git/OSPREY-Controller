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

The Osprey Controller has **4 independent relay channels** that act as automatic switches. Think of each channel as a standard light switch that is turned on and off by the controller.

### Safety Guidelines:
- **Disconnect power** to all cables before making connections.
- The controller switches only **one leg** of the power line (usually the Live/Positive wire). The neutral or ground wires must bypass the controller and connect directly to your equipment.

### Connecting Peripherals:

#### Channel 1: Primary Spotlight / Main Ambient Light
- **Typical Use**: Heavy-duty lighting like spotlights or high-power stage lights.
- **Connection**:
  1. Cut the Positive/Live wire of the spotlight power cord.
  2. Insert one cut end into the Channel 1 terminal (marked Common/COM).
  3. Insert the other cut end into the Normally Open (NO) terminal.
  4. Plug the spotlight cord into the wall outlet.

#### Channel 2: Special Effects (Laser / Strobe)
- **Typical Use**: Laser projectors, visual strobe flashers, or patterns.
- **Connection**:
  1. Splice the hot line of the laser's power adapter.
  2. Run the hot line through the Channel 2 terminal block.
  3. Ground/Neutral lines must go directly from the wall outlet to the laser.

#### Channel 3: Fog Machine / Party Gear
- **Typical Use**: Smoke/fog generators, bubble machines, or atmospheric machines.
- **Connection**:
  1. Connect the remote-trigger or main power line of the fog machine through the Channel 3 terminal contacts.
  2. Activation of Channel 3 closes the contact, simulating pressing the manual button on a fog machine remote.

#### Channel 4: Secondary Light / Auxiliary Load
- **Typical Use**: Accent LED strips, background wash lights, or secondary projectors.
- **Connection**:
  1. Connect the Positive line of the low-voltage power supply (e.g., 12V DC adapter) through Channel 4.
  2. The negative line connects directly from the power supply to the LED strip.

---

## 3. Using the Web Controller Manager

The Web Controller is a visual, dual-theme control dashboard that runs in your web browser on both Desktop and Mobile (Android).

### Android Mobile & Desktop Compatibility:
- **Desktop**: Open in Google Chrome, Microsoft Edge, or Opera. Connect via USB cable.
- **Android Mobile**: Connect your microcontroller to your Android phone using a **USB-C OTG (On-The-Go) adapter**. Open the page in **Google Chrome** or **Opera**. The integrated Google WebSerial WebUSB polyfill will automatically bridge Web Serial requests over WebUSB.
- **iOS Note**: Apple iOS (iPhones / iPads) blocks WebSerial and WebUSB API access across all browsers due to WebKit security policies.

### Logging In & Connecting:
1. Plug the Osprey Controller into your computer or Android phone's USB port.
2. Open **[index.html](file:///f:/Codes/Osprey_controller/index.html)** in a compatible browser.
3. Click the **Connect Controller** button.
4. A browser popup will prompt you to select the connected USB device ("ESP32 USB" or USB serial bridge).
5. Once connected, the dashboard opens for configuration management.

### Logging Out & Disconnecting:
- Click **Disconnect** on the top header to close the serial port safely.
- **Auto-Logout Security**: If the physical USB cable or OTG connection is unplugged at any point, the dashboard automatically detects the disconnection and returns to the login screen.

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

