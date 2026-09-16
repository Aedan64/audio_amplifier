# TPA3110D2 Stereo Audio Amplifier

A custom stereo Class-D audio amplifier based on the Texas Instruments
TPA3110D2 amplifier IC. The board is intended to power two 4-ohm automotive
speakers as a desktop audio system.

> **Project status:** Schematic development and component selection.
> This design has not yet been manufactured or electrically tested.

## Design Goals

- Stereo audio output
- Approximately 15 W per channel into 4-ohm speakers
- 3.5 mm stereo audio input
- External DC power input
- LC output filters
- Adjustable or fixed amplifier gain
- Power-limit configuration
- Input and power-supply protection
- Compact PCB suitable for a desktop speaker enclosure

## Main Component

The amplifier is built around the Texas Instruments **TPA3110D2**, a
two-channel Class-D audio power amplifier.

Important features include:

- Two bridge-tied-load output channels
- Differential audio inputs
- Gain-selection pins
- Power-limit control
- Shutdown and mute functions
- Overtemperature, overcurrent, and undervoltage protection

See the [TPA3110D2 datasheet](docs/datasheets/tpa3110d2.pdf) for complete
electrical specifications.

## Target Specifications

| Parameter | Target |
|---|---:|
| Amplifier IC | TPA3110D2 |
| Number of channels | 2 |
| Speaker impedance | 4 ohms |
| Target output power | Approximately 15 W per channel |
| Audio input | 3.5 mm stereo jack |
| Power input | External DC supply |
| Output filtering | LC filter on each BTL output |
| PCB software | KiCad |

The final power-supply voltage and current rating will be documented after
the output-power calculations and component selections are finalized.

## Circuit Sections

The schematic is divided into the following sections:

1. DC power input and input protection
2. Power-supply filtering and decoupling
3. Left and right audio inputs
4. TPA3110D2 amplifier
5. Gain and power-limit configuration
6. LC output filters
7. Left and right speaker connectors

## Output Filters

Each amplifier output uses an LC low-pass filter to reduce switching-frequency
energy before the signal reaches the speaker.

Because the TPA3110D2 uses bridge-tied-load outputs, neither speaker terminal
is connected directly to ground.

Current planned filter components:

- Inductor: 22 uH
- Capacitors: 2.2uF
- Load: 4-ohm speaker

The capacitor values, voltage ratings, current ratings, and filter response
will be verified before PCB layout.

## Power Supply

The board will use an external regulated DC supply connected through a
dedicated power connector.

The following items must be finalized:

- Input voltage
- Required continuous current
- Connector type and polarity
- Fuse or resettable fuse
- Reverse-polarity protection
- Transient-voltage protection

## Opening the Project

1. Install a compatible version of [KiCad](https://www.kicad.org/).
2. Clone or download this repository.
3. Open `amplifier.kicad_pro`.
4. Use KiCad's Schematic Editor to inspect the circuit.
5. Use PCB Editor after footprints have been assigned.

KiCAD version 10.0.5

## Project Status

- [x] Select amplifier IC
- [x] Choose stereo 4-ohm configuration
- [x] Create initial schematic
- [x] Add power-limit voltage divider
- [x] Add LC output filters
- [x] Finalize power-input protection
- [ ] Select exact component part numbers
- [ ] Assign footprints
- [ ] Run KiCad Electrical Rules Checker
- [ ] Create PCB layout
- [ ] Run Design Rules Checker
- [ ] Generate manufacturing files
- [ ] Assemble prototype
- [ ] Test output power, noise, and temperature

## Testing Plan

Before connecting the final speakers, the prototype should be tested for:

- Correct power-supply polarity
- Supply current with no audio input
- DC voltage across each speaker output
- Shutdown and mute behavior
- Output waveform using a resistive dummy load
- Clipping level
- Output power
- Amplifier and inductor temperature
- Noise or oscillation at the speaker outputs

## Known Limitations

This project is under development. Component values, footprints, supply
requirements, and PCB layout may change. Do not treat the current design as a
tested production circuit.

## Documentation

- TPA3110D2 datasheet
- Schematic PDF
- Bill of materials
- PCB images
- Fabrication files
- Prototype test results

These documents will be added as the project progresses.

## Author

Aedan Lewis

Electrical Engineering student project.

## License

A license has not yet been selected.