# Relaxation Oscillator

## How it works

This project implements a standard-cell relaxation oscillator based on the circuit described by Aiello. External timing capacitance connected to the `C1` and `C2` nodes affects the charging and discharging time, and therefore the oscillation frequency. The design does not require an external clock (`clock_hz: 0`).

`ENABLE1` and `ENABLE2` control the oscillator. Its digital outputs are `Q` and `Qn`. Analog pins `C1` and `C2` expose the timing nodes. Connect the external capacitor or capacitors as shown in the Xschem schematic.

## How to test

### Required equipment

- A compatible Tiny Tapeout test board for the project's 1x2 analog tile.
- The external timing capacitor or capacitors, connected as shown in the Xschem schematic.
- An oscilloscope and suitable probes for observing the digital outputs and analog timing nodes.

### Test procedure

1. Insert the chip into a compatible Tiny Tapeout test board and use the board's specified supply configuration. The project has `uses_3v3: false` and does not require an external clock.
2. Connect the timing capacitor or capacitors to `C1` and `C2` as shown in the Xschem schematic. These nodes are available at analog pins `UA[0]` and `UA[1]`.
3. Set `ENABLE1` (`UI[0]`) and `ENABLE2` (`UI[1]`) to the active logic levels specified by the schematic.
4. Use the oscilloscope to observe `Q` (`UO[0]`) and `Qn` (`UO[1]`). If the test setup permits, also observe `C1` and `C2` at the analog pins.
5. Record the supply configuration, capacitor connection, enable states, output frequency, output amplitude, and measurement setup. Save an oscilloscope capture as experimental evidence.

Use the project pin configuration in `info.yaml` together with the Xschem schematic when preparing the board connections.

## Pin map

| Pin | Name | Purpose |
|---|---|---|
| `UI[0]` | `ENABLE1` | Oscillator control input 1. |
| `UI[1]` | `ENABLE2` | Oscillator control input 2. |
| `UO[0]` | `Q` | Digital oscillator output. |
| `UO[1]` | `Qn` | Complementary digital oscillator output. |
| `UA[0]` | `C1` | Analog timing-capacitor node 1. |
| `UA[1]` | `C2` | Analog timing-capacitor node 2. |

## External hardware

- Tiny Tapeout test board compatible with this shuttle.
- External timing capacitor or capacitors connected as shown in the Xschem schematic.
- Oscilloscope and suitable probes.
