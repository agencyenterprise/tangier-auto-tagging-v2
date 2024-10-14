## Exploration on Autotagging for Genre and Mood
Jamendo datasets right now have general tags for all included themes and moods in a song. The problem is that sements of a song can have different themes, instruments and genres.

### Genre Tagging
Genre is a loosely defined concept. Some genre's have key features and musicologists can label and name sed features.

There are several models and papers that tackle the problem of genre tagging.

* The cc music model is decent, but the accuracy isn't good enough at labelling data to be part of our process. The error rate is too high. [model](https://huggingface.co/ccmusic-database/music_genre) / [demo](https://huggingface.co/spaces/ccmusic-database/music_genre)

* [kaggle competition](https://www.kaggle.com/datasets/vicsuperman/prediction-of-music-genre) represents music using high level features that are human labelled. Things like danceability, acousticness, energy and instrumentalness are not necesarily things that we can indicate from a spectogram.

### Mood Tagging

Mood tagging for music is a subset of a problem or class of problems called Multimodal Emotional Recognition. In general we foudnd several models that work for 

in my search I was able to find many datasets and papers, but very few fully working models that had decent performance.

* [lileonardo 3-average model](https://github.com/vibour/emotion-theme-recognition) - provides code to train a model but does not have a pretrained model.

* Collection of [Datasets](https://github.com/juansgomez87/datasets_emotion) for Musical Emotion Recognition that may be used in the future

* [Paper](https://cepdnaclk.github.io/e17-4yp-Music-Emotion-Recognition/) that uses Thayer's model of emotional recognition to classify mood of a song.

* I also found a paper on [Mid Level Features](https://archives.ismir.net/ismir2019/paper/000027.pdf) that could be a promising lead if we decide to generate human trained data. It creates features that are not as high level as acousticness, but not as low level as spectral centroid.

* [Paper](https://huggingface.co/papers/2308.14317)

* [Service](https://huggingface.co/case-studies/aws/musixmatch) called musixmatch which could be a potential low cost commercial service that we could use to label our segments.


### Spike on feature engineering with librosa
see feature_engineering.ipynb for more details on that.

## Installation in runpod

Mac
`brew install sox`

Linux

```
apt update
apt install python3.9
pip install virtualenv
virtualenv jaml -p python3.9
source jaml/bin/activate
pip install -r requirements-jmla.txt
pip install -U openmim
mim install mmcv==1.7.1
apt-get install python3-tk

```

```bash
sudo apt-get update
sudo apt-get install sox
```

Conda
```
conda install conda-forge::sox
```