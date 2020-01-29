---
title: Fastai Lesson 1
date: 2018-06-02 00:00:00 Z
permalink: "/fastai-lesson1"
layout: post
excerpt: Notes & Explorations with FastAI Lesson 1
---

### Notes
* environment.yml has `pytorch<0.4` which causes pytorch to not get updated if pytorch is not already installed. Had to do the following:
* also had to install fastai manually
* also installing some other useful libraries
```
pip install --force pytorch
pip install fastai
pip install gpustat
pip install google-images-download
```
* download google chromedriver
```
wget https://chromedriver.storage.googleapis.com/2.39/chromedriver_linux64.zip
unzip chromedriver.zip
sudo mv chromedriver /usr/local/bin
```

### Explorations
* Use `https://github.com/boxabirds/fastai-helpers` to create new dataset:

```
wget https://raw.githubusercontent.com/boxabirds/fastai-helpers/master/training-data-generator.py
```
This package uses `https://github.com/hardikvasa/google-images-download`

* You can use this as follows to download 200 images of `horse` and `hippo` in subdirectory `data\horsehippo` with train-valid split of 80-20 (note no spaces after the comma between category names, supports > 2 categories):
 
```python training-data-generator.py -d data/horsehippo -s "horse,hippo" -q 200 -v 20```

* A faster option to generate a dataset is to use `https://github.com/prairie-guy/ai_utilities`. A sample workflow would be as follows: 
```
git clone https://github.com/prairie-guy/ai_utilities.git
cd ai_utilities/
tar xvzf geckodriver-v0.19.1-linux64.tar.gz
sudo mv geckodriver /usr/local/bin
```

```python
python image_download.py 'horse' 200 --engine 'google'
python image_download.py 'hippo' 200 --engine 'google'
mv dataset horsehippo2
./filter_img.sh horsehippo2/horse
./filter_img.sh horsehippo2/hippo
python make_train_valid.py horsehippo2 --train 0.7 --valid 0.15 --test 0.15
mv horsehippo2 ~/fastai/courses/dl1/data/
``` 