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

## Experiment and Result 
In the experiment, OPT-350M was trained in colossal AI with Gemini plugin showing the OPT model converged slowly and the loss is decreasing in every epoch as shown as the plot below:

![image](https://github.com/tayyy/Assignment6_ColossalAI_OPT/assets/10602507/103fddaf-276e-40dd-babb-271045b1f8bb)

Benchmark of different plugin has been also conducted by training OPT-125M. 
The benchmark results show that using the torch_ddp plugin yielded a throughput of 2.59 batch/sec and a maximum memory usage per GPU of 8.38 GB. When switching to the torch_ddp_fp16 plugin, the throughput significantly increased to 5.71 batch/sec, while the maximum memory usage per GPU decreased to 7.11 GB. Adopting the low_level_zero plugin further improved the throughput to 6.57 batch/sec, with a reduction in maximum memory usage per GPU to 4.90 GB. Lastly, utilizing the gemini plugin resulted in a throughput of 6.29 batch/sec, with the lowest maximum memory usage per GPU among all plugins, at 3.51 GB.

![image](https://github.com/tayyy/Assignment6_ColossalAI_OPT/assets/10602507/50a688a9-0daa-43dd-b7d6-1ed394ca2ee2)

![image](https://github.com/tayyy/Assignment6_ColossalAI_OPT/assets/10602507/17eabcd8-1ec6-4305-81f6-6f647030a709)

## Reference

Research Paper: https://arxiv.org/pdf/2110.14883.pdf

Colossal Ai Website: https://colossalai.org/

Github Repo: https://github.com/hpcaitech/ColossalAI#colossalchat


