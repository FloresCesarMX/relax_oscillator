Relaxation Oscillator for Tiny Tapeout

A standard-cell-based relaxation oscillator designed from the circuit presented in Orazio Aiello's paper. The circuit uses an external timing capacitor to set its oscillation frequency. The schematic was captured in **Xschem**, and the physical layout was created in **Magic**.

## Overview

This repository contains the design files and documentation for a relaxation oscillator implemented with standard-cell logic. The project follows the relaxation-oscillator approach described in the reference paper and adapts it to the project's target process and Tiny Tapeout analog/custom design flow.

The external timing capacitor controls the circuit's charging and discharging time and therefore affects the output period and frequency. The repository is organized to make the schematic, physical layout, integration files, and verification evidence reviewable.

## Academic Motivation

Relaxation oscillators are useful in systems that need a periodic timing signal. Aiello's work shows how standard digital cells can be arranged to perform this traditionally analog function. This project implements that relaxation-oscillator concept and documents its schematic and physical realization.

Reference: Orazio Aiello, “On Standard Cell-Based Design for Dynamic Voltage Comparators and Relaxation Oscillators,” *Chips*, 2025, 4(3), 31. [https://doi.org/10.3390/chips4030031](https://doi.org/10.3390/chips4030031).

## Project Objectives

- Implement the paper's relaxation-oscillator concept using standard-cell logic.
- Capture and review the circuit schematic in Xschem.
- Create the physical layout in Magic for the target Tiny Tapeout flow.
- Use an external capacitor as the timing element that sets the oscillation frequency.

## Project Summary

| Item | Description |
|---|---|
| Design | Standard-cell-based relaxation oscillator |
| Reference | Aiello, *Chips* (2025), 4(3), 31 |
| Schematic capture | Xschem |
| Physical layout | Magic |
| Timing element | External capacitor |
| Target flow | Tiny Tapeout analog/custom flow |
| Institution | Universidad Autónoma de Baja California (UABC) |
| Process / PDK | [SKY130] |

## Design Concept

The oscillator uses a feedback network made from standard-cell logic. A timing capacitor connected to the designated circuit nodes charges and discharges as the logic state changes. This repeated transition produces a periodic, non-sinusoidal output. Changing the external capacitance changes the timing behavior; the exact frequency depends on the implemented circuit, process, loading, and measurement setup.

The circuit connections, capacitor terminals, enable signals, and output pin must match the version in the Xschem schematic and the Tiny Tapeout pin configuration. See [`info.yaml`](info.yaml) before wiring the chip.

## Design Methodology

The project follows a schematic-to-layout workflow:

1. **Schematic capture:** Create and inspect the oscillator circuit in Xschem.
2. **Physical implementation:** Build the standard-cell layout in Magic.
3. **Export:** Save the physical design collateral, including the GDS and LEF files used by the project flow.
4. **Review and verification:** Check the schematic, layout, and available test files. Record simulation results and measurements from fabricated silicon as separate results.

## Layout Strategy

The physical design was created in Magic using the standard-cell structures available in the target process. The editable Magic files are kept in `mag/`; exported physical collateral is kept in `gds/` and `lef/`. The GDS should be reviewed together with the corresponding schematic and project configuration.

## Supporting Tools

- **Xschem:** schematic capture and circuit review.
- **Magic:** physical layout and layout review.
- **Tiny Tapeout project flow:** project integration and configuration.

## Repository Structure

- `src/` — source and project integration files.
- `mag/` — Magic layout files.
- `gds/` — exported GDS files.
- `lef/` — LEF abstracts, if used by the integration flow.
- `test/` — project test and verification files.
- `docs/` — project notes and supporting documentation.
- `info.yaml` — Tiny Tapeout project metadata and pin configuration.


## Key Takeaways

- The project implements a standard-cell relaxation oscillator based on Aiello's published circuit.
- Xschem was used for the schematic, and Magic was used for the physical layout.
- An external capacitor provides the timing element and affects the oscillation frequency.
- The repository is intended to document the circuit, its physical implementation, and how it was verified.

## Project Team

- Glauber Abril Arce
- Daniela Aguirre Luque
- Lizeth Nayely Alvarez Villegas
- Dayra Jareth Campos Correa
- Ruth Angelina Clemente Gonzalez
- José Martín Estrada Mendoza
- Monserrat Estela Garcia Gallardo
- Julian Gonzalez Reynaga
- Daniela Michelle Gonzalez Silva
- Victor Fernando Mendoza Valenzuela
- Yahir Joel Montaño López
- Juan Núñez Acosta
- Edgar Javier Ontiveros Lopez
- Cesar Daniel Flores Franco
- Alejandro Valdez Sanchez

**Project supervisor:** Dr. José Luis Valtierra Sánchez de la Vega

**Institution:** Universidad Autónoma de Baja California (UABC)

## Acknowledgment

This project was developed at the Universidad Autónoma de Baja California (UABC) under the academic supervision of Dr. José Luis Valtierra Sánchez de la Vega. The oscillator concept is based on the work cited below.

## Reference

Aiello, O. “On Standard Cell-Based Design for Dynamic Voltage Comparators and Relaxation Oscillators.” *Chips* 4, no. 3 (2025): 31. [https://doi.org/10.3390/chips4030031](https://doi.org/10.3390/chips4030031).

<img width="1342" height="596" alt="image" src="https://github.com/user-attachments/assets/95688a29-96b0-47f9-b59b-195226c7c138" />
