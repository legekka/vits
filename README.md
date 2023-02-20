# How to use

## Clone this repository
```sh
git clone https://github.com/CjangCjengh/vits.git
```
## Choose cleaners
- Fill "text_cleaners" in config.json
- Edit text/symbols.py
- Remove unnecessary imports from text/cleaners.py
## Install requirements
```sh
pip install -r requirements.txt
```
## Create datasets
### Single speaker
"n_speakers" should be 0 in config.json
```
path/to/XXX.wav|transcript
```
- Example
```
dataset/001.wav|こんにちは。
```
### Mutiple speakers
Speaker id should start from 0 
```
path/to/XXX.wav|speaker id|transcript
```
- Example
```
dataset/001.wav|0|こんにちは。
```
## Preprocess
If you have done this, set "cleaned_text" to true in config.json
```sh
# Single speaker
python preprocess.py --text_index 1 --filelists path/to/filelist_train.txt path/to/filelist_val.txt

# Mutiple speakers
python preprocess.py --text_index 2 --filelists path/to/filelist_train.txt path/to/filelist_val.txt
```
## Train
```sh
# Single speaker
python train.py -c <config> -m <folder>

# Mutiple speakers
python train_ms.py -c <config> -m <folder>
```