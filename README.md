# [Natural-Language-Processing-with-Disaster-Tweets](https://www.kaggle.com/competitions/nlp-getting-started/overview)
Kaggle Competition: Predict which Tweets are about real disasters and which ones are not

## Final Rank and Result

[Leadboard is here](https://www.kaggle.com/competitions/nlp-getting-started/leaderboard)

|Model|Best Accuracy|Rank|
|:---|:---|:---|
|BERT|84.13%|39/860 Top 4%|
|RoBERTa|83.97%|53/860 Top 6%|

# Set-up
## Operation System:
![macOS Badge](https://img.shields.io/badge/-macOS-white?style=flat-square&logo=macOS&logoColor=000000) ![Linux Badge](https://img.shields.io/badge/-Linux-white?style=flat-square&logo=Linux&logoColor=FCC624) ![Ubuntu Badge](https://img.shields.io/badge/-Ubuntu-white?style=flat-square&logo=Ubuntu&logoColor=E95420)

## Language and Additional Packages:
![Python](http://img.shields.io/badge/-3.8.13-eee?style=flat&logo=Python&logoColor=3776AB&label=Python) ![PyTorch](http://img.shields.io/badge/-1.12.0-eee?style=flat&logo=pytorch&logoColor=EE4C2C&label=PyTorch) ![Scikit-learn](http://img.shields.io/badge/-1.1.1-eee?style=flat&logo=scikit-learn&logoColor=e26d00&label=Scikit-Learn) ![NumPy](http://img.shields.io/badge/-1.22.3-eee?style=flat&logo=NumPy&logoColor=013243&label=NumPy) ![tqdm](http://img.shields.io/badge/-4.64.0-eee?style=flat&logo=tqdm&logoColor=FFC107&label=tqdm) ![pandas](http://img.shields.io/badge/-1.4.3-eee?style=flat&logo=pandas&logoColor=150458&label=pandas) ![SciPy](http://img.shields.io/badge/-1.8.1-eee?style=flat&logo=SciPy&logoColor=8CAAE6&label=SciPy) ![colorama](http://img.shields.io/badge/-0.4.5-eee?style=flat&label=colorama) ![cudatoolkit](http://img.shields.io/badge/-11.6.0-eee?style=flat&label=cudatoolkit) ![datasets](http://img.shields.io/badge/-2.4.0-eee?style=flat&label=datasets) ![matplotlib](http://img.shields.io/badge/-3.4.2-eee?style=flat&label=matplotlib) ![nltk](http://img.shields.io/badge/-3.7-eee?style=flat&label=nltk) ![tokenizers](http://img.shields.io/badge/-0.11.4-eee?style=flat&label=tokenizers) ![transformers](http://img.shields.io/badge/-4.18.0-eee?style=flat&label=transformers) ![seaborn](http://img.shields.io/badge/-0.11.2-eee?style=flat&label=seaborn)

## GPU:

![Nvidia](http://img.shields.io/badge/-RTX_A6000_48GB-eee?style=flat&logo=NVIDIA&logoColor=76B900&label=NVIDIA)

## Environment
```console
username@localhost:~$ conda install pytorch torchvision torchaudio cudatoolkit=11.6 -c pytorch -c conda-forge
username@localhost:~$ pip install transformers
username@localhost:~$ pip install datasets
username@localhost:~$ pip install -U scikit-learn
username@localhost:~$ pip install numpy
username@localhost:~$ pip install pandas
username@localhost:~$ pip install tqdm
username@localhost:~$ pip install colorama
username@localhost:~$ pip install seaborn
username@localhost:~$ pip install nltk
```

# How to run

## Tuning Parameters

The first choice is tuning parameters, you can directly run the run.sh file. It will take a long time, about 100hrs. 
The best parameters for different model are provided below. 

```console
username@localhost:~$ bash /src/run.sh
```
    
## Training

Meanwhile, you can just run the python file, it will be executed once, and the result will be printed. You can try different parameters before you execute the python file.

```console
username@localhost:~$ python3 /src/train.py --model_name [$model_name] --threshold [$threshold] --batchsize [$batchsize] --dropout [$dropout] --layer[$layer] 
```

## Reproduce
Run the following command， which can achieve the best result of BERT model.
```
python src/train.py \
	--model_name bert_base \
	--threshold 0.6 \
	--batchsize 8 \
	--dropout 0.3 \
	--layer 3
```

Run the following command， which can achieve the best result of RoBERTa model.
```
python src/train.py \
	--model_name roberta_base \
	--threshold 0.6 \
	--batchsize 16 \
	--dropout 0.3 \
	--layer 1
```
Note: The results of each run may deviate slightly



