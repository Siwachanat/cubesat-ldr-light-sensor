# CubeSAT LDR Light Sensor

An ESP32-S3 light-direction sensor project using a pair of light-dependent resistors (LDRs), with a desktop calibration interface and competition preparation resources.

## Project files

Download and extract **cubesat-competition-kit.zip** for the complete project. The archive preserves the original folder structure, including firmware, calibration data, tests, and printable blade templates.

- `firmware/`: ESP32-S3 sketch, configuration and calibration headers, and PlatformIO setup. Supports Arduino IDE and PlatformIO.
- `comp_gui.py`: PyQt5 calibration console with serial capture, manual entry, plotting, and calibration-header generation.
- `data/`: supplied sweeps and calibration examples.
- `tests/`: simulation, firmware checks, and GUI checks.
- `COMPETITION_PLAYBOOK.md`: preparation and competition procedures.
- `baffle_templates.pdf`: printable blade templates.

## Getting started

1. Download and extract the ZIP.
2. Read the included `README.md` and `firmware/README.md` for setup and wiring details.
3. Install the desktop dependencies:

   ```sh
   pip install PyQt5 pyqtgraph pyserial numpy
   ```

4. Run `python comp_gui.py` from the extracted kit folder.
5. Follow the included calibration procedure before using angle estimates.

## Sensor approach

The supplied design uses two LDRs splayed approximately 20 degrees outward and a centre blade. Calibration maps the readings to light direction. The design uses a ratio estimator in the central region and an amplitude estimator near the ends; the latter depends on a tracked brightness reference.

## Validation status

The original kit contains simulation and compilation checks. These checks have not been rerun as part of this repository upload, and physical hardware performance has not been independently verified here. Consult the included documentation for the original reported results and limitations.
