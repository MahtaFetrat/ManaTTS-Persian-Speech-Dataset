# ManaTTS-Persian-Speech-Dataset

ManaTTS is the largest publicly accessible single-speaker Persian corpus, comprising over 114 hours of audio with a sampling rate of 44.1 kHz. It is released under the open CC-0 license, enabling educational and commercial use. This dataset is a comprehensive speech dataset for the Persian language, collected from the [Nasl-e-Mana](https://naslemana.com/) magazine. It includes a wide range of topics and domains, making it suitable for training high-quality text-to-speech models. The dataset is accompanied by a fully transparent, open-source pipeline for data collection and processing, including tools for audio segmentation and forced alignment.

## Dataset
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-dataset-orange)](https://huggingface.co/datasets/MahtaFetrat/Mana-TTS)

The ManaTTS dataset can be downloaded from [this link](https://huggingface.co/datasets/MahtaFetrat/Mana-TTS). You can access a smaller, random sample of this dataset in the [sampled data directory](sample_data). These samples were selected to reflect the same distribution of match qualities as the complete dataset. For more details on match qualities, please refer to [the paper](https://aclanthology.org/2025.naacl-long.464/).

## Raw Data Crawling
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1_E5KYAwuCr9B8k6EPYjVErsx-7rrr8Vl?usp=sharing) 

The raw data for this dataset was crawled from the Nasl-e-Mana magazine website. The crawling script used for this purpose is also provided in this repository and on Google Colab in [this link](https://colab.research.google.com/drive/1_E5KYAwuCr9B8k6EPYjVErsx-7rrr8Vl?usp=sharing).

## Processing Pipeline
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1fWTy4IH2tSuOLrLSD8E8LMaUlI_Gnf-e?usp=sharing) 

The following figure illustrates the overall processing pipeline used to create the ManaTTS dataset, including the steps for preproces

<p align="center">
  <img src="https://github.com/MahtaFetrat/ManaTTS-Persian-Speech-Dataset/assets/62302965/b3bf8dd1-f315-4278-bcd2-6ca80832fdcf" width="800">
</p>

This pipeline is available as a Jupyter Notebook included in this repository.  You can also run the notebook on Google Colab using [this link](https://colab.research.google.com/drive/1fWTy4IH2tSuOLrLSD8E8LMaUlI_Gnf-e?usp=sharing).

To run the pipeline, follow these steps:

1. Set up the required environment (details in the notebook)
2. Place the raw audio and text files in a directory named `raw`
3. Execute the cells in the notebook sequentially

## Trained TTS Model
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-model-orange)](https://huggingface.co/MahtaFetrat/Persian-Tacotron2-on-ManaTTS)

A text-to-speech (TTS) model has been trained on the ManaTTS dataset. The code for training the model, as well as some output samples, are available in [this repository](https://github.com/MahtaFetrat/Persian-MultiSpeaker-Tacotron2). The model weights and inference instructions can be found in [this repository](https://huggingface.co/MahtaFetrat/Persian-Tacotron2-on-ManaTTS).

## Contributing
Contributions to this project are welcome! If you encounter any issues or have suggestions for improvements, please open an issue or submit a pull request.

## License
The ManaTTS dataset is released under the CC-0 1.0 license, while the processing pipeline is licensed under the MIT license.

## Important Notice on Ethical Use of ManaTTS Dataset

The ManaTTS dataset is provided exclusively for research and development purposes. We emphasize the critical importance of ethical conduct in utilizing this dataset. Please refrain from any misuse, including but not limited to voice impersonation, identity theft, or fraudulent activities. 

By accessing and using the ManaTTS dataset, you are obligated to uphold the highest standards of integrity and respect for user privacy. Any violation of these principles may have severe legal and ethical consequences.

For any inquiries or clarifications regarding the use of this dataset, please reach out to us. Your cooperation in ensuring responsible use of this dataset is greatly appreciated.

## Acknowledgment

We would like to express our sincere gratitude to [Nasl-e-Mana](https://naslemana.com/), the monthly magazine of the blind community of Iran, for their generosity. Their commitment to openness and collaboration has been instrumental in advancing research and development in speech synthesis. We are especially thankful for their choice to release the data under the Creative Commons CC-0 license, allowing for unrestricted use and distribution.


## Collaboration and Community Impact
We encourage researchers, developers, and the broader community to utilize the resources provided in this project, particularly in the development of high-quality screen readers and other assistive technologies to support the Iranian blind community. By fostering open-source collaboration, we aim to drive innovation and improve accessibility for all.


## Citation
If you use this dataset or the processing pipeline in your work, please cite the following paper:

```bash
@inproceedings{qharabagh-etal-2025-manatts,
    title = "{M}ana{TTS} {P}ersian: a recipe for creating {TTS} datasets for lower resource languages",
    author = "Qharabagh, Mahta Fetrat  and Dehghanian, Zahra  and Rabiee, Hamid R.",
    booktitle = "Proceedings of the 2025 Conference of the Nations of the Americas Chapter of the Association for Computational Linguistics: Human Language Technologies (Volume 1: Long Papers)",
    month = apr,
    year = "2025",
    address = "Albuquerque, New Mexico",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2025.naacl-long.464/",
    pages = "9177--9206",
}
```

# ManaTTS-Persian-Speech-Dataset  

**ManaTTS** is the largest publicly available single-speaker Persian corpus, comprising over **114 hours** of high-quality audio (sampled at **44.1 kHz**). Released under the permissive **CC-0 license**, this dataset is freely usable for both educational and commercial purposes.  

Collected from **[Nasl-e-Mana](https://naslemana.com/)** magazine, the dataset covers a diverse range of topics, making it ideal for training robust **text-to-speech (TTS) models**. The release includes a **fully transparent, open-source pipeline** for data collection and processing, featuring tools for **audio segmentation** and **forced alignment**. For the full codebase, visit the **[ManaTTS GitHub repository](https://github.com/MahtaFetrat/ManaTTS-Persian-Speech-Dataset)**.  

---

### Dataset Columns  

| Column Name      | Description |
|------------------|-------------|
| **file_name**    | Unique identifier for the audio file. |
| **transcript**   | Ground-truth text transcription of the audio chunk. |
| **duration**     | Duration of the audio chunk (in seconds). |
| **match_quality** | Quality of alignment between the approximate transcript and ground truth (`HIGH` or `MIDDLE`). Reflects confidence in transcript accuracy (see [paper](https://aclanthology.org/2025.naacl-long.464/) for details). |
| **hypothesis**   | Approximate transcript used to search for the ground-truth text. |
| **CER**          | Character Error Rate between the hypothesis and accepted transcript. |
| **search_type**  | Indicates whether the transcript was matched continuously in the source text (`type 1`) or with gaps (`type 2`). |
| **ASRs**         | Ordered list of ASRs used until a match was found. |
| **audio**        | Audio file as a numerical array. |
| **sample_rate**  | Sampling rate of the audio file (44.1 kHz). |

---

## Usage

### Python (Hugging Face)
First install the required package:
```bash
pip install datasets
```

Then load the data:
```python
from datasets import load_dataset

# Load a specific partition (e.g., part 001)
dataset = load_dataset("MahtaFetrat/Mana-TTS", 
                      data_files="dataset/dataset_part_001.parquet", 
                      split="train")

# Inspect the data
print(dataset)
print(dataset[0])  # View first sample
```

### Command Line (wget)
Download individual files directly:
```bash
# Download single file (e.g., part 001)
wget https://huggingface.co/datasets/MahtaFetrat/Mana-TTS/resolve/main/dataset/dataset_part_001.parquet
```

---

## Trained TTS Model  

[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-Model-orange)](https://huggingface.co/MahtaFetrat/Persian-Tacotron2-on-ManaTTS)  

A **Tacotron2-based TTS model** trained on ManaTTS is available on Hugging Face. For inference and weights, visit the [model repository](https://huggingface.co/MahtaFetrat/Persian-Tacotron2-on-ManaTTS).  

---

## Contributing  

Contributions to this project are welcome! If you encounter any issues or have suggestions for improvements, please open an issue or submit a pull request.

---

## License  

This dataset is released under the **[CC-0 1.0 license](https://creativecommons.org/publicdomain/zero/1.0/)**.  

---

## Ethical Use Notice  

The ManaTTS dataset is intended **exclusively for ethical research and development**. Misuse—including voice impersonation, identity theft, or fraudulent activities—is strictly prohibited. By using this dataset, you agree to uphold **integrity and privacy standards**. Violations may result in legal consequences.  

For questions, contact the maintainers.  

---

## Acknowledgments  

We extend our deepest gratitude to **[Nasl-e-Mana](https://naslemana.com/)**, the monthly magazine of Iran’s blind community, for their generosity in releasing this data under **CC-0**. Their commitment to open collaboration has been pivotal in advancing Persian speech synthesis.  

---

## Community Impact  

We encourage researchers and developers to leverage this resource for **assistive technologies**, such as screen readers, to benefit the Iranian blind community. Open-source collaboration is key to driving accessibility innovation.  

---

## Citation  

If you use ManaTTS in your work, cite our paper:  

```bibtex
@inproceedings{qharabagh-etal-2025-manatts,
    title = "{M}ana{TTS} {P}ersian: A Recipe for Creating {TTS} Datasets for Lower-Resource Languages",
    author = "Qharabagh, Mahta Fetrat and Dehghanian, Zahra and Rabiee, Hamid R.",
    booktitle = "Proceedings of the 2025 Conference of the North American Chapter of the Association for Computational Linguistics",
    month = apr,
    year = "2025",
    address = "Albuquerque, New Mexico",
    publisher = "Association for Computational Linguistics",
    pages = "9177--9206",
    url = "https://aclanthology.org/2025.naacl-long.464/",
}
```

---


## Aditional Links
- [ManaTTS Huggingface Repository](https://huggingface.co/datasets/MahtaFetrat/Mana-TTS)
- [ManaTTS Paper](https://aclanthology.org/2025.naacl-long.464/)
- [Nasl-e-Mana Magazine](https://naslemana.com/)
- Tacotron2 Trained on ManaTTS [Huggingface](https://huggingface.co/MahtaFetrat/Persian-Tacotron2-on-ManaTTS) | [Github](https://github.com/MahtaFetrat/ManaTTS-Persian-Tacotron2-Model)
