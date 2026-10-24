# Buck Converter PCB Design Using KiCad

## Overview

This project is a custom PCB design for a **DC-DC buck converter** that steps down a higher DC input voltage to a regulated **5 V output**. The design was created in KiCad, from the circuit schematic through PCB layout and 3D visualization.

The circuit uses an **LM2576HVS-5** fixed 5 V buck regulator, along with an inductor, Schottky diode, input/output capacitors, and an output indicator LED.

> **Note:** The schematic and PCB screenshots document the design process. Confirm the regulator's datasheet requirements, component ratings, footprint pin mapping, and PCB clearances before manufacturing or powering the board.

## Project Features

- Custom schematic capture in KiCad.
- Single-sided top-layer routing shown in the PCB layout.
- Screw-terminal connectors for DC input and 5 V output.
- Input and output filtering capacitors.
- Inductor and Schottky freewheeling diode for the buck-converter power stage.
- LED output indicator with a series current-limiting resistor.
- 3D PCB visualization for checking component placement and board appearance.

## Design Specifications

| Parameter | Design detail |
|---|---|
| Converter topology | Buck (step-down) DC-DC converter |
| Regulator IC | LM2576HVS-5 |
| Intended output | 5 V DC |
| Switching inductor | 100 µH (as shown in schematic) |
| Input capacitor | 100 µF (as shown in schematic) |
| Output capacitor | 100 µF (as shown in schematic) |
| Output indicator | LED with 220 Ω series resistor |
| Input connector | 2-pin screw terminal |
| Output connector | 2-pin screw terminal |
| CAD tool | KiCad |
| PCB views | Layout and 3D viewer |

**Input voltage and maximum output current:** Not specified in the screenshots. Select these from the regulator datasheet and the ratings of the diode, inductor, capacitors, connectors, and PCB traces before use.

## Circuit Operation

1. **Input supply:** DC power enters through the input screw terminal.
2. **Input filtering:** The input capacitor helps reduce supply ripple and transient disturbances.
3. **Buck conversion:** The LM2576HVS-5 switching regulator controls energy transfer through the inductor.
4. **Freewheeling path:** The Schottky diode provides a current path for the inductor when the regulator's internal switch is off.
5. **Output filtering:** The output capacitor helps smooth the converted voltage.
6. **Output connection:** The regulated output is available at the output screw terminal.
7. **Power indication:** The LED and 220 Ω resistor indicate the presence of output voltage, subject to correct polarity and wiring.

## Main Components

| Reference | Component | Value / part shown | Purpose |
|---|---|---|---|
| U1 | Buck regulator | LM2576HVS-5 | Regulates the output to 5 V |
| L1 | Inductor | 100 µH | Stores and transfers energy during switching |
| D1 | Schottky diode | Schottky type | Provides the freewheeling current path |
| C1 | Input capacitor | 100 µF | Input filtering |
| C2 | Output capacitor | 100 µF | Output filtering |
| D2 | LED | Value not specified | Output power indication |
| R1 | Resistor | 220 Ω | Limits LED current |
| J1 | 2-pin screw terminal | Input | DC input connection |
| J2 | 2-pin screw terminal | Output | 5 V output connection |

Component voltage ratings, current ratings, tolerance, ESR, package, and exact diode part number should be selected or verified against the datasheet and the intended operating conditions.

## PCB Design

The PCB layout places the regulator, inductor, diode, capacitors, indicator LED, resistor, and input/output terminals on a compact board.

Layout considerations for a switching regulator include:

- Keep high-current switching loops short and compact.
- Place the input bypass capacitor close to the regulator's input and ground pins.
- Keep the diode, regulator switch node, and inductor connections short.
- Use suitably wide copper tracks for input, output, and ground current.
- Keep the feedback connection away from noisy switching nodes and route it as recommended by the datasheet.
- Check copper clearances, thermal performance, mounting, and connector polarity before fabrication.

The screenshots show a PCB layout and a 3D preview. They are useful for reviewing placement and appearance, but they do not by themselves confirm electrical correctness or thermal suitability.

## Design Workflow

1. Draw the circuit schematic in KiCad.
2. Assign footprints to the components.
3. Transfer the components to the PCB editor.
4. Arrange components and define the board outline.
5. Route the nets and inspect track widths and clearances.
6. Run the Electrical Rules Checker (ERC) and Design Rules Checker (DRC), then resolve all relevant errors.
7. Inspect the 3D model for component orientation, footprint alignment, and connector placement.
8. Generate manufacturing files only after reviewing the schematic, layout, and component datasheets.

## Validation Checklist

Before ordering or powering the PCB:

- [ ] Verify the LM2576HVS-5 pinout against the exact package datasheet.
- [ ] Confirm that the input voltage is within the regulator's permitted range.
- [ ] Verify the Schottky diode's polarity, reverse-voltage rating, and current rating.
- [ ] Verify the inductor's saturation current, current rating, and inductance.
- [ ] Confirm capacitor polarity, voltage rating, capacitance, and required ESR.
- [ ] Check the feedback pin connection and output voltage path against the reference circuit.
- [ ] Confirm connector pin numbering and positive/ground markings.
- [ ] Run KiCad ERC and PCB DRC and resolve relevant violations.
- [ ] Inspect copper width, thermal reliefs, clearances, and component footprints.
- [ ] Perform initial power-up with a current-limited bench supply and measure the output before connecting a load.

## Repository Contents

Suggested repository structure:

```text
buck-converter/
├── README.md
├── schematic/
│   └── buck_converter.kicad_sch
├── pcb/
│   └── buck_converter.kicad_pcb
└── images/
    ├── schematic.png
    ├── pcb-layout.png
    └── pcb-3d.png
```

Update the filenames and folders to match the files actually included in the repository. Add exported screenshots to `images/` if you want them displayed in this README.

## Skills Demonstrated

- Schematic capture and PCB layout using KiCad
- Component and footprint selection
- Routing and PCB design-rule checking
- Understanding of a switching buck-converter power stage
- Connector placement, polarity marking, and 3D board inspection
- Hardware design documentation

## Disclaimer

This README describes the design shown in the project screenshots. Actual performance, output regulation, current capability, and safety have not been established by the screenshots alone. Verify the design and test it under controlled conditions before connecting it to any equipment.

## Author

**Ashutosh K. Undure**  
Electronics and Communication Engineering | Embedded Systems and PCB Design
