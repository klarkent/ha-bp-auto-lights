# Auto Lights Automation Blueprint for Home Assistant

Blueprint that will control lights in a room, using one presence sensor and an
illuminance sensor to decide when lights are to be turned on or off. Supports
more conditions to turn lights on/off (see Features).

![Blueprint Automation Settings](images/chrome-capture-2025-1-31.gif)

> [!CAUTION]
> Pre-release version. There is definitely trash in the BP, features will change without notice, no versioning is available until release.
Use at your own risk ;)

## Features

I created this BP because I was unhappy with Node-Red and with the default
automation flow in HA. I wanted something that can be configured and that then
"just works". Here's what I implemented:

- 🔆 **Illuminance Control**: Automatically turns lights on or off based on
  configured brightness thresholds.  
- 🧑‍🤝‍🧑 **Presence Detection**: Activates or deactivates lights when the room
  becomes occupied or vacant.  
- ⌛ **Adjustable Delay**: Ensures lights change state only after presence or
  absence has been detected for a set duration.  
- 🎭 **Scene-Based Control**: Uses **Home Assistant Scenes** instead of direct
  light configuration. Script-based control is not supported.  
- 🎮 **Streaming Mode Protection**: Prevents automation from interrupting lights
  when they are in streaming mode—perfect for synced gaming or ambient lighting
  setups.  
- ✋ **Manual Mode**: Retains previous brightness and color settings instead of
  resetting to a default scene. Example: If you set bright lights for studying,
  they’ll stay that way when you leave and return.  
- 🔜 **Future: Multi-Area Support**: Enables finer control within a single room
  (e.g., with Aqara FP2), allowing custom behaviors like increasing wardrobe
  light brightness when someone is nearby for a set time.  
- 🔜 **Future: Energy Saver**: Automatically dims lights when the last person
  leaves the room.  
- 🔜 **Future: Auto-Manual Mode**: If detecting *non-user-triggered* light
  changes becomes possible, adjustments will persist until the room is vacant
  for a configurable duration. This may conflict with streaming mode.  

## 📌 Use Cases  

Currently, this blueprint covers basic automation needs. It does not yet account for guest presence or sleeping detection, but these features are planned for future updates as I implement them in my own home.  

### ✅ Best Use Cases So Far:  
- **Rooms where no one sleeps** – Ideal for living rooms, hallways, or workspaces.  
- **Rooms that don’t require multi-zone settings** – The area-based feature is not yet implemented.  
- **Rooms with multiple presence sensors** – While support for multiple sensors isn't difficult to add, I haven’t needed this functionality yet.  
- **Rooms with simple scene activation logic** – This blueprint does not yet handle scene selection based on time or other conditions, but I may introduce it in the future once I gain more expertise in Home Assistant.  

## 🛠️ Supported Devices with Special Features  

I can only provide support for devices that I personally own, as I need to test changes myself. In theory, any device with a Home Assistant entity should work, but some checks are device-specific. This blueprint currently includes custom checks for:  

- **Nanoleaf Blocks** – Streaming mode detection  
- **Philips Hue Lights** – Streaming mode detection  

## 🚀 Release Plans  

I will release this blueprint with proper versioning once it works seamlessly for my own automation needs. Until then, updates will be ongoing as I refine and expand its capabilities.

## 🛠 Installation

If you feel adventurous, you can import this Blueprint in your HA setup by
clicking on button below:

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2Fklarkent%2Fha-bp-auto-lights%2Frefs%2Fheads%2Fmain%2Froom_light_automation.yaml)