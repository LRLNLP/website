---
title: Challenge
weight: 5
omit_header_text: true
description: We'd love to hear from you
featured_image: '/images/banner_large.png'
type: page
menu: main

---

## Submissions

The test partition, without labels, will be made available at least 2 weeks before the challenge deadline (June 30, 2025).
Participants will be able to submit their predictions for the test set, and the results will be evaluated on our server. 
The exact details of how to submit will be provided closed to the deadline, for now please refer to the 
supplementary code on how to evaluate your predictions on [GitHub](https://github.com/BlEmoRe/blemore-common/tree/main)

## Dataset 

The training partition of the dataset is available on [Zenodo](https://zenodo.org/records/15096942)

The training partition of the BLEMORE dataset includes 2,456 multimodal portrayals of both basic and blended emotions, 
recorded under controlled studio conditions with synchronized audio and video.

A total of 47 actors and actresses participated in the recordings, each was instructed to express:

### Basic Emotions

_Anger, Disgust, Fear, Happiness, Sadness_ — portrayed in four different intensities (`int1–int4`)

_Neutral_ — portrayed in four distinct but equivalent imagined situations (`sit1–sit4`); 
these situations are not ordered or ranked, and are included primarily to increase variability in neutral portrayals

### Blended Emotions

All pairwise combinations of the five basic emotions (excluding _neutral_)

Portrayed in three blend ratios:

* `50/50`: equal salience
* `70/30`: first emotion dominant
* `30/70`: second emotion dominant

Expressions were conveyed using facial expressions, body movement, and non-linguistic vocalizations (e.g., sighs, laughs). Participants were instructed to appear naturalistic and avoid exaggerated or stereotypical portrayals.


## Metrics

we employ two main evaluation metrics: `ACC_presence` and `ACC_salience`.

- `ACC_presence` measures whether the correct label(s) are predicted without errors.
  A correct prediction must include all present emotions while avoiding false negatives
  (e.g., predicting only one emotion in a blend) and false positives
  (e.g., predicting emotions that are not part of the label).

- `ACC_salience` extends `ACC_presence` by considering the relative prominence of each emotion.
  It evaluates whether the predicted proportions reflect the correct ranking — whether the emotions
  are equally present or one is more dominant than the other. This metric applies only to blended emotions.

`ACC_presence` is in effect a generic way to measure (blended) emotion recognition, and is easily
comparable to models implemented on other datasets. `ACC_salience` captures the unique feature of
our dataset — emotion salience in different blend conditions.

We encourage submissions to provide information about how various blended emotions are expressed, 
e.g. by providing lists of predictor importance, to increase the explainability of their systems.

## Baselines 

Baselines, accuracy metrics, and other supplementary code is provided on [GitHub](https://github.com/BlEmoRe/blemore-common/tree/main) 

