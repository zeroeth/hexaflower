SVG hexagon flower
==================

Learning to write re-usable svg constructs.


aliasing and coordinates
------------------------

To flatten all the reusable shape defs and transforms into a simpler set of absolute coordinates: Export from Inkscape as a **simplified svg** or from command line:

    rsvg in.svg -o flat.svg --format=svg
    
To hint to any renderer that it should avoid antialiasing add `shape-rendering="crispEdges"` to the svg tag.

Then view in gimp or from command line (doesn't work?):

    convert +antialias -density 10 flat.svg out.png
    
This works better (And doesn't need to be flattened):

    rsvg flat.svg -o flat.png --format=png

**old method with imagemagick mvg commands** (only works with flattened svg)

    convert +antialias -density 10 msvg:wee.svg +antialias hexim.png

**Alternatives?**


Inkscape command line

Batik Library.

    sudo apt install libbatik-java
    rasterizer image.svg -d out.png -h 320 -w 320

Use ghostscript (first convert to ps/pdf).

    gs -dSAFER -dBATCH -dNOPAUSE -sDEVICE=png16m \
       -r72 -dGraphicsAlphaBits=1 \
       -sOutputFile=image.png image.pdf

### Notes

Viewbox is weird between inkscape and browsers. 1% stroke width acts differently resulting in a thick line in inkscape, but normal in the browser. 0.01 (no measurement unit) acts consistant between the two. This would not happen if the viewbox coordinate system were closer to the svg height width.
