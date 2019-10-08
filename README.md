# Tracking Progress in Rich Context

[The Coleridge Initiative](https://coleridgeinitiative.org/richcontext) 
at NYU has been researching [*Rich Context*](https://coleridgeinitiative.org/richcontext) to enhance search and discovery of datasets used in scientific research – see the [_Background Info_](https://github.com/Coleridge-Initiative/rclc/wiki/Background-Info) section for more details.
Partnering with experts throughout academia and industry, NYU-CI has
worked to leverage the closely adjacent fields of NLP/NLU, knowledge
graph, recommender systems, scholarly infrastructure, data mining from
scientific literature, dataset discovery, linked data, open vocabularies, metadata management, data governance, and so on.
Leaderboards are published here on GitHub to track _state-of-the-art_ (SOTA) progress among the top results.

---

## Leaderboard 1

### Entity Linking for Datasets in Publications

The first challenge is to identify the datasets used in research
publications, initially focused on the problem of 
[_entity linking_](https://nlpprogress.com/english/entity_linking.html).
Research papers will generally mention the datasets they've used, although there are no formal means to describe that metadata in a machine-readable way.

Identifying dataset mentions typically requires:

  * extracting text from an open access PDF
  * some NLP parsing of the text
  * feature engineering (e.g., paying attention to where the text is located in the paper)
  * modeling to identify up to 5 datasets per publication

See [_Evaluating Models for Entity Linking with Datasets_](https://github.com/Coleridge-Initiative/rclc/wiki/Evaluating-Models-for-Entity-Linking-with-Datasets) for details about how the `Top5uptoD` leaderboard metric is calculated.

### Current SOTA

|  source | precision  | repo | corpus | date | contact |
| ------- | :----:| :----: | :----: | ---------- | :-----------: |
| [LARC](https://github.com/LARC-CMU-SMU) | 78.36 | [link]( https://github.com/LARC-CMU-SMU/rclc_2019_baseline) | [v0.1.5](https://github.com/Coleridge-Initiative/rclc/releases/tag/v0.1.5) | 2019-09-26 | [@philipskokoh](https://github.com/philipskokoh) |

---

## Instructions

  * [How To Participate](https://github.com/Coleridge-Initiative/rclc/wiki/How-To-Participate)
  * [Corpus Description](https://github.com/Coleridge-Initiative/rclc/wiki/Corpus-Description)
  * [Downloading Resource Files](https://github.com/Coleridge-Initiative/rclc/wiki/Downloading-Resource-Files)
  * [Background Info](https://github.com/Coleridge-Initiative/rclc/wiki/Background-Info)
  * [Workflow Stages](https://github.com/Coleridge-Initiative/rclc/wiki/Workflow-Stages)
  * [Glossary Terms](https://github.com/Coleridge-Initiative/rclc/wiki/Glossary-Terms)

Use of open source and open standards are especially important to
further the cause for effective, reproducible research. 
We're hosting this competition to focus on the research challenges of specific machine learning use cases encountered within Rich Context – see the [_Workflow Stages_](https://github.com/Coleridge-Initiative/rclc/wiki/Workflow-Stages) section. 

If you have any questions about the Rich Context leaderboard competition – and especially if you identify any problems in the corpus (e.g., data quality, incorrect metadata, broken links, etc.) – please use the GitHub issues for this repo and pull requests to report, discuss, and resolve them.
