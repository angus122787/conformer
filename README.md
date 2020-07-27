<img src="./conformer-conv-module.png" width="600px"></img>

## Conformer

Implementation of the convolutional module from the <a href="https://arxiv.org/abs/2005.08100">Conformer</a> paper, for improving the local inductive bias in Transformers.

## Install

```bash
$ pip install conformer
```

## Usage

```python
import torch
from conformer.conformer import ConformerConvModule

layer = ConformerConvModule(
    dim = 512,
    expansion_factor = 2,       # what multiple of the dimension to expand for the depthwise convolution
    kernel_size = 32,           # kernel size, 17 - 32 was said to be optimal
    dropout = 0.                # dropout at the very end
)

x = torch.randn(1, 1024, 512)
layer(x) # (1, 1024, 512)
```

## Citations

```bibtex
@misc{gulati2020conformer,
    title={Conformer: Convolution-augmented Transformer for Speech Recognition},
    author={Anmol Gulati and James Qin and Chung-Cheng Chiu and Niki Parmar and Yu Zhang and Jiahui Yu and Wei Han and Shibo Wang and Zhengdong Zhang and Yonghui Wu and Ruoming Pang},
    year={2020},
    eprint={2005.08100},
    archivePrefix={arXiv},
    primaryClass={eess.AS}
}
```
