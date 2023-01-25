# lutcraft (lutc)
Tool to create 3D lookup tables (.cube files) for video/image color manipulation.

Lutcraft is a command line program written in python3.


## About 3D luts

3D lookup tables are used to manipulate the look of an image or a video seqence.
The map each point in a colorspace (e.g. RGB) to a new point in the same colorspace.

I guess if you found your way here, you know what 3D luts are and what they
are used for ;-) 

## Usage

###  1. Create a neutral png image
`lutc lut-neutral.png`

This creates a 'neutral' image.

### 2. Manipulate the colors of the image
Do pixel-level color adjustments as desired.

Tools I suggest are darktable, gimp, flowblade or cinelerra.
Any other program doing pixel-level imaging will do fine.

Then save the image. I assume you call the file lut-x.png.

### Convert the image into a lookup table (.cube file)
`lutc -i lut-x.png lut-x.cube`

This will output a 3D lookup tabble corresponding to the
file lut-x.cube

## Advanced usage
`lutc -h` displays all available options.

### Adjust lut3d size

The default lut size is 32.

To create a lut with a size of 64, use
`lutc -s 64 lut64-neutral.png

Then manipulate the image as desired and create the .cube file:

`lutc -i lut64-x.png lut64-x.cube`

lutcraft can detect the size of the image automatically for most
values of size.

## Precision

The normal precision is 4 digits after the comma.

If you only need a lut with size 16, you can reduce the precision
to 2 for smaller output files:

`lutc -s 16 -i lut16-x.png -p 2 lut16-x.cube`
