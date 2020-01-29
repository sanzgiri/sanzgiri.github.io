---
title: Tensorflow in Swift
date: 2019-05-20 00:00:00 Z
permalink: "/tensorflow-swift"
layout: post
excerpt: Tensorflow-Swift
---

### Using Swift on Tensorflow

* Lauching a Jupyter notebook for Swift 
```
git clone https://github.com/google/swift-jupyter.git
cd swift-jupyter
docker build -f docker/Dockerfile -t swift-jupyter .
docker run -p 8888:8888 -it --cap-add SYS_PTRACE -v ~/swift-notebooks:/notebooks swift-jupyter
```

* Useful resources:
1. Swift for Tensorflow project on github: <https://github.com/tensorflow/swift>
1. Swift kernels in Jupyter: <https://github.com/google/swift-jupyter/#option-3-using-the-docker-container>
1. Fast AI swift notebooks: <https://github.com/fastai/fastai_docs/tree/master/dev_swift>
1. Hacking with Swift: <https://www.hackingwithswift.com>
1. Swift for Tensorflow example: <https://colab.research.google.com/github/tensorflow/swift/blob/master/docs/site/tutorials/model_training_walkthrough.ipynb>