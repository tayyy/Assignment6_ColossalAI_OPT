## Model: OPT-350M
The experiment utilized the OPT-350M model, which is part of the Open Pre-trained Transformer (OPT) suite of open-sourced decoder-only transformer language models developed by Meta AI, with 350 million parameters. Like the other OPT models, OPT-350M follows a standard transformer decoder architecture, with 24 layers, 16 attention heads, and a hidden dimension size of 1024. The model uses ReLU activations and was trained using an AdamW optimizer with a linear warmup and decay learning rate schedule, on a large corpus of English text data.

## Dataset Employed: WikiText-2

The dataset utilized is the raw WikiText-2 dataset, an unaltered version of the WikiText language modeling dataset. Unlike preprocessed variants, this dataset maintains original tokens from Wikipedia articles, including case, punctuation, and numbers, without substituting out-of-vocabulary words with a special <unk> token. This raw format is particularly beneficial for character-level language modeling tasks, preserving comprehensive character-level information from the source text. Compared to the preprocessed Penn Treebank dataset, raw WikiText-2 is more than twice as large and boasts a significantly expanded vocabulary, rendering it ideal for models capable of exploiting long-term dependencies in text.

## Parallel setting (Model Training): Gemini 

Gemini, developed by Colossal-AI, is a memory management system designed to efficiently utilize both CPU and GPU memory during model training, akin to the symbiotic relationship of two stars. It dynamically distributes tensors across CPU and GPU storage spaces, enabling model training to overcome GPU memory limitations. Gemini's memory management comprises two components: MemStatsCollector (MSC) and StatefulTensorMgr (STM).
	
The training process of deep learning networks is iterative, and Gemini capitalizes on this characteristic by dividing iterations into two stages: warmup and non-warmup. During warmup, which encompasses the initial one or several iterative steps, MSC gathers relevant information. Subsequently, in the non-warmup stage, STM utilizes the information collected by MSC to relocate tensors, minimizing the volume of data movement between CPU and GPU.

## Instruction to run code:
1. Open ColossalAI_OPT.ipynb in Google Colab and execute it using GPU hardware acceleration.
2. This script automates the process by cloning the repository from GitHub, installing all essential dependencies and packages necessary for model training, and conducting performance benchmarking with various ColossalAI plugins.

## ExperimentResult 
