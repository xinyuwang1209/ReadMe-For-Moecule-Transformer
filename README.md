# ReadMe-For-Moecule-Transformer

### Installation
#### An environment config `moses.yml` is provided in this repository. You can create the environment from the file
`$ conda env create -f moses.yml `
#### then activate the environment
`$ conda activate moses`

### Before training
#### First cd to the directory of the downloaded code:
`$ `

### Training
`python scripts/train.py --size_batch=256 --model_type=AMG --dim_attention=768 --n_heads=4 --n_layers=12 --load_pretrain=0 --epochs=20`
### Sampling
`python scripts/sample.py --dir_model=dir_save/AMG_768_4_3072_12 --idx=5 --size_batch=64`
### Evaluating
`python scripts/evaluate.py --n_sample=30000 --path_sample=dir_save/AMG_768_4_3072_12/sample_0.csv`


