# ring-modeling
These are the steps I took when 3D modeling some Celtic knotwork wedding rings for 3D printing. There are likely simpler ways for the same effect.

# Tools Used
* Text editor
* Chrome
* Inkscape
* GIMP
* [potrace](http://potrace.sourceforge.net/)
* FreeCAD
* Simple algebra, geometry, and [Wikipedia's Ring Size page](https://en.wikipedia.org/wiki/Ring_size)
* Blender
* 3D Printing Service

# Steps
1. Make your initial image(s) for your layer(s). I'm weird, so I wrote SVG text by hand. FreeCAD/Blender don't like inporting SVG images with the masks and elements used, plus I have some sharp corenrs to round off, so the next steps are processing my hand created 2D image. Depending on how you create your source SVG you might be able to skip to step 5.
2. Open with Inscape and export to png. IMPORTANT: Rename while exporting so we don't overwrite the original image on a later step.
3. Open the png in GIMP. We're going to round sharp corners, and re-export to another format.
    1. Select --> by color, click transparent area
    2. Select --> Invert
    3. Slect --> Shrink 30px
    4. Select --> Grow 30 px
    5. Select --> Invert
    6. Delete selection
    7. Export As PNM image (RAW)
4. Use potrace from the command line: potrace -b svg -C #A9A9A9 \<pnm image name\>
5. Import the processed SVG into FreeCAD
    1. Open the Part Workbench
    2. Measure --> Measure Linear --> From tip to tip of your artwork
    3. Decide how many milimeters thick your ring should be. A commercial size 5.5 measured 2.16 and a size 8.5 measured 2.3)
    4. Figure out the outer circumference of your ring in mm 2pi*(chart radius + ringThickness) = outerCircumference
    5. We now have the ratio of FreeCAD units to mm, and should know how much to extrude each layer (I do 2 layers for knotwork, overlapping the middle third)
    6. Extrude the layer
