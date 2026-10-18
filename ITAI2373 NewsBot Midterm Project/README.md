# NewsBot Intelligence System — ITAI 2373

**Student:** Zain Ahmed  
**Status:** Individual project  
**Repository:** https://github.com/zainahm713/ITAI2373-Portfolio

## Project overview

NewsBot processes BBC news articles and combines eight required NLP project components: application context, text preprocessing, TF-IDF features, POS patterns, dependency parsing, sentiment and emotion-word cues, multi-class classification, and named entity recognition. The notebook also examines chi-square term associations, an n-gram Bag-of-Words baseline, and entity co-mentions.

## Experiment and selected results

The corpus includes **1,440 distinct usable articles** in five labeled categories. The training set contains 1,080 articles and the test set 360. Three models were evaluated on the same split. Training-only cross-validation selected **LinearSVC**, with **96.39% accuracy** and **0.9608 macro F1** on the held-out set. The Bag-of-Words Naive Bayes baseline reached **96.39% accuracy**. SpaCy POS/dependency/NER analysis covered a stratified sample of 175 articles. The PDF report describes the measured findings and limitations.

## Project files

- `NewsBot_Intelligence_System.ipynb` — executed Google Colab notebook and integrated classifier.
- `report/MT_Report_Group_Individual_Zain_Ahmed_ITAI2373.pdf` — complete technical report.
- `results/` — plots, metrics, classified sentiment output, POS and entity summaries, and trained classifier artifact.
- `reflection/NewsBot_Reflection_Individual.pdf` — two-page reflection.
- `data/SOURCE.md` — original dataset attribution and licensing note.
- `requirements.txt` — Python dependency specifications.

## Reproducibility

The Colab notebook requires a labeled BBC News training CSV from the original dataset link. Running its cells sequentially installs the required libraries and `en_core_web_sm`, trains three models, computes the linguistic analyses, and produces exported figures and the report. The notebook uses `random_state=42`, a stratified 75/25 split, and a 7,000-feature TF-IDF vocabulary of unigrams and bigrams; all vocabulary fitting is restricted to training data.

## Model limitations

The BBC corpus is historical; observed category accuracy does not guarantee performance on current news. Full spaCy parsing is sampled to reduce processing overhead. The VADER model is lexicon-based, simplistic emotion-word counts are not validated emotion labels, and named-entity co-mentions are not validated relationships. The illustrative input texts in the notebook are integration smoke tests, not independent real-world evaluation.

## References

- BBC News Classification (Kaggle): https://www.kaggle.com/competitions/learn-ai-bbc/data
- spaCy: https://spacy.io/
- scikit-learn: https://scikit-learn.org/
- NLTK: https://www.nltk.org/

**Development provenance:** Implementation and drafting received AI assistance. Experimental figures and reported scores are sourced from the executed notebook outputs.
