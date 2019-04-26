# Art on the command line with ImageMagick

This is a slimmed-down version for importing to Glitch. The complete repository, with install instructions and PowerPoint slides, can be found [here.](https://github.com/Vampire-Computer-People/art_cmdline_magick)

Note that this uses ImageMagick 6, not 7!

# Script execution examples

Scripts are set to output files to the /output folder.

## Simple conversion:

`convert sprites/veto_side_step_south_east00.png output/jpeg_convert.jpg`

## Conversion with wildcards:

`convert sprites/veto_side_step_south_east*.png output/jpeg_convert%02d.jpg`

## Scale:

`convert sprites/veto_side_step_south_east00.png -scale 500% output/big.png`

## Scale with distortion:

`convert sprites/veto_side_step_south_east00.png -scale 10% -scale 1000% output/pixelated.png`

## Montage - create a sprite sheet from images

`convert montage sprites/veto_side_step_south_east*.png -tile 3x2 -geometry 200x200 -background transparent output/sprite_sheet.png`

## Split the sheet back into separate images

`convert output/sprite_sheet.png -crop 200x200 output/tile_%02d.png`

## Custom CLI - sprite sheet

`python scripts/sprite_sheet.py -d sprites -o output/sheet.png`

# Scripting with Wand 

## The Meme Machine

`python scripts/meme_machine.py`

## Rorschach

`python scripts/rorschach.py`
