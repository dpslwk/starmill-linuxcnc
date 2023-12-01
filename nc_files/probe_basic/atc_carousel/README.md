# atc_carousel - Probe Basic Subroutines

https://kcjengr.github.io/probe_basic/atc_setup.html

This folder contains carousel ATC subroutines for `probe_basic`  
These routines are all called form the ATC tab in the main UI or as part of M6 remap

| File                               | Purpose                                            |
|------------------------------------|----------------------------------------------------|
| `clamptool.ngc`                    | Clamp the spindle drawbar                          |
| `extendatc.ngc`                    | Move the ATC carousel under the spindle            |
| `m10.ngc`                          | Move tool carousel best direction to pocket P      |
| `m11.ngc`                          | Move tool carousel CCW P number of pockets         |
| `m12.ngc`                          | Move tool carousel CW P number of pockets          |
| `m13.ngc`                          | Move tool carousel CW until homed                  |
| `m21.ngc`                          | Move Carousel to the tool change position (OUT) then unload any tool in the spindle into the current pocket  |
| `m22.ngc`                          | Move Carousel to the home position (IN) after loading any tool in the current pocket to the spindle |
| `m23.ngc`                          | Not currently used                                 |
| `m24.ngc`                          | Unclamp the spindle drawbar                        |
| `m25.ngc`                          | Move the ATC carousel under the spindle            |
| `m26.ngc`                          | Not currently used                                 |
| `move_head_above_carousel.ngc`     | Move Z to atc_z_tool_clearance_height              |
| `move_tool_to_carousel_height.ngc` | Move Z to atc_z_tool_change_height                 |
| `retractatc.ngc`                   | Move the ATC carousel to the home position         |
| `store_tool_in_carousel.ngc`       | Store spindle tool in carousel                     |
| `toolchange.ngc`                   | Main M6 toolchange routine                         |
| `unclamptool.ngc`                  | Unclamp the spindle drawbar                        |


Three settings in your INI file set basic configuration of the carousel ATC

```
[ATC]
# Carousel image available for 8, 10, 12, 14, 16, 18, 20, 21, 24
POCKETS = 12
# The Z height you spindle needs to be at to clamp/unclamp a tool form the ATC
Z_TOOL_CHANGE_HEIGHT = -3.9000
# The Z clearance height you spindle needs to be at to safely clear the ATC
Z_TOOL_CLEARANCE_HEIGHT = -0.1

```

`POCKETS` (defaults to 12) sets `#<number_of_pockets>`
This is used in most files


`Z_TOOL_CHANGE_HEIGHT` (defaults to -3.9000)
`Z_TOOL_CLEARANCE_HEIGHT` (defaults to [AXIS_Z]MAX_LIMIT>-0.1)
These two set the heights used in the following files 

* m21
* m22
* move_head_above_carousel
* move_head_above_carousel
* extendatc

## Hal Connections

![HAL Connections need for ATC](/docs_src/source/images/atc_carousel_connections.png)

## TODO:
* add `atc_z_tool_change_height` and `atc_z_tool_clearance_height` to settings UI
* m21 and m22: call move_tool_to_carousel_height instead of `G53 G0 Z#<atc_z_tool_change_height>`
* extendatc, m21: call move_head_above_carousel instead of `G53 G0 Z#<atc_z_tool_clearance_height>``
