SVG hexagon flower
==================

Learning to write re-usable svg constructs.


alias notes
-----------
bake out a 'flat' svg from rsvg. then pass that to convert using the msvg engine
rsvg in.svg -o out.svg --format=svg
convert +antialias -density 10 msvg:wee.svg +antialias hexim.png
