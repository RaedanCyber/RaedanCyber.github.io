# Automotive Central-Locking Relay Board Reverse Engineering

**Category:** Electronics / embedded systems / reverse engineering  
**Status:** Bench validation achieved; programmable Arduino GPIO integration and final application testing pending  
**Public portfolio page:** https://raedancyber.github.io/projects/automotive-relay-reverse-engineering.html

## Objective

Repurpose a salvaged automotive central-locking PCB into a dual-relay module with independent 5V microcontroller control. The original eight-pin harness and schematic were unavailable.

## Hardware

- Two LARM RY-15-I electromechanical relays (rated coil voltage not independently confirmed from markings)
- Two C1815 GR-marked NPN devices, consistent with the 2SC1815 transistor family
- Discrete resistors and steering/flyback diodes, two 16V-marked electrolytic capacitors
- Eight-pin connector adapted to an eight-wire breakout harness
- 13V battery, multimeter, Arduino Uno 5V supply, multiple 220Ω resistors

## Method

1. Compared component-side and solder-side photographs and preserved consistent connector numbering.
2. Used unpowered continuity to map copper nets and relay resting contacts.
3. Read transistor markings and checked pinout against datasheet; measured an approximately 0.6V base-emitter diode reading on Q1.
4. Traced SD3 and SD4 shared banded nodes and separate unbanded connections to transistor collectors and relay terminals.
5. Applied current-limited battery power to each relay-coil circuit; changed resistor network only after voltage observation.
6. Checked upper relay contact switching using DC voltage measurements.
7. Established that Q1 and Q2 emitters route to connector pins 6 and 5 respectively.
8. With common ground, exercised both transistor-controlled relays using a series-resistor-limited 5V input from the Arduino supply pin.

## Verified observations

| Test | Result |
|---|---|
| Resting contact continuity | Pins 2, 3, and 4 interconnected at rest |
| SD3 and SD4 cathodes | Continuity between banded ends |
| Upper SD3 anode | Connected to Q1 collector (middle leg) |
| Lower SD4 anode | Connected to Q2 collector (middle leg) |
| Coil with 1,100Ω series limiting | ~1.8–1.9V; no click |
| Coil with 440Ω series limiting | ~3.8V; no click |
| Coil with three 220Ω in parallel (~73Ω) | ~9.2V; both relays clicked in individual tests |
| Upper relay output pin 3 | ~0V OFF, ~10V ON under current-limited test |
| Q1 emitter | Pin 6 |
| Q2 emitter | Pin 5 |
| 5V base-drive experiment | Both relays actuated independently through their existing transistors with a 440Ω series base resistor |

## Connector map (reverse-engineered, not manufacturer-confirmed)

| Pin | Function | Evidence |
|---|---|---|
| 1 | Shared NO-side rail | Inferred from traces and upper contact behaviour |
| 2 | Shared NC-side rail | Resting continuity; exact contact labels inferred |
| 3 | Upper switched/common output | Verified voltage change |
| 4 | Lower switched/common output | Inferred; ON-state contact measurement outstanding |
| 5 | Q2 emitter | Continuity |
| 6 | Q1 emitter | Continuity |
| 7 | SD6 banded/cathode-side connection | Continuity; external purpose not established |
| 8 | SD2 banded/cathode-side connection | Continuity; external purpose not established |

## What remains

- Validate programmable Arduino GPIO D8/D9 operation using individual base resistors. The successful test was from Arduino 5V, *not* GPIO firmware.
- Independently confirm lower relay contact output transitions.
- Establish final protected coil supply / fuse sizing; temporary test resistors do not substitute for a permanent protection design.
- Before use with speakers: verify both are on a compatible *single* amplifier output, check parallel load impedance, and avoid combining separate amplifier channels with shared relay rails.
- Add full annotated board images and a measured complete schematic.

## Engineering caution

Do not connect 12–13V battery voltage to Arduino GPIO or assume every numbered pin is an isolated relay contact. The board has shared contact rails. Continuity, diode readings and current-limited bench observations are recorded separately from inferred circuit topology.

## Component reference

2SC1815 family datasheet (device marking C1815 GR; actual manufacturer's stamping not independently authenticated): https://media.digikey.com/pdf/Data%20Sheets/Toshiba%20PDFs/2SC1815.pdf
