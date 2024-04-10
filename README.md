## Model: OPT-350M
The experiment utilized the OPT-350M model, which is part of the Open Pre-trained Transformer (OPT) suite of open-sourced decoder-only transformer language models developed by Meta AI, with 350 million parameters. Like the other OPT models, OPT-350M follows a standard transformer decoder architecture, with 24 layers, 16 attention heads, and a hidden dimension size of 1024. The model uses ReLU activations and was trained using an AdamW optimizer with a linear warmup and decay learning rate schedule, on a large corpus of English text data.

## Dataset Employed:

The dataset utilized is the raw WikiText-2 dataset, an unaltered version of the WikiText language modeling dataset. Unlike preprocessed variants, this dataset maintains original tokens from Wikipedia articles, including case, punctuation, and numbers, without substituting out-of-vocabulary words with a special <unk> token. This raw format is particularly beneficial for character-level language modeling tasks, preserving comprehensive character-level information from the source text. Compared to the preprocessed Penn Treebank dataset, raw WikiText-2 is more than twice as large and boasts a significantly expanded vocabulary, rendering it ideal for models capable of exploiting long-term dependencies in text.

## Run Demo

By running the following script:
```bash
bash run_demo.sh
```
You will finetune a [facebook/opt-350m](https://huggingface.co/facebook/opt-350m) model on this [dataset](https://huggingface.co/datasets/hugginglearners/netflix-shows), which contains more than 8000 comments on Netflix shows.

The script can be modified if you want to try another set of hyperparameters or change to another OPT model with different size.

The demo code is adapted from this [blog](https://medium.com/geekculture/fine-tune-eleutherai-gpt-neo-to-generate-netflix-movie-descriptions-in-only-47-lines-of-code-40c9b4c32475) and  the [HuggingFace Language Modelling examples](https://github.com/huggingface/transformers/tree/main/examples/pytorch/language-modeling).



## Run Benchmark

You can run benchmark for OPT model by running the following script:
```bash
bash run_benchmark.sh
```
The script will test performance (throughput & peak memory usage) for each combination of hyperparameters. You can also play with this script to configure your set of hyperparameters for testing.
