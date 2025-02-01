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


## Use-cases

So far, this Blueprint has very basic use-cases. It does not take into account
the presence of guests, or of someone sleeping. Those are going to be there in
the future, as I get the time to implement those functions for my own home.

The best use-cases are so far:

- Rooms where no one sleeps
- Rooms that don't need multi-zone settings (as the Area feature is not yet
    implemented)
- Rooms that need more than one presence-sensor (it probably would not be hard
    to introduce, but it is not a use-case I need)
- Rooms with no special logic needed as of which scene to activate based on time
    or condition. (this also may be introduced at some point in time, but at
    the moment I feel like my knowledge of HA is not enough to implement this
    in a usable way in a Blueprint)

## Supported Devices with "special" features

I can provide support only for devices that I own, because I need to be able to
test changes, as I am a user of the BP myself. In theory, any device that has
a HA entity should work, but some checks are device-specific. In this BP those
devices have custom checks:

- Nanoleaf Blocks (streaming mode detection)
- Philips HUE lights (streaming mode detection)

## When will this be released?

I will release the Blueprint with proper versioning when I feel it doesn't get
on my way for the type of automation I want to achieve.