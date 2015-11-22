SVG hexagon flower
==================

Learning to write re-usable svg constructs.


aliasing and coordinates
------------------------

To flatten all the reusable shape defs and transforms into a simpler set of absolute coordinates: Export from Inkscape as a **simplified svg** or from command line:

    rsvg in.svg -o flat.svg --format=svg

Add `shape-rendering="crispEdges"` to the svg tag, then view in gimp or from command line:

    convert +antialias -density 10 flat.svg out.png

**old method with imagemagick mvg commands**

    convert +antialias -density 10 msvg:wee.svg +antialias hexim.png

**Alternatives?**

Use ghostscript.

    gs -dSAFER -dBATCH -dNOPAUSE -sDEVICE=png16m \
       -r72 -dGraphicsAlphaBits=1 \
       -sOutputFile=image.png image.pdf

### Notes

Viewbox is weird between inkscape and browsers. 1% stroke width acts differently resulting in a thick line in inkscape, but normal in the browser. 0.01 (no measurement unit) acts consistant between the two. This would not happen if the viewbox coordinate system were closer to the svg height width.
