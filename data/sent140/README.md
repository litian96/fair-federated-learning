# Sentiment140 Dataset

## Setup Instructions

Download the dataset [here](https://drive.google.com/file/d/1-nqfQ7FvWdLLUx4cbx8u0xJm9T4gDugj/view?usp=sharing), unzip it and put the `train` and `test` folder under `fair_flearn/data/sent140/data`.

The above data can be generated by the following instruction:


- ```-s``` := 'iid' to sample in an i.i.d. manner, or 'niid' to sample in a non-i.i.d. manner; more information on i.i.d. versus non-i.i.d. is included in the 'Notes' section
- ```--iu``` := number of users, if iid sampling; expressed as a fraction of the total number of users; default is 0.01
- ```--sf``` := fraction of data to sample, written as a decimal; default is 0.1
- ```-k``` := minimum number of samples per user
- ```-t``` := 'user' to partition users into train-test groups, or 'sample' to partition each user's samples into train-test groups
- ```--tf``` := fraction of data in training set, written as a decimal; default is 0.9


Instruction used to generate Sent140 in the paper:

```
./preprocess.sh -s niid --sf 0.4 -k 30 -tf 0.8 -t sample
```


(Make sure to delete the rem\_user\_data, sampled\_data, test, and train subfolders in the data directory before re-running ```preprocess.sh```.)


