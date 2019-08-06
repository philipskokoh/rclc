# Tracking Progress in Rich Context

[The Coleridge Initiative](https://coleridgeinitiative.org/richcontext) at NYU has been researching [*Rich Context*](https://coleridgeinitiative.org/richcontext) to enhance search and discovery of datasets used in scientific research -- see below for background info.
Partnering with experts throughout academia and industry, NYU-CI has worked to leverage the closely adjacent fields of NLP/NLU, knowledge graph, recommender systems, scholarly infrastructure, data mining from scientific literature, dataset discovery, linked data, open vocabularies, metadata management, data governance, and so on.

Use of open source and open standards are especially important to further the cause for effective, reproducible research.
We are hosting this competition to focus on the challenges of specific machine learning use cases within Rich Context, then publishing a leaderboard on GitHub to track progress among the top results.


## How To Participate

To submit an entry for the leaderboard, each team must provide a link to their public GitHub repo that includes:

  1. Code in a single [Jupyter notebook](https://jupyter.org/) used to build their model and evaluate results -- referencing the [corpus](blob/master/corpus.jsonld) from this repo
  1. Configuration which allows anyone to run the notebook on [Binder](https://mybinder.org/) (see the [docs](https://mybinder.readthedocs.io/en/latest/introduction.html#preparing-a-repository-for-binder) and a [tutorial](http://ivory.idyll.org/blog/2017-four-steps-five-minutes-binder.html))
  1. An open source license for the code, configuration, and subsequent models produced
  1. A brief paper describing their approach

In other words, all entries must be open source and the public may evaluate the results online with a single click.

If you have any questions regarding the Rich Context Leaderboard or if there are any problems identified in the corpus (e.g., data quality, incorrect metadata, broken links, etc.) please use GitHub issues and pull requests to report, discuss, and resolve them.

Note that the corpus will be extended over time, with previous entries in the leaderboard being re-evaluated at each update.


---
## Entity Linking for Datasets in Publications

### Task

The first challenge is to identify the datasets used in research publications, initially focused on the problem of [entity linking](https://nlpprogress.com/english/entity_linking.html).
Research papers typically mention the datasets they've used, although the process to identify those mentions requires extracting text from the PDF, some NLP parsing of the text, feature engineering (e.g., paying attention to where is found in the paper), and so on.

The [corpus](blob/master/corpus.jsonld) for this challenge provides a graph of research publications linked with their datasets, and serialized as [JSON-LD](https://json-ld.org/) using the [ADRF vocabulary](https://github.com/Coleridge-Initiative/adrf-onto/wiki/Vocabulary), which is turn is based on [POD](https://sparontologies.github.io/cito/current/cito.html), [CITO](https://sparontologies.github.io/cito/current/cito.html), etc.
Each publication has properties for *uuid*, *title*, *journal*, an optional *doi*, plus a URL for an *open access pdf* – plus, a list of datasets used in that research.
Each dataset has properties for *uuid*, *name*, and *provider*.
These annotations have been verified by domain experts.


### Current SOTA

|  Source | Precision-at-K | Code | 
| ------------- | :-----:| :----: | :----: | --- |
| Foo, Bar, Baz, et al. (2019) | 86.6 | [link]( https://github.com/HaritzPuerto/RCC/) |


### Evaluation

We evaluate models based on the top *k* datasets predicted for each publication, using “precision at k” as the metric: 

```
(# identified datasets @k that are relevant) / (# identified datasets @k)
```

In this case, *k* is 5.

Each prediction must be accompanied by a metric to estimate the uncertainty of the predicted dataset.

Notebooks used to evaluate models must calculate these two metrics for each publication, along with the aggregate rate of correct datasets appearing in the top *k* entries.


---
## Subsequent Stages

It’s important to consider Rich Context in the sense of a workflow: ML models solve specific use cases at different stages of the workflow.
So there are needs for multiple kinds of modeling to be researched and evaluated.
The structure of this leaderboard competition is capable of managing multiple use cases -- with one leaderboard for each identified use case -- as an ongoing, parallelized research effort.

Overall, a three-step process is being used to apply the results of this competition and extend the corpus:

  1. track progress for specific machine learning use cases, based on the current corpus
  2. apply leading ML models to identify datasets in a broader set of research publications
  3. have authors confirm or reject the inferred datasets

The latter step introduces opportunities to use semi-surpervised learning (aka, “human-in-the-loop” approaches) to improve research metadata.
For example, [RePEc](http://repec.org/) communications could provide means for that annotation process and feedback.

---
## Background Info

For more details about Rich Context and other related research, see the white paper ["Rich Context in the Administrative Data Research Facility"](https://coleridgeinitiative.org/assets/docs/ADRF%20White%20Paper_%20Rich%20Context.pdf).

The first iteration of the [Rich Context Competition](https://coleridgeinitiative.org/richcontextcompetition) (during late 2018-early 2019) established the potential to apply the latest machine learning research toward search and discovery of research datasets.
A book now in production -- 
[*Rich Search and Discovery for Research Datasets: Building the next generation of scholarly infrastructure*](https://tinyurl.com/richcontextbook) 
--  summarizes that initial machine learning competition and approaches taken by leading teams, plus key takeaways.

This next iteration of the competition has been based on “state of the art” (SOTA) leaderboards that track ML research, such as [NLP-progress](https://nlpprogress.com/) and [PapersWithCode](https://paperswithcode.com/sota).

Sponsors of this research include 
[Schmidt Futures](https://schmidtfutures.com/), 
the Eric and Wendy Schmidt Fund for Strategic Innovation, 
[Overdeck Family Foundation](https://overdeck.org/), 
and the 
[Alfred P. Sloan Foundation](https://sloan.org/).
We are grateful for support from partners in this research, including
[SAGE Publications](https://sagepub.com/), 
[Digital Science](https://www.digital-science.com/),
and 
[Project Jupyter](https://jupyter.org/).
Development of the corpus has assisted by
[USDA](https://www.usda.gov/)
and
[Bundesbank](https://www.bundesbank.de/en).