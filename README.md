# Description

**Status:** Forked by Dereck de Mezquita; this version was made functional and modified for efficiency. Will be integrated into a personal project for later use in text generation by artificial intelligence.

# How to run GPT-2

Use a anaconda environment with Python, the following versions are necessary including CUDA-9 if you want to use a GPU for faster processing. I used the following machine for running the model with 774M parameters:

```{bash}
(base) dereck@ubuntu-server:~/projects/gpt-2$ uname -r
5.4.0-42-generic

sudo lshw
```

For detailed hardware specifications on the machine I used to run this please see the file [sys-info.txt](./sys-info.txt)

## Custom commands

```
python3 src/interactive_conditional_samples.py --top_k 40 --model_name=774M
```

```
python3 -c 'import tensorflow as tf; print(tf.__version__)'
```


## Watch GPU usage

```
watch -d -n 0.5 nvidia-smi
```

## Debugging

If you're having issues with the CUDA connection to the GPU; which will happen when not using CUDA v9. CUDA v11 works but you have to modify the path:

```
echo $LD_LIBRARY_PATH
export LD_LIBRARY_PATH=/usr/local/cuda/lib64
```

# Example outputs

Here are some example outputs I've been able to get gpt-2 to output. I will be refining the models for specific purposes such as: music generation (lyrics), poetry, and cover letter writing (job applications).

For some more example outputs please see: [results.txt](./results.txt).

## Prompts and responses

**Model prompt >>> Bitcoin price in us dollars in the year 2022**

**SAMPLE 1**

, but the current value is $3,000,000. As you can imagine, $20,000,000 would be a lot of money to a man who already knows how to navigate the world. But, as you'll learn in one of my next posts, we're already getting closer than we expected.

But before we go on to discuss how bitcoin could replace fiat currency, let me explain what a world filled with bitcoin could mean for the world. The world is about to get a lot more interesting If nothing else, a bitcoin-driven world means more money. If you look at the current value of bitcoin in my favorite metric, the total market capitalization, the total bitcoin value, which includes other cryptocurrencies and other digital assets, exceeds the GDP of China by at least $6 trillion. Now, the GDP of China is roughly $4 trillion. If bitcoin-driven inflation doesn't cause the Chinese economy to collapse within the next few years, how's this for a world-changing event? As a result of bitcoin's rapid adoption by individuals and businesses in China, it has already led to a dramatic change in the way the China economy works. For the first time in Chinese history, banks have been replaced by bitcoin. The total capitalization of Chinese bitcoin exchanges now surpass their national GDP. 

If you look more closely, you'll see that the total market capitalization of China-based Bitcoin exchanges is greater than that of major Chinese multinational conglomerates, meaning that the Chinese economy is now powered by a single new technology (Bitcoin).

With the economy of China at a tipping point, the possibilities for a world based on blockchain technology far outweigh those associated with fiat currencies.

If the financial industry of China was powered by blockchain, a new financial industry could be born in that country.

If the Chinese government would become more proactive about embracing blockchain, the market value of Bitcoin would increase by at least double.

The blockchain has the potential to reshape entire industries, as well as make new markets possible.

And if a world that's already on the verge of being turned upside down by the crypto-anarchy becomes a place that is transformed by blockchain technology, then I th
ink we're going to be in for some amazing change.

When I first met Satoshi Nakamoto, the man believed to be the creator of bitcoin, I thought he was just a guy who came up with this crazy idea. I

------------
------------

<!-- **Status:** Archive (code is provided as-is, no updates expected) -->

# gpt-2

Code and models from the paper ["Language Models are Unsupervised Multitask Learners"](https://d4mucfpksywv.cloudfront.net/better-language-models/language-models.pdf).

You can read about GPT-2 and its staged release in our [original blog post](https://blog.openai.com/better-language-models/), [6 month follow-up post](https://openai.com/blog/gpt-2-6-month-follow-up/), and [final post](https://www.openai.com/blog/gpt-2-1-5b-release/).

We have also [released a dataset](https://github.com/openai/gpt-2-output-dataset) for researchers to study their behaviors.

<sup>*</sup> *Note that our original parameter counts were wrong due to an error (in our previous blog posts and paper).  Thus you may have seen small referred to as 117M and medium referred to as 345M.*

## Usage

This repository is meant to be a starting point for researchers and engineers to experiment with GPT-2.

For basic information, see our [model card](./model_card.md).

### Some caveats

- GPT-2 models' robustness and worst case behaviors are not well-understood.  As with any machine-learned model, carefully evaluate GPT-2 for your use case, especially if used without fine-tuning or in safety-critical applications where reliability is important.
- The dataset our GPT-2 models were trained on contains many texts with [biases](https://twitter.com/TomerUllman/status/1101485289720242177) and factual inaccuracies, and thus GPT-2 models are likely to be biased and inaccurate as well.
- To avoid having samples mistaken as human-written, we recommend clearly labeling samples as synthetic before wide dissemination.  Our models are often incoherent or inaccurate in subtle ways, which takes more than a quick read for a human to notice.

### Work with us

Please [let us know](mailto:languagequestions@openai.com) if you’re doing interesting research with or working on applications of GPT-2!  We’re especially interested in hearing from and potentially working with those who are studying
- Potential malicious use cases and defenses against them (e.g. the detectability of synthetic text)
- The extent of problematic content (e.g. bias) being baked into the models and effective mitigations

## Development

See [DEVELOPERS.md](./DEVELOPERS.md)

## Contributors

See [CONTRIBUTORS.md](./CONTRIBUTORS.md)

## Citation

Please use the following bibtex entry:
```
@article{radford2019language,
  title={Language Models are Unsupervised Multitask Learners},
  author={Radford, Alec and Wu, Jeff and Child, Rewon and Luan, David and Amodei, Dario and Sutskever, Ilya},
  year={2019}
}
```

## Future work

We may release code for evaluating the models on various benchmarks.

We are still considering release of the larger models.

## License

[Modified MIT](./LICENSE)
