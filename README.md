# Mirex 2019 Audio Classification (Train/Test) Tasks

## Tasks

| Task                                      | No of samples | No of Classes |
|-------------------------------------------|---------------|---------------|
| [Audio Classical Composer Identification](https://www.music-ir.org/mirex/wiki/2019:Audio_Classification_(Train/Test)_Tasks) | 2772          | 11            |
| Audio US Pop Music Genre Classification   | 7000          | 10            |
| Audio Latin Music Genre Classification    | 3227          | 10            |
| Audio Music Mood Classification                 | 600           | 5             |
| [Audio K-POP Mood Classification](https://www.music-ir.org/mirex/wiki/2019:Audio_K-POP_Mood_Classification)           | 1438          | 5             |
| [Audio K-POP Genre Classification](https://www.music-ir.org/mirex/wiki/2019:Audio_K-POP_Genre_Classification)          | 1894          | 7             |

## Requirements
- Python >= 3.6
- Python packages:
  - librosa, numpy, pandas, joblib, tqdm, sklearn, albumentations, runstats
  - PyTorch >= 1.1

## Setting up environment

- `mkdir -p mirex`
- `tar -xzf mirex.tar.gz -C mirex`
- `source mirex/bin/activate`
- `conda-unpack`


## Running commands

### generating sample data

`python generate_sample_data.py -d data/ -i data/sample.wav`

### Feature extraction

`python extract_features.py -s /home/scratch -i data/features_extraction.txt -n 4 `

### Training

`python train.py -s /home/scratch -i data/train.txt -n 4 -t kpop_mood`

### Classifying

`python classify.py -s /home/scratch -i data/test.txt -o test_preds.txt -n 4 -t kpop_mood`

## Time taken

### Features extraction 
- 4 threads ~ 5 min
- ~ 1.5 GB memory for extracted features # maychange with parameters
