# ReadMe-For-Moecule-Transformer

### Installation
An environment config `moses.yml` is provided in this repository. You can create the environment from the file

`$ conda env create -f moses.yml `

then activate the environment

`$ conda activate moses`

### Before training

First cd to the directory of the downloaded code:

`$ cd $code`

Create the directory used to the models.

`$ mkdir dir_save`

### Training
`$ python scripts/train.py --size_batch=256 --model_type=AMG --dim_attention=768 --n_heads=4 --n_layers=12 --load_pretrain=0 --epochs=20`

By default the script creates a folder in `dir_save` directory based on the configuration of the model, and saves the trained models in that folder. You can specify the directory path If you want to change the saving location. For example:

`$ python scripts/train.py --size_batch=256 --model_type=AMG --dim_attention=768 --n_heads=4 --n_layers=12 --load_pretrain=0 --epochs=20 --dir_checkpoint=my_location`

### Sampling

`$ python scripts/sample.py --dir_model=dir_save/AMG_768_4_3072_12 --idx=5 --size_batch=64 --temperature=1.0`

The sample script stores the sampled molecules in the same directory where the model is stored. Therefore you can find the sampled molecules in `dir_save/AMG_768_4_3072_12/sample_5_1.0.csv`. Here the `1.0` in the csv file name represents the temperature used in the sampling program.


### Evaluating

`$ python scripts/evaluate.py --n_sample=30000 --path_sample=dir_save/AMG_768_4_3072_12/sample_0.csv`

This scripts evaluates the generated molecules and provides a table of metrics based on MOSES. See more information from https://github.com/molecularsets/moses
