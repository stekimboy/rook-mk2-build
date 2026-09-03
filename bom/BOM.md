# Bill of Materials (this build)

This parts list follows Rolohaun Design's Rook 2020 MK2 BOM, published under
CC BY-NC 4.0 with the design on Printables
(https://www.printables.com/model/798733-rook-2020-mk2). Purchase links and
current prices are in the upstream Google Sheet:
https://docs.google.com/spreadsheets/d/1k5knQOW3YX01BzTAEe6YCPVp2iNppOEKYJrqB6Ln_Wk

Part names and quantities below are the ones used for this build. Prices and
links are intentionally omitted; the ones in the upstream sheet are the
designer's, not a record of this build's purchases.

## Frame
- 11 x 200 mm 2020 extrusion with blind joints (DIY), or the Funssor premade frame kit as an alternative

## Motion
- GT2 6 mm belt, 4 m
- 4 x 20T pulley, 5 mm bore, 6 mm wide
- F695 bearings, 28 needed (3 packs of 10)
- 2 x MGN9C 200 mm rail (Y)
- 1 x MGN9C 150 mm rail (X)
- 3 x NEMA17 42 mm (4 if using a BMG extruder)
- 2 x 8 mm linear rod, 200 mm (Z)
- 2 x LM8UU bearing, 45 mm long
- 4 x rubber feet, 38 mm diameter x 19 mm

## Geared Z (optional, recommended)
- 80T GT2 pulley, 5 mm bore (or 3D printed)
- Closed-loop GT2 188 mm belt
- 5 mm D-shaft, 50 to 60 mm (cut brass tube works)

## Hardware
- 10 x M3x6 button head, X/Y carriage mounts
- 22 x M3x10, stepper mounting
- 2 x M3x12, X linear rail
- 6 x M3x16, idler towers, mainboard
- 2 x M3x18, motor mounts
- 8 x M3x25, Y rails
- 10 x M3 T-nuts, 4 x M3 nuts
- 4 x M5x25, XY carriage idlers
- 14 x M5x16 button head, rubber feet / foot mounts
- 4 x M5x10x1 mm shims
- 35 x M5x8 + 35 x M5 T-nuts, frame
- ~100 x M3 heat inserts, 5.0 OD x 4.0 L (order 300)

## Extruder + Hotend
- HDX-Lite direct-drive extruder
- Bambu X1 hotend

## Bed
- Funssor Rook bed
- 100 x 100 mm heater
- Bed springs + M4 bolts

## Electronics
- 24 V 8 A power supply
- XT60 panel male + female
- Omron-style endstop (Z only)
- BTT SKR Pico
- 3010 24 V hotend fan (GDstime)
- 5015 24 V part-cooling fan (GDstime)

## Deviations from the stock MK2

Only what this repo documents (README, `klipper/printer.cfg`) is
listed here.

Choices among the options the upstream BOM offers:

- Direct drive: HDX-Lite extruder with a Bambu X1 hotend, instead of the
  Bowden BMG option in the upstream sheet.
- Controller: BTT SKR Pico (four TMC2209s on one shared UART), instead of the
  SKR Mini E3 v3 option. Sensorless X/Y homing with a single mechanical
  endstop on Z is how the upstream design is intended to run, and this build
  follows that.

Build-specific details in `printer.cfg`:

- The Z endstop is mounted at the top of Z travel (`position_endstop` =
  `position_max` = 92.5), so `[homing_override]` homes Z before X and Y.
  Whether this differs from the stock endstop placement is not recorded in
  this repo.
- A third fan output (gpio20) is repurposed as a fixed 40 % always-on fan via
  `[output_pin always_on_fan]`; it is not slicer-controllable.
- X/Y `position_max` is set to the 120 mm bed, not the frame's travel.
