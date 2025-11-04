# pictureToPixelQuilt

This project is intended to convert a picture file (.jpg) to a grid of tiles
that can be used as a quilt pattern.

The necessary R packages can be installed with a tool like conda:

``conda env create -p env --file requirements.yaml``

then the environment can be activated with:

``conda activate env/``

Parameters are specified in the ``config.yaml`` file. Edit as necessary. The
following parameters are currently included:

```bash

  # picture file to process (JPG)
  input_fn: fall_landscape.jpg
  
  # number of tiles across the width
  tile_number_width: 40
  
  # number of different fabrics
  color_number: 16
  
  # size in inch of each tile (not implemented yet, this will be used to determine the
  # fabric requirements
  tile_size: 2
```

Run the Rmarkdown script with:

``Rscript -e "rmarkdown::render('pictureToPixelQuilt.Rmd')"

