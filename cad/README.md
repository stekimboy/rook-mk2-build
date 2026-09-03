# CAD

The Fusion 360 assembly for this build, `My-Rook.step` (STEP AP214, about
170 MB), is attached to the GitHub Release for this repo rather than tracked
in git:

https://github.com/stekimboy/rook-mk2-build/releases

Download it from there and open it in Fusion 360, Onshape, FreeCAD, or any
STEP-capable tool.

## Provenance

The assembly is derived from Rolohaun Design's Rook 2020 MK2 CAD, published
under CC BY-NC 4.0 at https://www.printables.com/model/798733-rook-2020-mk2.
It is shared under the same license (see `LICENSE` at the repo root).

It also contains reference geometry for purchased parts, included only so the
assembly fits together on screen. These models belong to their respective
owners and are not licensed by this repo:

- McMaster-Carr F695ZZ bearings and an MXL pulley
- An Annex Engineering Sherpa Mini extruder, used as a stand-in for the
  HDX-Lite that is actually on the printer
- Trianglelab / CR10-style hotend models
- A 5015 blower fan, a NEMA17 stepper, GT2 pulleys and belts, LM8LUU bearings

## Known mismatch with the built printer

The toolhead in the CAD (Sherpa Mini plus a CR10-style hotend) does not match
what is installed: an HDX-Lite direct-drive extruder with a Bambu X1 hotend.
Treat the CAD toolhead as placeholder geometry, not as a record of the build.
