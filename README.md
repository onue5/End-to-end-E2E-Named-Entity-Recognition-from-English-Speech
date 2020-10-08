[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.3893954.svg)](https://doi.org/10.5281/zenodo.3893954)

<sub> **Implentation of the [E2E NER paper](https://arxiv.org/abs/2005.11184).**</sub> <br/>


### Problem statement:
In this work, we present an E2E NER approach from Enlgish speech, which jointly optimizes the ASR and NER tagger components. Experimental results show that the proposed E2E approach outperforms  the  classical  two-step  approach. 

## Overview:
Named entity recognition (NER) from text has been a widely studied problem. Until now, NER from speech is mostly studied in a two-step pipeline process. NER is an important task in information extraction systems and very useful in many applications. Recent studies confirm that integrated approaches (e.g., E2E ASR)outperform sequential ones (e.g., phoneme based ASR). It has many [progress](https://nlp.cs.nyu.edu/sekine/papers/li07.pdf) and applications such as in optimizing search engine algorithms~, classifying content for news providers, and recommending content. However, NER from speech has many applications such as the privacy concerns in medical recordings (to mute or hide specific words such as patient names), but not a lot of work has been done in this regard. In this work we explore E2E and two-step approach for English speech and comapre the results.

### What we deliver in this repo:
* **Source code files**: For bth the ASR and NER tagger component as standlaone and for the E2E NER.
* **README.md**: Detailed Description of dataset preparation, augmentation(if any), detection network used, training
parameters/hyper-parameters and anchor box tuning.

### Dataset: 
* Download the mp3.tar.gz and txt.tar.gz files from [here](https://doi.org/10.5281/zenodo.3893954). The dataset is for **research** purposes only.
  * Extract these files using: tar -xv --use-compress-program=pigz -f file_name. 
  * After extracting the files convert the .mp3 files to .wav files before training and testing. 
  * Once downloaded update the .csv files at E2E_NER/data/ner/.
* Total number of classes are 3: Person, Location, and Organization. 
* Added files to identify the source of an utterance from the source dataset. Files are at `E2E_NER/data/ner/source_given_filename.json` and `E2E_NER/data/ner/source.json
  * source_given_filename.json: It has the file names which are present in the individual source dataset for easy comparision.
  * source.json: It has the links to download the source datasets.

### Dataset preparation steps:
* The dataset for this task is prepared with special symbols at the end and at the start.
* Apart from the default data augmentation (Tempo and gain), We did not use any augmented data for training. <br/>

**Base neural net used:** A standard [DS2]("https://arxiv.org/pdf/1512.02595.pdf") architecture is used for the E2E NER implementation with default parameters.

### Experimental results: <br/>
| System   | Category     | Precision | Recall | F1     |
| -------- | ------------ | --------- | ------ | ------ |
| Two-step |Micro average | 0.83      |0.77    |0.80    |
| E2E NER  |Micro average | **0.96**  |**0.85**|**0.90**|

### Citation

@article{yadav2020end,<br/>
  title={End-to-end Named Entity Recognition from English Speech},<br/>
  author={Yadav, Hemant and Ghosh, Sreyan and Yu, Yi and Shah, Rajiv Ratn},<br/>
  journal={arXiv preprint arXiv:2005.11184},<br/>
  year={2020}<br/>
}<br/>

[Paper](https://arxiv.org/abs/2005.11184) is accepted at interspeech2020.

## Release Notes
Jun 2020
* Initital release

For any queries [Hemant](raotnameh@gmail.com), [Sreyan](gsreyan@gmail.com).
