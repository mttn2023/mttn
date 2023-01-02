# MTTN: Multi-Pair Text to Text Narratives for Prompt Generation

MTTN is a dataset which is aimed for text-2-text generation, with a focus on diffusion model prompts. The model trained on this data will be able to fill gaps and create natural propmts that can be used to generate images directly.

MTTN is derived from different popular text datasets, including MS-COCO, WiT, Flickr, Conceptual captions which were then merged with a large collection of independent prompts that were originally used for image generations.

___

## Dataset Description

To form MTTN, the data was cleaned of any trailing *ASCII* values of special characters, following which there different *Emojis* were removed. Finally the dataset was then stripped step by step till we were left with only subject and objects of the sentences. The following are the columns of the dataset with one sample data:

Original | Special Chars Removed | Emoji_removed | stage1 | stage2 | stage3 | stage4 | stage5
--- | --- | --- | --- | --- | --- | --- | ---
A clock sitting next to a pier, with a group of people below it | A clock sitting next to a pier with a group of people below it | a clock sitting next to a pier with a group of people below it | clock sitting next to pier with group of people below it | clock sitting next to pier with group of people below it | clock sitting next pier people | clock next pier people | clock next pier people



## Paper and datasets

MTTN paper can be accessed from [here]().

MTTN has been divided into the following splits for easy access, training and testing of different LLM.
The complete list is given below:

Name | Link | Description
--- | --- | ---
MTTN - 100K | [Download]() | 100K randomly sample data from the entire MTTN dataset
MTTN - 250K | [Download]() | 250K randomly sample data from the entire MTTN dataset
MTTN - 500K | [Download]() | 500K randomly sample data from the entire MTTN dataset
MTTN - 1M   | [Download]() | 1M randomly sample data from the entire MTTN dataset
MTTN - 2.5M | [Download]() | The full dataset that was created, containing more than 2.5 million samples

## Usage

All the subsets are available in json format, and can be used in the following manner in python:
```python
import pandas as pd

df = pd.read_json('file_path', orient='split', compression='infer')
```

Output:
```python
>>>df
0    vintage poster of a savage wild alien planet, ...    vintage poster of a savage wild alien planet s...    vintage poster of a savage wild alien planet s...    vintage poster of savage wild alien planet sea...    vintage poster of savage wild alien planet sea...    vintage poster savage alien planet sea highly ...    vintage poster savage alien planet sea highly ...    vintage poster savage alien planet sea highly ...
1    the ethereal god of technology bestows the gif...    the ethereal god of technology bestows the gif...    the ethereal god of technology bestows the gif...    ethereal god of technology bestows gift of gre...    ethereal god of technology bestows gift of gre...    ethereal god technology bestows gift circuits ...    ethereal god technology bestows gift circuits ...    ethereal god technology bestows gift circuits ...
2    beautiful black woman fixing hair in the morning    beautiful black woman fixing hair in the morning    beautiful black woman fixing hair in the morning    beautiful black woman fixing hair in morning    beautiful black woman fixing hair in morning    woman fixing hair morning    woman hair morning    woman hair morning
```
