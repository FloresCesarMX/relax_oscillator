# Relaxation Oscillator

## How it works

This project implements a standard-cell relaxation oscillator based on the circuit described by Aiello. The oscillator and its timing elements are integrated on-chip, so no external timing capacitor or clock is required.

`ENABLE1` and `ENABLE2` are control inputs. The digital outputs are `Q` and `Qn`. Analog pins `C1` and `C2` expose internal nodes for observation.

## How to test

Power the chip and use an oscilloscope to measure its outputs. No external timing components or clock are required.

Analog measurements at `C1` and `C2` may be affected by the Tiny Tapeout analog multiplexer and pad parasitics, which can reduce or distort the observed amplitude. Use the digital outputs as the primary signals for measuring the oscillation period.

### Required equipment
- An oscilloscope and suitable probes.

### Test procedure

1. Power the chip using the board's specified supply configuration. The project has `uses_3v3: false` and requires no external clock.
2. Set `ENABLE1` (`UI[0]`) and `ENABLE2` (`UI[1]`) to the active logic levels defined in the Xschem schematic, using the board's input controls if needed.
3. Measure the digital outputs `Q` (`UO[0]`) and `Qn` (`UO[1]`) with the oscilloscope.
4. Optionally observe internal analog nodes `C1` (`UA[0]`) and `C2` (`UA[1]`). Their measured waveforms may be affected by the analog multiplexer and pad parasitics.
5. Measure the output period and calculate the frequency as `f = 1/T`.
6. Record the supply configuration, enable states, measured period or frequency, output amplitude, and measurement setup. Save an oscilloscope capture as evidence.

## External hardware

No external timing components are required.


## Pin map

| Pin | Name | Purpose |
|---|---|---|
| `UI[0]` | `ENABLE1` | Oscillator control input 1. |
| `UI[1]` | `ENABLE2` | Oscillator control input 2. |
| `UO[0]` | `Q` | Digital oscillator output. |
| `UO[1]` | `Qn` | Complementary digital oscillator output. |
| `UA[0]` | `C1` | Analog timing-capacitor node 1. |
| `UA[1]` | `C2` | Analog timing-capacitor node 2. |

