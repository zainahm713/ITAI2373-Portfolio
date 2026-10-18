# NewsBot Intelligence System — Results

## Dataset and evaluation

The BBC labeled training data contained 1,490 articles; removal of exact duplicate article texts left 1,440 usable articles across business, entertainment, politics, sport, and tech. A stratified 75/25 split produced 1,080 training and 360 test articles. TF-IDF was fitted on training data alone.

The cross-validation-selected model was **LinearSVC** with 96.39% test accuracy and **0.9608 macro F1**. Logistic Regression reached 96.11% accuracy (0.9588 macro F1) and Multinomial Naive Bayes reached 95.83% accuracy (0.9554 macro F1). A Bag-of-Words and Naive Bayes baseline reached 96.39% accuracy (0.9618 macro F1).

The most frequent off-diagonal confusion was three technology test articles classified as entertainment. This overlap illustrates the ambiguity of technology reporting about digital media and consumer platforms, although individual erroneous articles would need manual review to establish their specific causes.

## Linguistic analysis and sentiment

The slower POS, dependency, and NER components used a stratified sample of 175 articles, 35 from each category. In this sample, sports had the greatest proper-noun share (11.2%), and technology had the smallest share (4.7%). Named-entity extraction recorded people, organizations, geographic locations, dates, and money expressions; co-mentions indicate shared article coverage, not verified relationships.

VADER labeled 46.6% of politics coverage as negative, the highest share among the five categories. Sport and entertainment had greater positive-label shares (78.9% and 80.2% respectively). These signals measure language patterns in a historical corpus, not public opinion.

## Practical implications and limits

A newsroom could use the model to prioritize article routing, and monitoring teams could filter relevant topic categories before manual review. Important limitations include the historical domain of BBC stories, small sampled linguistic analysis, vocabulary-specific classifiers, lexical polarity errors, and misleading interpretations of entity co-occurrence. The test scores reflect one split and do not establish future real-world performance.

## Original data and references

BBC News Classification (Kaggle): https://www.kaggle.com/competitions/learn-ai-bbc/data

spaCy: https://spacy.io/ · scikit-learn: https://scikit-learn.org/ · NLTK: https://www.nltk.org/
