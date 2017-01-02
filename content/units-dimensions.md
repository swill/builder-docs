---
title: Units & Dimensions
weight: 10
---

## Builder Units

All units used by the builder are in Millimeters (`mm`).  That includes dimensions, coordinates and output.  Unfortunately, the current library I am using for exporting DXF files does not support specifying the units in the file format.  Because of this, the dimensions are in `mm` in the drawing, but no units are exported with the DXF file.  Make sure your CAD program is set to `mm` when you open the DXF because it will assume your default units.  If you need a file with units defined for your laser cutter, you will want to open the file in LibreCAD (or some other CAD software), make sure the drawing units are set to `mm`, and then save as a `DXF 2007` file format.  The `DXF 2007` format will save the units as well as the dimension in the resulting DXF file.

## Key Sizing & Spacing

Each key drawn by the builder is based on a multiple of a `key unit`, which has a shorthand of `u`.  A `key unit` is defined to be the amount of space a single 1x1 unit key takes up on a keyboard.  Two 1u keys will be 1u from center to center, which is a constant of `19.05mm`.  Each key on a keyboard can be defined as a multiple of a `key unit`, so a standard Space Bar would be 6.25u, and a Right Shift would be 2.75u.  

For the most part, you will not have to worry too much about the key sizing since the <a href="http://www.keyboard-layout-editor.com/" target="_blank">keyboard-layout-editor.com</a> (KLE) has presets for most of the common layouts.  Keep in mind that KLE may not have the right amount of space between the different key clusters on some layouts, so if you are working from a PCB for a TKL or 104 layout, you will want to verify the spacing KLE specifies.