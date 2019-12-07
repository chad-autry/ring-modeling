# ring-modeling
These are the steps I took when 3D modeling some Celtic knotwork wedding rings for 3D printing. There are likely simpler ways for the same effect.

# Tools Used
* Text editor
* Chrome
* Inkscape
* GIMP
* [potrace](http://potrace.sourceforge.net/)
* FreeCAD
* Blender
* 3D Printing Service

# Steps
1. Make your initial image. I'm weird, so I wrote SVG text by hand. You will likely do something else...
2. Open with Inscape and export to png. Even though I start with SVG, FreeCAD/Blender don't like inporting SVG images with the masks and elements used. IMPORTANT: Rename while exporting so we don't overwrite the original image on a later step.
3. Open png in GIMP. We're going to round sharp corners, and re-export to another format.
    1. Select --> by color, click transparent area
    2. Select --> Invert
    3. Slect --> Shrink 30px
    4. Select --> Grow 30 px
    5. Select --> Invert
    6. Delete
    7. Export As PNM image (RAW)
4. potrace -b svg -C #A9A9A9 <pnm image name>
5. Import the processed SVG into FreeCAD
