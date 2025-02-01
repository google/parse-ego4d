# PARSE-Ego4D
 This repo contains the code and data for the PARSE-Ego4D in the paper [``PARSE-Ego4D: Personal Action Recommendation Suggestions for Egocentric Videos``](https://arxiv.org/abs/2407.09503).
 
 ```
@article{abreu2024parseego4d,
  author    = {Abreu, Steven and Do, Tiffany and Ahuja, Karan and Gonzalez, Eric J and Payne, Lee and McDuff, daniel and Gonzalez-Franco, Mar},
  title     = {PARSE-Ego4D Personal Action Recommendation Suggestions for Egocentric Videos},
  journal   = {},
  year      = {2024},
}
```

## Overview
PARSE-Ego4D aims at solving the space of intelligent assistance involving not only understanding but also action. Existing ego-centric video datasets contain rich annotations of the videos, but not of actions that an intelligent assistant could perform in the moment. To address this gap, we release PARSE-Ego4D, a new set of personal action recommendation annotations for the Ego4D dataset. We take a multi-stage approach to generating and evaluating these annotations. First, we used a prompt-engineered large language model (LLM) to generate context-aware action suggestions and identified over 18,000 action suggestions. While these synthetic action suggestions are valuable, the inherent limitations of LLMs necessitate human evaluation. To ensure high-quality and user-centered recommendations, we conducted a large-scale human annotation study that provides grounding in human preferences for all of PARSE-Ego4D. We analyze the inter-rater agreement and evaluate subjective preferences of participants. Based on our synthetic dataset and complete human annotations, we propose several new tasks for action suggestions based on ego-centric videos. The annotations in PARSE-Ego4D will support researchers and developers who are working on building action recommendation systems for augmented and virtual reality systems

More details can be found on the project page: https://parse-ego4d.github.io/ 



## Data
Parse-Ego4D dataset includes 18,000 suggested actions. The dataset is split into three different files:

``data/suggestions.csv`` is the synthetic data generated by our LLM, Gemini Pro, that contains action suggestions for all snippets of Ego4D videos. The column Ego4D VideoID refers to the video ID in the Ego4D dataset which can be used to join this spreadsheet with the Ego4D dataset, in conjunction with the Batch idx and Batch size.
``data/annotations_raw.csv`` contains the raw annotations from our human user study on Prolific.
``data/annotations.csv`` contains the annotations aggregated per video snippet. This is the data used for all downstream ML tasks reported in the paper.
The common ID shared between all three spreadsheets is the ``suggestion_id``. In addition, the PARSE-Ego4D ID provides a unique mapping to the Ego4D database.

You’re free to copy, modify, and redistribute this data under the terms of the CC-BY license. See the [`LICENSE`](../LICENSE) file for details.


## Code
The dataset was generated using advanced prompting and LLM analysis and validated using a large human study with participants in Prolific with over human 36,171. Generation files are also provided in the form of ipython notebooks that can run on Google Colab:
``code/Ego4Ddatageneration.ipynb`` is the prompting and data processing tool that was used to parse all the narrations of ego4d.
``code/Ego4Dvideos.ipynb`` contains the code that cropped the videos to the suggested actions by PARSE-Ego4D so they could be later shown on our Prolific user study.
``code/Ego4Dcleaning_analysis.ipynb`` contains the annotations aggregated per video snippet. This is the data used for all downstream ML tasks reported in the paper.


## Main Contributors
- **Steve Abreu (Google and University of Gronigen)**
- **Tiffany Do (Google and University of Central Florida)**
- **Karan Ahuja (Google)**
- **Eric J Gonzalez (Google)**
- **Lee Payne (Google)**
- **Daniel McDuff (Google)**
- **Mar Gonzalez-Franco (Google)**  


## Contribute
To learn how to contribute to this project, read [CONTRIBUTING.md](../CONTRIBUTING.md).

## License
The code is released with Apache 2.0 License [LICENSE.txt](../LICENSE.txt).
The data is released with CC-BY-4.0 License [CC-BY-4.0](../data/CC-BY-4.0).