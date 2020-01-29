---
title: Fastai Lesson 2
date: 2018-06-02 00:00:00 Z
permalink: "/fastai-lesson2"
layout: post
excerpt: Notes & Explorations with FastAI Lesson 2
---

### Notes from Lesson 2

```
  sz => image_size,
  bs => batch_size,
  precompute => use_precomputed_activations 
  ps => dropout_probabilities, 
  aug_tfms => augmentation_transforms
```

- `precompute=True` means activations have already been computed (use previous weights). It caches some of the intermediate steps which we do not need to recalculate every time. It uses cached non-augmented activations. That’s why data augmentation doesn’t work with precompute. Having precompute speeds up our work.

- I think one fundamental difference between a pre-trained network and a pre-computed outputs, is that:

    In a pre-trained network the layer weights that have been pre-calculated, but this has nothing to do with your input data with the training/test/validation images of dogs and cats
Pre-computed activations have passed your input data (dogs and cat images) through the network and have cached the results.
It seems like pre-computing is a second level caching mechanism to avoid repeated feedforward passes on the input data, since it will end up producing the same results each time. The danger is that if you make some tweaks (like data augmentation), and you forget to re-run the pre-compute phase, then your changes won’t be reflected.

- With Data Augmentation, set `precompute=False`

- Set `precompute=False` when freezing, should be done automatically
 
  