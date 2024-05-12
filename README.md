# Unified Vision-Language Pre-training (VLP).
This repo hosts an implementation of Zhou (2020)'s work on [Unified Vision-Language Pre-training (VLP)](https://arxiv.org/pdf/1909.11059.pdf).
## File Description

```VLP_Inference ``` :  To test the released model <br>
```VLP_TrainTest.ipynb ``` :  To train the model on Flickr30k <br>
```VLP_Hyperparameter ``` :  To To train the model with new hyperparameters on Flickr30k <br>
```run_img2txt_dist.py ``` :  Runs the training loop <br>
```decode_img2txt.py ``` :  Runs the testing loop <br>
```seq2seq_loader.py ``` :  Defines the seq2seq training objective <br>
```scst_utils.py ``` :  Defines Self-Critical Sequence Training (SCST) for COCO dataset (not used here) <br>
Rest of the files deal with either pretraining on Conceptual Captions or the VQA task and have not been used here <br>

## Installation
### Conda Environment (Option I, Recommended)
0) Recursively ssh clone the repo to include `coco` and `pythia` submodules.
```
git clone --recursive https://github.com/120205690/597-Course-Project.git
```

1) Install CUDA (e.g., 10.0), CUDNN (e.g., v7.5), and [Miniconda](https://docs.conda.io/en/latest/miniconda.html) (either Miniconda2 or 3, version 4.6+).

2) Run the following commands to set up conda env and install Python packages:

```
MINICONDA_ROOT=[to your Miniconda root directory] # e.g., /home/[usrname]/miniconda3
cd VLP
conda env create -f misc/vlp.yml --prefix $MINICONDA_ROOT/envs/vlp
conda activate vlp
```

3) Finally, `cd` to the repo root directory and install other dependencies by running:
```
./setup.sh
```
To support language evaluation (SPICE), run
```
cd coco-caption
./get_stanford_models.sh
```


# Inference and Testing

To run the code locally, install NVIDIA Apex from https://github.com/NVIDIA/apex <br>
To run on Colab, try installing NVIDIA Apex using the shell script given. <br>
If it doesn't install correctly, run VLP_TrainTest.ipynb. Else use original run_img2txt_dist.py from  [Vision-Language Pre-training (VLP)](https://github.com/LuoweiZhou/VLP)) <br>
Trained model checkpoints are contained in the flickr30k folder <br>

# Acknowledgement

All credits go to https://github.com/LuoweiZhou/VLP <br>
Check out their AIII 2020 Paper at [Unified Vision-Language Pre-training (VLP)](https://arxiv.org/pdf/1909.11059.pdf).
