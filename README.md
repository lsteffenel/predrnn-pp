# OSE (Ozone Secondary Events) forecast with PredRNN++

PredRNN++ is a TensorFlow implementation of [PredRNN++](https://arxiv.org/abs/1804.06300), a recurrent model for video prediction from Yunbo Wang et al.

## Setup
Required python libraries: tensorflow (>=1.0) + opencv + numpy.\
Tested in ubuntu/centOS + nvidia titan X (Pascal) with cuda (>=8.0) and cudnn (>=5.0).

## Datasets
to do

## Training
Use the train.py script to train the model. To train the default model on Moving MNIST simply use:
```
python train.py
```
You might want to change the `--train_data_paths`, `--valid_data_paths` and `--save_dir` which point to paths on your system to download the data to, and where to save the checkpoints.

To train on your own dataset, have a look at the `InputHandle` classes in the `data_provider/` folder. You have to write an analogous iterator object for your own dataset. 

At inference, the generated future frames will be saved in the `--results` folder.

## Prediction samples
The ground truth | PredRNN++ | A baseline model.\
10 frames are predicted given the last 10 frames.

<div align=center><img width="192" height="64" src="https://github.com/Yunbo426/ImageToGit/blob/master/23.gif"/></div>

## Citation
Please cite the following paper if you find this repository useful.
```
@inproceedings{steffenel2019,
    title={Spatio-Temporal LSTM Forecasting of Ozone Secondary Events},
    author={Steffenel, Luiz Angelo, Rasera, Gustavo, Begue, Nelson, Kirsch Pinheiro, Damaris, Bencherif, Hassan},
    journal={EGU General Assembly 2019},
    year={2019},
    url={https://meetingorganizer.copernicus.org/EGU2019/EGU2019-8075.pdf}
}
```

