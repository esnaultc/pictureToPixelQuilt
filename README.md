# pictureToPixelQuilt

Trying to merge two of my favorite hobbies, this project is intended to convert a picture file (.jpg)
to a grid of square tiles of a finite number of colors that can be used as a quilt pattern.

## Prerequisites

The necessary R packages can be installed with a version control tool such conda:

``conda env create -p env --file requirements.yaml``

then the environment can be activated with:

``conda activate env/``

## Parameters

Parameters are specified in the ``config.yaml`` file, to be edited as necessary. The
following parameters are currently included:

```bash

  # picture file to process (JPG)
  input_fn: fall_landscape.jpg
  
  # number of tiles across the width of the picture. The number of tiles across the height
  # will be deducted from the picture size
  tile_number_width: 40
  
  # number of different colors / fabrics
  color_number: 16
  
  # size in inch of each tile (not implemented yet, this will be used to determine the
  # fabric requirements
  tile_size: 2
```

## Command line to run the script

Run the Rmarkdown script with:

``Rscript -e "rmarkdown::render('pictureToPixelQuilt.Rmd')"``

This command generates an html report, a jpeg of the resulting tiled picture and
a jpeg of the color swatch.

## To Do

This repo is still under development. The goal is to generate a full quilt pattern
with fabric requirements, pattern grid and instructions.

- return the number of tiles of each color
- generate a tile grid split into smaller blocks (8x8 tiles?) that can be assembled and
  sewn together later
- calculate the fabric requirements, taking into account a 1/4" seam allowance on the tiles,
  translate into fat quarters, or other fabric yardage
- print out the full instructions with grids pictures in the html report

