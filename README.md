# Awesome Blackmagic Design [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

A curated list of amazingly awesome collection of lists, software, libraries, documentations, videos, tutorials and anything useful around Blackmagic Design products. 

## Official Developer Resources

- [Blackmagic Design Developer](https://www.blackmagicdesign.com/developer): Official developer portal, SDKs, sample code, and product protocol manuals.
- [ATEM SDK and Software](https://www.blackmagicdesign.com/developer/products/atem/sdk-and-software): Official ATEM Switchers SDK and documentation.
- [HyperDeck Ethernet Protocol](https://www.blackmagicdesign.com/developer/products/hyperdeck/sdk-and-software): Official text protocol for controlling HyperDeck recorders over TCP.
- [Videohub Ethernet Protocol](https://www.blackmagicdesign.com/developer/products/videohub/sdk-and-software): Official text protocol for controlling Videohub routers over the network.
- [Camera Control](https://www.blackmagicdesign.com/developer/products/camera/sdk-and-software): Official SDI/Bluetooth camera control protocol and Camera REST API manuals.
- [DeckLink / Desktop Video SDK](https://www.blackmagicdesign.com/developer/products/capture-and-playback/sdk-and-software): Official SDK for DeckLink, UltraStudio, and Intensity capture/playback devices. [Online docs](https://sdk-doc.blackmagicdesign.com/decklink-sdk/index.html).
- [Blackmagic Design Forum](https://forum.blackmagicdesign.com): Developer and product support forums.

## Protocol Docs and Reverse Engineerings

- [BMD ATEM switcher protocol by Skaarhoj](https://www.skaarhoj.com/discover/blackmagic-atem-switcher-protocol)
- [BMD Camera HDMI protocol](https://blog.brixit.nl/reverse-engineering-the-bmd-camera-hdmi-control/)
- [Blackmagic firmware reverse engineering](https://github.com/micolous/blackmagic-firmware-re): Tools (`libbmfw` / `bmfw`) for inspecting and extracting BMD firmware and gateware update packages (ATEM, Web Presenter, converters, and more).

## Libraries

### Communcating with ATEM mixers by Languages
- JavaScript: [Sofie ATEM Connection Library](https://github.com/nrkno/sofie-atem-connection), [Node Applest ATEM](https://github.com/applest/node-applest-atem), [ATEM](https://github.com/Dev1an/Atem)
- C#: [LibAtem](https://github.com/LibAtem/LibAtem)
- C++/Qt: [libqatemcontrol](https://github.com/petersimonsson/libqatemcontrol)
- Swift: [Swift ATEM](https://github.com/Dev1an/Swift-Atem)
- Arduino: [Arduino Libs by Skaarhoj](https://github.com/kasperskaarhoj/SKAARHOJ-Open-Engineering/tree/master/ArduinoLibs)
- Python: [PyATEMMax](https://github.com/clvLabs/PyATEMMax), [pyatem](https://git.sr.ht/~martijnbraam/pyatem) (OpenSwitcher)
- Go: [ATEM Go](https://github.com/mraerino/atem-go), [Go ATEM](https://github.com/bdogan/go-atem)
- Rust: [necromancer](https://github.com/micolous/necromancer)

### HyperDeck
- JavaScript: [Sofie HyperDeck Connection](https://github.com/Sofie-Automation/sofie-hyperdeck-connection), [Hyperdeck-JS-Lib](https://github.com/LA1TV/Hyperdeck-JS-Lib)
- Python: [pyperdeck](https://github.com/FlantasticDan/pyperdeck)

### Videohub
- [videohubctrl](https://github.com/gfto/videohubctrl): CLI to control Videohub SDI routers over the network.
- Python: [bmd_videohub](https://github.com/sohonetlabs/bmd_videohub)

### Fairlight
- Rust: [fairlight-live-rs](https://github.com/MikanseiLaboratory/fairlight-live-rs): Fairlight Live TCP protocol client (mixer control, project database).

### DeckLink / Capture and Playback
- JavaScript: [macadam](https://github.com/Streampunk/macadam): Async Node.js interface to DeckLink capture and playback devices.
- [bmdtools](https://github.com/lu-zero/bmdtools): Capture and play utilities for DeckLink.

### Testing
- [ATEM Connection Test Generator](https://github.com/LibAtem/atem-connection-test-generator): C# library to generate ATEM commands for unit tests

## Tools
- [wireshark-atem-dissector](https://github.com/peschuster/wireshark-atem-dissector): Wireshark dissector for Blackmagic Design ATEM video switcher protocol. 
- [ATEM Simulator](https://github.com/Dev1an/Atem-Simulator): Swift application that simulates an ATEM switcher for testing.
- [ATEM Image Auto Uploader](https://github.com/mintopia/atemlib): C# (Windows only) script to automate uploads to the media pool.
- [multiviewTouchControl](https://github.com/airbenich/multiviewTouchControl): Raspberry Pi multiview touch control for ATEM switchers.
- [ATEM Compositor](https://github.com/TipoftheHats/atem-compositor): Alternate UI for Super Sources.
- [H2R Layouts](https://layouts.heretorecord.com): Online alternate UI for Super Sources via macros.
- [OpenSwitcher](https://openswitcher.org): Linux alternate software controller for ATEM switchers.
- [($)MixEffect](https://mixeffect.app): PAID iOS app to controll ATEM switchers.
- [Bitfocus Companion](https://bitfocus.io/companion): Stream Deck and other control surfaces for ATEM and many other devices.
- [atemOSC](https://github.com/SteffeyDev/atemOSC) / [($)Banyan AVBridge](https://atemosc.com): Control ATEM (and HyperDeck) over OSC, MIDI, and HTTP.
- [SuperConductor](https://github.com/SuperFlyTV/SuperConductor): Cross-platform playout client that can control ATEM, CasparCG, OBS, vMix, and more.
- [ATEMWeb](https://github.com/roygdavis/ATEMWeb): REST API for ATEM switchers.
- [ATEM tally light (ESP8266)](https://github.com/AronHetLam/ATEM_tally_light_with_ESP8266): Wireless WiFi tally light for ATEM switchers.
- [wifi-tally](https://github.com/wifi-tally/wifi-tally): Affordable WiFi tally light (NodeMCU / ESP8266) with support for multiple mixers including ATEM.
- [TouchDesigner ATEM CHOP](https://github.com/camikura/touchdesigner-atem-chop): Control ATEM from TouchDesigner's CHOP operator.
- [Magic Pocket Control](https://github.com/marklysze/Magic-Pocket-Control-ESP32): BMD camera control on ESP32 devices (M5Stack, LILYGO, and others).
- [Unbound Editor Device Customizer](https://github.com/PuzzleEmptyM/Unbound-editor-device-customizer): Remap Blackmagic Speed Editor buttons without DaVinci Resolve.

### Bitfocus Companion modules
- [ATEM](https://github.com/bitfocus/companion-module-bmd-atem)
- [HyperDeck](https://github.com/bitfocus/companion-module-bmd-hyperdeck)
- [Videohub](https://github.com/bitfocus/companion-module-bmd-videohub)
- [Cameras](https://github.com/bitfocus/companion-module-bmd-cameras)
- [Web Presenter](https://github.com/bitfocus/companion-module-bmd-webpresenter)
- [SmartView](https://github.com/bitfocus/companion-module-bmd-smartview)
- [MultiView 4](https://github.com/bitfocus/companion-module-bmd-multiview4)
- [MultiView 16](https://github.com/bitfocus/companion-module-bmd-multiview16)
- [Ultimatte](https://github.com/bitfocus/companion-module-bmd-ultimatte)
- [Teranex](https://github.com/bitfocus/companion-module-bmd-teranex)
- [Teranex Mini](https://github.com/bitfocus/companion-module-bmd-teranex-mini)
- [Fairlight Live](https://github.com/bitfocus/companion-module-bmd-fairlight-live)
- [Audio Monitor](https://github.com/bitfocus/companion-module-bmd-audiomonitor)
- [GPI and Tally Interface](https://github.com/bitfocus/companion-module-bmd-gpi-and-tally-interface)

### Bitfocus Companion surfaces
- [Blackmagic Controller](https://github.com/bitfocus/companion-surface-blackmagic-controller): Use BMD hardware panels as Companion surfaces.
- [Videohub Panel](https://github.com/bitfocus/companion-surface-blackmagic-videohub-panel): Use Videohub control panels as Companion surfaces.

## DaVinci Resolve

- [DaVinci Resolve Scripting API (community copy)](https://gist.github.com/X-Raym/2f2bf453fc481b9cca624d7ca0e19de8): Readable copy of the official Lua/Python scripting README shipped with Resolve (`Help > Documentation > Developer`).
- [DCTLs](https://github.com/Demystify-Color/DCTLs): Free DCTL collection for DaVinci Resolve.

## Tutorials

- [Installing ATEM Software Controll on Linux](tutorials/atem-software-control-linux-instal.md)
