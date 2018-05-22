# End-To-End Memory Network on SQuAD-QA-Systems


## Usage
### 0. Requirements
- Python
- tensorflow
- numpy
- nltk
- six
- json

### 1. Data Preprocessing
Create the following folders in your code directory:

 - Folder 1: /data/squad
 - Folder 2: /download/squad

Download the dataset:

 - SQuAD dataset: https://rajpurkar.github.io/SQuAD-explorer/ (Folder 2)


Run the following in the 'code' folder to preprocess the data:

```
python preproc1.py
```

In this script, the following preprocessing steps will be implemented:
- The SQuAD dataset is tokenized by the tokenizer tool from nltk, put the context, question, answer and answer span into one file. Context are divided into individual sentences one per line. Lines in these files are aligned. The answer span is transformed into the index of sentence in the context paragraph. 
- For SQuAD dataset, the train dataset is splitted into two parts: a 95% slice for training, and the rest 5% for validation purposes. The dev dataset will be used as the test set in this project.

### 2. Run tasks

Implementation of [End-To-End Memory Networks](http://arxiv.org/abs/1503.08895) with sklearn-like interface using Tensorflow. Tasks are from the [bAbl](http://arxiv.org/abs/1502.05698) dataset and the [SQuAD](https://rajpurkar.github.io/SQuAD-explorer/).

## Get Started

```
git clone git@github.com:domluna/memn2n.git

mkdir ./memn2n/data/
cd ./memn2n/data/
wget http://www.thespermwhale.com/jaseweston/babi/tasks_1-20_v1-2.tar.gz
tar xzvf ./tasks_1-20_v1-2.tar.gz

cd ../
```

## Examples

Running a [single bAbI task](./single.py)
```
python single.py
```
or run a specific task "i"
```
python single.py -task_id i
```

Running a [single SQuad task](./single.py)
```
python single.py -task_id 21
```

Running a [joint model on all bAbI tasks](./joint.py)

```
python joint.py
```
