# DeepLSH: Deep Locality-Sensitive Hash Learning for Fast and Efficient Near-Duplicate Crash Report Detection

## Motivation
Automatic crash bucketing is a critical step in the software development process to efficiently analyze and triage bug reports. It generally consists in grouping similar reports through clustering techniques. However, with real-time streaming bug collection, systems are needed to quickly answer the question: **What are the most similar bugs to a new one?** that is, efficiently find its "near-duplicates". Many stack trace based-similarity metrics have been proposed to compute the similarity between stack-traces (the only information availaible for debugging and reproducing crash reports). These measures are generally embedded in clustering algorithms but this comes with several drawbacks: First, it needs numerous similarity calculations when assigning a new stack trace to a cluster. Second, clusters are not stable over time and should be recalculated frequently without loosing links to actual bug tickets that have been previously created. It can also be difficult to set the various parameters that need to be tuned. On the other hand, searching for exact nearest neighbors is computationally demanding and generally infeasible.   

## Overview
In this work, we aim at detecting for a crash report its candidate near-duplicates (i.e., similar crashes that are likely to be induced by the same software bug) in a large database of historical crashes and given any similarity measure dedicated to compare between stack traces. To this end, we propose **DeepLSH** a deep Siamese hash coding neural network that learns to approximate the locality-sensitive property to provide binary hash codes aiming to locate the most similar stack traces into hash buckets as shown in the Figure . **DeepLSH** have been conducted on a large stack trace dataset and performed on state-of-the-art similarity measures proposed to tackle the crash deduplication problem:
- Jaccard coefficient [[Ref](https://en.wikipedia.org/wiki/Jaccard_index)]
- Cosine similarity [[Ref](https://en.wikipedia.org/wiki/Sine_and_cosine)]
- Lucene TF-IDF [[Ref](https://lucene.apache.org/core/7_6_0/core/org/apache/lucene/search/similarities/TFIDFSimilarity.html)]
- Edit distance [[Ref](https://en.wikipedia.org/wiki/Edit_distance)]
- Brodie et al. [[Paper](https://www.cs.drexel.edu/~spiros/teaching/CS576/papers/Brodie_ICAC05.pdf)]
- PDM-Rebucket [[Paper](https://www.researchgate.net/publication/254041628_ReBucket_A_method_for_clustering_duplicate_crash_reports_based_on_call_stack_similarity)]
- DURFEX [[Paper](https://users.encs.concordia.ca/~abdelw/papers/QRS17-Durfex.pdf)]
- Lerch and Mezini [[Paper](https://files.inria.fr/sachaproject/htdocs//lerch2013.pdf)]
- Moroo et al. [[Paper](http://ksiresearch.org/seke/seke17paper/seke17paper_135.pdf)]
- TraceSIM [[Paper](https://arxiv.org/pdf/2009.12590.pdf)]

## Contributions and Main Findings

## How DeepLSH works? 

![test](code/Images/Images-paper/Test-Phase.png)

## How to use this code?
1. Clone this repository using: ```git clone https://github.com/anony2023/DeepLSH.git ```
2. Install the required python packages: ```pip install -r ./code/requirements.txt ```
3. Run the notebooks in code/notebooks/measure:
    * measure-DeepLSH.ipynb : the end-to-end procedure to train/test and validate DeepLSH
    * measure-Baseline.ipynb: the end-to-end procedure to train/test and validate the Baseline
    * measure-Runtime.ipynb : comparison between the required runtime for DeepLSH vs. brute force

