# zegamiML

## Requirements

* Python 3.5+
* Python modules:
  * [NumPy](https://www.numpy.org/)
  * [pandas](https://pandas.pydata.org/)
  * [Pillow](https://pillow.readthedocs.io/en/stable/)
  * [scikit-learn](https://scikit-learn.org/stable/)
  * [umap](https://github.com/lmcinnes/umap)
  * [matplotlib](https://matplotlib.org/) (required only for plotting)

This tool performs unsupervised dimensionality reduction using one of the currently supported analyses types (PCA, tSNE or UMAP) and appends two new columns with coordinates of the first two components of the embeding to the tab-delimited zegami table. This table can be later used in the zegami platform to further analyse the data.

## Usage 

```
usage: zegamiML [-h] -i INPUT -o OUTPUT -c IMAGE_COLUMN -d IMAGE_DIR
                [-a ANALYSIS_TYPE] [-v] [-p]

zegamiML - dimensionality reduction applied on the set of images to be used in
Zegami processing

optional arguments:
  -h, --help            show this help message and exit
  -i INPUT, --input INPUT
                        Input file name (must be a tab-delimited file)
  -o OUTPUT, --output OUTPUT
                        Output file name (original TSV with the X and Y
                        columns appended)
  -c IMAGE_COLUMN, --image_column IMAGE_COLUMN
                        Column name in TSV that contains the image name
  -d IMAGE_DIR, --image_dir IMAGE_DIR
                        Directory that contains all the images.
  -a ANALYSIS_TYPE, --analysis_type ANALYSIS_TYPE
                        PCA, TSNE or UMAP.
  -v, --verbose
  -p, --plot            Produce a visualisation of the applied
                        dimensionalityreduction.
```

## Example

```
./zegamiML -i ./test/zegami.tab  -o ./zegami_UMAP.tab -d ./test/imgs -c path -a UMAP -p
```

