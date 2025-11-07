# pictureToPixelQuilt

See the rendered html at [https://esnaultc.github.io/pictureToPixelQuilt/](https://esnaultc.github.io/pictureToPixelQuilt/)

Trying to merge two of my favorite hobbies, this project is intended to convert a picture file (.jpg)
to a grid of square tiles of a finite number of colors that can be used as a quilt pattern.

It relies on first reducing the total number of colors in the image, using ``image_quantize`` from
the R package ``magick``, dividing the full image into square tiles. For each tile, the dominant
color is determined and converted to RGB.

At this point, most images will still return an impractical number of colors. K-means clustering,
throught the R package ``kmeans`` is used to cluster the colors into a user-defined final
number of colors.

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
  img_filename: fall_landscape.jpg
  
  # number of tiles across the width of the picture. The number of tiles across the height
  # will be deducted from the picture size
  tile_number_width: 50
  
  # number of different colors / fabrics
  color_number: 16
  
  # size in inch of each tile (not implemented yet, this will be used to determine the
  # fabric requirements
  tile_size: 2

  # colorspace to use in reducing the number of colors in the original picture
  # (some examples are YUV, RGB, HSV)'

  colorspace: YUV

  # maximum number of colors returned after colorspace reduction
  colorspace_max_colors: 500

  # block size in tiles (i.e. 8 for instructions for blocks of 8x8 tiles)
  grid_block_size: 8
```

## Command line to run the script

Run the Rmarkdown script with:

``Rscript -e "rmarkdown::render('pictureToPixelQuilt.Rmd')"``

This command generates a pattern as an html file.

