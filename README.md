# CompSpoof V2 Dataset

## 1. Introduction

CompSpoof V2 is a dataset designed for component-level anti-spoofing detection research, where either the speech or the environmental sound component (or both) may be spoofed.

CompSpoof V2 contains over 250k audio samples, with a total duration of approximately 283 hours. 
Each audio sample has a fixed length of 4 seconds and is provided at multiple sampling rates, enabling a more faithful simulation of real-world acoustic and system-level variations.

Building upon [CompSpoof dataset](https://xuepingzhang.github.io/CompSpoof-dataset/), CompSpoof V2 significantly expands the diversity of attack sources, environmental sounds, and mixing strategies. 
In addition, newly generated audio samples are distributed across the test set and are specifically designed to serve as detection data under unseen conditions. 
To further simulate realistic transmission effects, portions of the test set are processed using various audio codec toolkits.


**CompSpoof V2 Download Link:** [https://huggingface.co/datasets/XuepingZhang/ESDD2-CompSpoof-V2/](https://huggingface.co/datasets/XuepingZhang/ESDD2-CompSpoof-V2/)

**Baseline code:** [https://github.com/XuepingZhang/ESDD2-Baseline](https://github.com/XuepingZhang/ESDD2-Baseline)

---

## 2. Audio Class Description and Samples
Below are audio samples from the **CompSpoof V2** dataset. For each class, we provide the **mixed/original audio**, along with the **speech** and **environment** sources.

### Class 0 — Original 

**Label:** original 

**Description:** Original bona fide speech and corresponding environment audio without mixing

<table>
  <thead>
    <tr>
      <th>Original</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        <audio controls>
          <source src="audio_demo/class0/original.wav" type="audio/mpeg">
        </audio>
      </td>
    </tr>
  </tbody>
</table>

### Class 1 — Bona fide + Bona fide 

**Label:** bonafide_bonafide 

**Description:** Bona fide speech mixed with another bona fide environmental audio

<table>
  <thead>
    <tr>
      <th>Mixed</th>
      <th>Speech</th>
      <th>Environment</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        <audio controls>
          <source src="audio_demo/class1/52257_bonafide_bonafide.wav" type="audio/mpeg">
        </audio>
      </td>
      <td>
      <audio controls>
          <source src="audio_demo/class1/common_voice_en_161723_chunk0.wav" type="audio/mpeg">
        </audio>
      </td>
      <td>
      <audio controls>
          <source src="audio_demo/class1/rXHHLtG_iGQ_000562.mp4_chunk1.wav" type="audio/mpeg">
        </audio>
      </td>
    </tr>
  </tbody>
</table>


### Class 2 — Spoofed Speech + Bona fide Environment 

**Label:** spoof_bonafide 

**Description:** Spoof speech mixed with bona fide environmental audio
<table>
  <thead>
    <tr>
      <th>Mixed</th>
      <th>Speech</th>
      <th>Environment</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        <audio controls>
          <source src="audio_demo/class2/48570_spoof_bonafide.wav" type="audio/mpeg">
        </audio>
      </td>
      <td>
      <audio controls>
          <source src="audio_demo/class2/hunters_space_09_f000072_chunk2.wav" type="audio/mpeg">
        </audio>
      </td>
      <td>
      <audio controls>
          <source src="audio_demo/class2/uBaRlBqQj3A_000496.mp4_chunk2.wav" type="audio/mpeg">
        </audio>
      </td>
    </tr>
  </tbody>
</table>


### Class 3 — Bona fide Speech + Spoofed Environment 

**Label:** bonafide_spoof 

**Description:** Bona fide speech mixed with spoof environmental audio

<table>
  <thead>
    <tr>
      <th>Mixed</th>
      <th>Speech</th>
      <th>Environment</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        <audio controls>
          <source src="audio_demo/class3/124039_bonafide_spoof.wav" type="audio/mpeg">
        </audio>
      </td>
      <td>
      <audio controls>
          <source src="audio_demo/class3/common_voice_en_22168656_chunk0.wav" type="audio/mpeg">
        </audio>
      </td>
      <td>
      <audio controls>
          <source src="audio_demo/class3/metro_station-barcelona-61-1847-a_0.wav" type="audio/mpeg">
        </audio>
      </td>
    </tr>
  </tbody>
</table>


### Class 4 — Spoofed Speech + Spoofed Environment 

**Label:** spoof_spoof 

**Description:** Spoof speech mixed with spoof environmental audio

<table>
  <thead>
    <tr>
      <th>Mixed</th>
      <th>Speech</th>
      <th>Environment</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        <audio controls>
          <source src="audio_demo/class4/513140_spoof_spoof.wav" type="audio/mpeg">
        </audio>
      </td>
      <td>
      <audio controls>
          <source src="audio_demo/class4/jane_eyre_21_f000330_chunk0.wav" type="audio/mpeg">
        </audio>
      </td>
      <td>
      <audio controls>
          <source src="audio_demo/class4/b033_0.wav" type="audio/mpeg">
        </audio>
      </td>
    </tr>
  </tbody>
</table>


***

## 3. CompSpoof V2 VS CompSpoof
[CompSpoof dataset](https://xuepingzhang.github.io/CompSpoof-dataset/) is our previously released dataset designed for component-level spoofing detection.
Building upon this foundation, we introduce CompSpoof V2, a substantially upgraded version with expanded task formulation.
The key differences between CompSpoof and CompSpoof V2 are summarized below.

| Aspect                | CompSpoof                       | CompSpoof V2                                                                                                                       |
|-----------------------|---------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
| Data volume           | 2.5k audio clips, about 7 hours | more than 250k audio clips, about 283 hours                                                                                        |
| Data sources          | SSTC, ASV5, VggSound, VcapAV, Common Voice  | AudioCaps, VggSound, CommonVoice, LibriTTS, english-conversation-corpus,ASV5, MLAAD,TUTASC, TUTSED, UrbanSound, VGGSound, EnvSDD, VcapAV |
| Duration              | range from 5 to 21 seconds      | 4 seconds/audio clip                                                                                                               |
| Codec transformation  | ❌                               | ✅                                                                                                                                  |
| Newly generated audio | ❌                               | ✅                                                                                                                                  |


---

## 4. Dataset Structure

The dataset follows a hierarchical directory structure organized by data split:

```text
CompSpoof
├── development                     # training and val data，including audio source
│   ├── env_source                  # environmental sound audio used as the environmental sound component in the mixture
│   ├── metadata                    # metadata of development set
│       ├── train.csv
│       └── val.csv
│   ├── mixed_audio                 # mixed audio files, which **don't** belong to the `original` class
│   ├── original_audio              # audios belong to `original` class
│   └── speech_sources              # speech audio used as the speech component in the mixture
│
├── test1                           # test1 set data, without audio source
│   ├── audio                       # audio files
│   └── metadata                    # metadata of test1 set, which only has file name and labels
│       └── test1.csv
│
├── test1_source (Released later)   # test1 set data，including audio source
│   ├── env_sources                 # environmental sound audio used as the environmental sound component in the mixture
│   ├── metadata                    # metadata of test1 set, with full annotation
│   │   └── test1.csv
│   ├── mixed_audio                 # mixed audio files, which **don't** belong to the `original` class
│   ├── original_audio              # audios belong to `original` class
│   └── speech_sources              # speech audio used as the speech component in the mixture
|
├── test2                           # test2 set data, without audio source
│   ├── audio                       # audio files
│   └── metadata                    # metadata of test2 set, which only has file name and without labels
│       └── test2.csv
│
└── test2_source (Released later)   # training and val data，including audio source
    ├── env_sources                 # environmental sound audio used as the environmental sound component in the mixture
    ├── metadata                    # metadata of test2 set, with full annotation
    │   └── test2.csv
    ├── mixed_audio                 # mixed audio files, which **don't** belong to the `original` class
    ├── original_audio              # audios belong to `original` class
    └── speech_sources              # speech audio used as the speech component in the mixture
```

---

## 5. Audio Source
The audio sources for each category are as follows:

### train & val set 

| Label             | Original Source      | Speech Source                                      | Environmental Sound Source                      |
|-------------------|--------------------|--------------------------------------------------|------------------------------------------------|
| original          | AudioCaps, VggSound | -                                                | -                                              |
| bonafide_bonafide | -                  | CommonVoice, LibriTTS, english-conversation-corpus | AudioCaps, TUTASC, TUTSED, UrbanSound, VGGSound |
| bonafide_spoof    | -                  | CommonVoice, LibriTTS                             | EnvSDD, VcapAV                                 |
| spoof_bonafide    | -                  | ASV5, MLAAD                                      | AudioCaps, TUTASC, TUTSED, UrbanSound, VGGSound |
| spoof_spoof       | -                  | ASV5, MLAAD                                      | EnvSDD, VcapAV                                 |



### test1 & test2 set

| Label             | original source     | speech source                                      | environmental sound source                      |
|-------------------|---------------------|----------------------------------------------------|-------------------------------------------------|
| original          | AudioCaps, VggSound | -                                                  | -                                               |
| bonafide_bonafide | -                   | CommonVoice, LibriTTS, english-conversation-corpus | AudioCaps, TUTASC, TUTSED, UrbanSound, VGGSound |
| bonafide_spoof    | -                   | CommonVoice, LibriTTS                              | EnvSDD, VcapAV, **New Generated**                   |
| spoof_bonafide    | -                   | ASV5, MLAAD, **New Generated**                         | AudioCaps, TUTASC, TUTSED, UrbanSound, VGGSound |
| spoof_spoof       | -                   | ASV5, MLAAD, **New Generated**                         | EnvSDD, VcapAV, **New Generated**                   |


---

## 6. Data Splits

The dataset is divided into three standard splits:

* **Training set**: used for model training
* **Validation set**: used for validation and hyper-parameter tuning
* **Test1 & Test2 set**: used for final performance reporting

Training set and validation set have the same date source and class distribution.

Test1 set and Test2 set share the same date source and class distribution.
Test1 set and Test2 set share some new generated audios which are **unseen** in training and validation set.
Portions of the test1 set and test2 set have been processed with audio **codec toolkits**.

The quantity and proportion of audios for each category in each set are as follows:

### train set (Total: 175361)

| Label             | Count   | Ratio   |
|:------------------|---------|---------|
| bonafide_spoof    | 50361   | 28.72%  |
| original          | 48639   | 27.74%  |
| spoof_spoof       | 29413   | 16.77%  |
| bonafide_bonafide | 25189   | 14.36%  |
| spoof_bonafide    | 21759   | 12.41%  |


### val set (Total: 24864)

| Label             | Count   | Ratio   |
|:------------------|---------|---------|
| bonafide_spoof    | 8071    | 32.46%  |
| original          | 6939    | 27.91%  |
| spoof_spoof       | 4657    | 18.73%  |
| bonafide_bonafide | 2784    | 11.20%  |
| spoof_bonafide    | 2413    | 9.70%   |



### test1 set (Total: 27605)

| Label             | Count   | Ratio   |
|:------------------|---------|---------|
| bonafide_spoof    | 7655    | 27.73%  |
| original          | 7455    | 27.01%  |
| spoof_spoof       | 5945    | 21.54%  |
| bonafide_bonafide | 3570    | 12.93%  |
| spoof_bonafide    | 2980    | 10.80%  |

### test2 set (Total: 27603)

| Label             | Count   | Ratio   |
|:------------------|---------|---------|
| bonafide_spoof    | 7672    | 27.79%  |
| original          | 7415    | 26.86%  |
| spoof_spoof       | 5894    | 21.35%  |
| bonafide_bonafide | 3635    | 13.17%  |
| spoof_bonafide    | 2987    | 10.82%  |


---

## 7. Metadata

Metadata is provided in CSV format, with **one row per audio file**. Each field describes the source, generation process, and mixing configuration of the corresponding composite spoofing sample.

The meaning of each field in Metadata is as follows:

* **`audio_path`**: Relative path to the final mixed audio file used for training or evaluation.

* **`label`**: Class label of the audio sample. Typical values include: original, bonafide_bonafide, spoof_bonafide, bonafide_spoof, spoof,spoof

* **`split`**: Dataset split indicator: train, val, test

* **`original_audio_source`**: Source dataset of the original audio, e.g., AudioCaps.


---

* **`speech_path`**: Path to the speech signal used as the speech component in the mixture.

* **`speech_source`**: Source dataset of the speech signal, e.g., ASV5, CommonVoice.

* **`speech_generation_mothed`**: Generation method used to produce the speech signal, e.g., TTS (text-to-speech), VC (voice-conversion).

* **`speech_generation_source`**: Dataset to generate the spoofed speech, e.g., a spoofed speech is generated by TTS, the text for generation is the source. 

* **`speech_generation_model`**: Model used to generate the spoofed speech.

---

* **`env_path`**: Path to the environmental sound used as the environmental sound component in the mixture.

* **`env_source`**: Source dataset of the environmental sound, e.g., EnvSDD, VcapAV.

* **`env_generation_mothed`**: Method used to generate the spoofed environmental sound, e.g.,TTA (text-to-audio).

* **`env_generation_source`**: Dataset to  generate the spoofed environmental sound, e.g., a spoofed **speech** is generated by **TTS**, the text for generation is the source. 

* **`env_generation_model`**:Model used to generate the spoofed environmental sound.

---

* **`mix_target_snr`**: Target signal-to-noise ratio (SNR, in dB) used when mixing the speech and environmental sound.

---

## 8. Citation

If you use CompSpoof V2 in your research, please cite the corresponding paper:

```
@dataset{zhang2025esdd2compspoofv2,
  title     = {ESDD2-CompSpoof-V2: A Composite Spoofing Dataset for Speech Anti-Spoofing},
  author    = {Zhang, Xueping and Li, Ming},
  year      = {2025},
  publisher = {Hugging Face},
  url       = {https://huggingface.co/datasets/XuepingZhang/ESDD2-CompSpoof-V2}
}

```


---

## 9. License
This dataset is a derived dataset constructed by combining and mixing audio samples from multiple publicly available datasets.
  - The **MLAAD** and **VCapAV** datasets are released under the [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/deed.en) license.
  - The **LibriTTS**, **EnvSDD** and **VGGSound** datasets is released under the [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) license.
  - The **Common Voice** dataset is released under the Creative Commons [CC0 1.0 Universal](https://creativecommons.org/publicdomain/zero/1.0/deed.en) license.
  - The **ASVspoof 5** dataset is released under the [ODC-By](https://huggingface.co/datasets/jungjee/asvspoof5/blob/main/LICENSE.txt) License.
  - The **english-conversation-corpus** dataset is released under the [GPLv3](https://github.com/thuhcsi/english-conversation-corpus/blob/master/LICENSE)License.
  - The **AudioCaps** dataset is released under the [mit](https://choosealicense.com/licenses/mit/) License.
  - The **TUTASC**, **TUTSED** and **UrbanSound** datasets are released under the Non-Commercial License.


  Users must comply with the license terms of each original dataset.
  The authors do **not** claim ownership of the original audio content.
  Due to the inclusion of datasets licensed under [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/deed.en) license, **this dataset is released under the [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/deed.en) license**.

---

## 10. Contact Information

For questions, issues, or collaboration inquiries, please contact:
* Email: [xueping.zhang@dukekunshan.edu.cn](xueping.zhang@dukekunshan.edu.cn)


