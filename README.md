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

- 🔆 **Illuminance condition**: turn on/off the lights according to the 
    configured values.
- 🧑‍🤝‍🧑**Presence detection**: turn on/off the lights when the room becomes occupied
    or unoccupied.
- ⌛ **Delay on/off**: turn on/off lights only when the presence/absence lasts for
    a configurable amount of time.
- **Scene selection**: Rather than configuring lights through the Blueprint
    directly, uses **HA Scenes**. Using scripts is therefore not supported.
- **Prevent streaming mode interruptions**: Are you a fan of games with synced
    lights? I've got you covered. The automation won't trigger when any of the
    lights are in streaming mode. 
- **FUTURE** *Manual mode*: allow setting a manual mode, so that lights still go
    on/off but instead of resetting them, the previous values are kept. Example:
    you set bright lights in a room because you are studying. Once you go out of the
    room and come back, the lights go on at the same color and brightness as
    before, instead of the "default" scene.
- **FUTURE** *Multiple-area support*: Supports commanding sub-areas inside the
    same room (mostly for Aqara FP2) so that you can add additional behaviour to
    lights. Example: set the brightness of a wardrobe light to 100% when someone
    is there for X seconds.
- **FUTURE** *Energy saver*: dims the lights to a certain percentace immediately
    after the last person leaves the room.
- **FUTURE** *Auto-manual-mode*: This depends on whether it will be possible to
    detect a light change *not* triggered by the user in any way. If this is
    possible, I would make it so that any adjustment to the lights is kept until
    the room is left for a prolonged (configurable) amount of time. May conflict
    with the streaming-mode.

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