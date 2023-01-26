# MTTN: Multi-Pair Text to Text Narratives for Prompt Generation :books: :left_right_arrow: :page_facing_up: :speech_balloon:

MTTN(read mutton) is a dataset which is aimed for text-2-text generation, with a focus on diffusion model prompts. The model trained on this data will be able to fill gaps and create natural propmts that can be used to generate images directly.

MTTN is derived from different popular text datasets, including 
* [MS-COCO](https://cocodataset.org/) 
* [WiT](https://arxiv.org/abs/2103.01913)
* [Flickr](https://shannon.cs.illinois.edu/DenotationGraph/)
* [Conceptual captions](https://ai.google.com/research/ConceptualCaptions/) 

which were then merged with a  ***large collection of independent prompts***  that were originally used for image generations.

___

## Dataset Description :ledger:

To form MTTN, the data was cleaned of any trailing *ASCII* values of special characters, following which there different *Emojis* were removed. Finally the dataset was then stripped step by step till we were left with only subject and objects of the sentences. The following are the columns of the dataset with one sample data:

Original | Special Chars Removed | Emoji_removed | stage1 | stage2 | stage3 | stage4 | stage5
--- | --- | --- | --- | --- | --- | --- | ---
A clock sitting next to a pier, with a group of people below it | A clock sitting next to a pier with a group of people below it | a clock sitting next to a pier with a group of people below it | clock sitting next to pier with group of people below it | clock sitting next to pier with group of people below it | clock sitting next pier people | clock next pier people | clock next pier people



## Paper and datasets :pencil:

MTTN paper can be accessed from [here]().

MTTN has been divided into the following splits for easy access, training and testing of different LLM.
The complete list is given below:

Name | Link :link: | Description
--- | --- | ---
MTTN - 100K | [Download](https://drive.google.com/file/d/10bWK_Q_FaWim11i9uob_0ConOLqdry_X/view?usp=share_link) | 100K randomly sample data from the entire MTTN dataset
MTTN - 250K | [Download](https://drive.google.com/file/d/1-A7JXLEIEHKaSnqKQYc7VS3sEY70UhRj/view?usp=share_link) | 250K randomly sample data from the entire MTTN dataset
MTTN - 500K | [Download](https://drive.google.com/file/d/1-AZVVvYPbttpZz9rHmnjeSCyqTu4uszU/view?usp=share_link) | 500K randomly sample data from the entire MTTN dataset
MTTN - 1M   | [Download](https://drive.google.com/file/d/1-EeCso_umR1elWcLJwWH1D0cPpKJCK-7/view?usp=share_link) | 1M randomly sample data from the entire MTTN dataset
MTTN - 2.4M | [Download](https://drive.google.com/file/d/1-JoRvYprRQg7KUX5ad63O1gZbzMSJDLl/view?usp=share_link) | The full dataset that was created, containing more than 2.4 million samples

## Usage :bar_chart:

All the subsets are available in json format, and can be used in the following manner in python:
```python
import pandas as pd

df = pd.read_json('downloaded_json_file_path', orient='split', compression='infer')
```

Output:
```python
>>>df
0    vintage poster of a savage wild alien planet, ...    vintage poster of a savage wild alien planet s...    vintage poster of a savage wild alien planet s...    vintage poster of savage wild alien planet sea...    vintage poster of savage wild alien planet sea...    vintage poster savage alien planet sea highly ...    vintage poster savage alien planet sea highly ...    vintage poster savage alien planet sea highly ...
1    the ethereal god of technology bestows the gif...    the ethereal god of technology bestows the gif...    the ethereal god of technology bestows the gif...    ethereal god of technology bestows gift of gre...    ethereal god of technology bestows gift of gre...    ethereal god technology bestows gift circuits ...    ethereal god technology bestows gift circuits ...    ethereal god technology bestows gift circuits ...
2    beautiful black woman fixing hair in the morning    beautiful black woman fixing hair in the morning    beautiful black woman fixing hair in the morning    beautiful black woman fixing hair in morning    beautiful black woman fixing hair in morning    woman fixing hair morning    woman hair morning    woman hair morning
```
___
## Citation :pushpin:	
Cite the dataset using our [paper](https://arxiv.org/abs/2301.10172):
```bibtex
@misc{https://doi.org/10.48550/arxiv.2301.10172,
  doi = {10.48550/ARXIV.2301.10172},
  
  url = {https://arxiv.org/abs/2301.10172},
  
  author = {Ghosh, Archan and Ghosh, Debgandhar and Maji, Madhurima and Chanda, Suchinta and Goswami, Kalporup},
  
  keywords = {Computation and Language (cs.CL), Machine Learning (cs.LG), FOS: Computer and information sciences, FOS: Computer and information sciences},
  
  title = {MTTN: Multi-Pair Text to Text Narratives for Prompt Generation},
  
  publisher = {arXiv},
  
  year = {2023},
  
  copyright = {Creative Commons Attribution Share Alike 4.0 International}
}
```
