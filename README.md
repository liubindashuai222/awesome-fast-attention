# awesome-fast-attention [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)

A curated list of efficient attention modules (last update: Sat, 01 Aug 2020 18:46:29 +0000)

## Table of Contents

* **[Efficient Attention](#efficient-attention)**
* **[Articles](#articles)**

## Efficient Attention

|Paper (citations)|Implementation|Complexity|AutoRegressive|Main Idea|
|:---:|:---:|:---:|:---:|:---:|
|[Generating Wikipedia by Summarizing Long Sequences](https://arxiv.org/abs/1801.10198v1 ) (208)|[memory-compressed-attention](https://github.com/lucidrains/memory-compressed-attention ) ![](https://img.shields.io/github/stars/lucidrains/memory-compressed-attention.svg?style=social )|![formula](https://render.githubusercontent.com/render/math?math=\mathcal{O}({b}\cdot\frac{N}{b}\cdot\frac{N}{{b}\cdot{k}}\cdot{D}))|:x:|<details><summary>EXPAND</summary><p>compresses key and value + blocked attention</p></details>|
|[CCNet: Criss-Cross Attention for Semantic Segmentation](https://arxiv.org/abs/1811.11721v2 ) (149)|[CCNet](https://github.com/speedinghzl/CCNet ) ![](https://img.shields.io/github/stars/speedinghzl/CCNet.svg?style=social )|![formula](https://render.githubusercontent.com/render/math?math=\mathcal{O}({N}\cdot({H}%2b{W})\cdot{D}))|:x:|<details><summary>EXPAND</summary><p>each pixel attends to its row and column simultaneously</p></details>|
|[Efficient Attention: Attention with Linear Complexities](https://arxiv.org/abs/1812.01243v8 ) (2)|[efficient-attention](https://github.com/cmsflash/efficient-attention ) ![](https://img.shields.io/github/stars/cmsflash/efficient-attention.svg?style=social )|![formula](https://render.githubusercontent.com/render/math?math=\mathcal{O}({N}\cdot{D}^2))|:x:|<details><summary>EXPAND</summary><p>Softmax(Q)*(Softmax(K^T)*V)</p></details>|
|[Star-Transformer](https://arxiv.org/abs/1902.09113v2 ) (24)|[fastNLP](https://github.com/fastnlp/fastNLP/blob/master/fastNLP/modules/encoder/star_transformer.py ) ![](https://img.shields.io/github/stars/fastnlp/fastNLP.svg?style=social )|![formula](https://render.githubusercontent.com/render/math?math=\mathcal{O}({N}\cdot{D}))|:x:|<details><summary>EXPAND</summary><p>uses a relay(global) node and attends to/from that node</p></details>|
|[Generating Long Sequences with Sparse Transformers](https://arxiv.org/abs/1904.10509v1 ) (139)|[torch-blocksparse](https://github.com/ptillet/torch-blocksparse ) ![](https://img.shields.io/github/stars/ptillet/torch-blocksparse.svg?style=social )|![formula](https://render.githubusercontent.com/render/math?math=\mathcal{O}({N}\cdot\sqrt{N}\cdot{D}))|:heavy_check_mark:|<details><summary>EXPAND</summary><p>sparse block based attention</p></details>|
|[GCNet: Non-local Networks Meet Squeeze-Excitation Networks and Beyond](https://arxiv.org/abs/1904.11492v1 ) (96)|[GCNet](https://github.com/xvjiarui/GCNet ) ![](https://img.shields.io/github/stars/xvjiarui/GCNet.svg?style=social )|![formula](https://render.githubusercontent.com/render/math?math=\mathcal{O}({N}\cdot{D}^2))|:x:|<details><summary>EXPAND</summary><p>squeeze and excitation with an attention pooling (instead of a GAP)</p></details>|
|[SCRAM: Spatially Coherent Randomized Attention Maps](https://arxiv.org/abs/1905.10308v1 ) (1)|-|![formula](https://render.githubusercontent.com/render/math?math=\mathcal{O}({N}\cdot\log({N})\cdot{D}))|:heavy_check_mark:|<details><summary>EXPAND</summary><p>uses PatchMatch to find close keys</p></details>|
|[Interlaced Sparse Self-Attention for Semantic Segmentation](https://arxiv.org/abs/1907.12273v2 ) (13)|IN_PAPER|![formula](https://render.githubusercontent.com/render/math?math=\mathcal{O}({N}\cdot{D}^2%2b{N}\cdot\sqrt{N}\cdot{D}))|:heavy_check_mark:|<details><summary>EXPAND</summary><p>combination of a short length and then long range(dilated) attention</p></details>|
|[Permutohedral Attention Module for Efficient Non-Local Neural Networks](https://arxiv.org/abs/1907.00641v2 ) (2)|[Permutohedral_attention_module](https://github.com/SamuelJoutard/Permutohedral_attention_module ) ![](https://img.shields.io/github/stars/SamuelJoutard/Permutohedral_attention_module.svg?style=social )|![formula](https://render.githubusercontent.com/render/math?math=\mathcal{O}({N}\cdot{D}^2))|:x:|<details><summary>EXPAND</summary><p>uses permutohedral lattice approximation algorithm to approximate the attention output</p></details>|
|[Large Memory Layers with Product Keys](https://arxiv.org/abs/1907.05242v2 ) (28)|[XLM](https://github.com/facebookresearch/XLM ) ![](https://img.shields.io/github/stars/facebookresearch/XLM.svg?style=social )|![formula](https://render.githubusercontent.com/render/math?math=\mathcal{O}({Q}\cdot({K}%2b{k}^2)\cdot{D}))|:heavy_check_mark:|<details><summary>EXPAND</summary><p>search for nearest neighbor keys</p></details>|
|[Expectation-Maximization Attention Networks for Semantic Segmentation](https://arxiv.org/abs/1907.13426v2 ) (38)|[EMANet](https://github.com/XiaLiPKU/EMANet ) ![](https://img.shields.io/github/stars/XiaLiPKU/EMANet.svg?style=social )|![formula](https://render.githubusercontent.com/render/math?math=\mathcal{O}({N}\cdot{k}\cdot{D}))|:x:|<details><summary>EXPAND</summary><p>applys expectation maximization to cluster keys into k clusters</p></details>|
|[Compressive Transformers for Long-Range Sequence Modelling](https://arxiv.org/abs/1911.05507v1 ) (20)|[compressive-transformer-pytorch](https://github.com/lucidrains/compressive-transformer-pytorch ) ![](https://img.shields.io/github/stars/lucidrains/compressive-transformer-pytorch.svg?style=social )|![formula](https://render.githubusercontent.com/render/math?math=\mathcal{O}({N}^2\cdot{D}))|:heavy_check_mark:|<details><summary>EXPAND</summary><p>compresses distant tokens instead of just stop_grad() ing them, more efficient version of transformerXL</p></details>|
|[BP-Transformer: Modelling Long-Range Context via Binary Partitioning](https://arxiv.org/abs/1911.04070v1 ) (8)|[BPT](https://github.com/yzh119/BPT ) ![](https://img.shields.io/github/stars/yzh119/BPT.svg?style=social )|![formula](https://render.githubusercontent.com/render/math?math=\mathcal{O}({N}\cdot{k}\cdot\log(\frac{N}{k})\cdot{D}))|:heavy_check_mark:|<details><summary>EXPAND</summary><p>attends to distant tokens coarsely and attends to close tokens in a more fine-grained manner</p></details>|
|[Axial Attention in Multidimensional Transformers](https://arxiv.org/abs/1912.12180v1 ) (5)|[axial-attention](https://github.com/lucidrains/axial-attention ) ![](https://img.shields.io/github/stars/lucidrains/axial-attention.svg?style=social )|![formula](https://render.githubusercontent.com/render/math?math=\mathcal{O}({N}\cdot({H}%2b{W})\cdot{D}))|:heavy_check_mark:|<details><summary>EXPAND</summary><p>apply attention on each axis separately</p></details>|
|[Reformer: The Efficient Transformer](https://arxiv.org/abs/2001.04451v2 ) (69)|[trax](https://github.com/google/trax/tree/master/trax/models/reformer ) ![](https://img.shields.io/github/stars/google/trax.svg?style=social )|![formula](https://render.githubusercontent.com/render/math?math=\mathcal{O}({N}\cdot\log({N})\cdot{D}^2))|:heavy_check_mark:|<details><summary>EXPAND</summary><p>uses LSH to find close keys</p></details>|
|[Transformer on a Diet](https://arxiv.org/abs/2002.06170v1 ) (2)|[transformer-on-diet](https://github.com/cgraywang/transformer-on-diet ) ![](https://img.shields.io/github/stars/cgraywang/transformer-on-diet.svg?style=social )|![formula](https://render.githubusercontent.com/render/math?math=\mathcal{O}({N}\cdot{k}\cdot{D}))|:heavy_check_mark:|<details><summary>EXPAND</summary><p>dilated transformer like wavenet</p></details>|
|[Sparse Sinkhorn Attention](https://arxiv.org/abs/2002.11296v1 ) (4)|[sinkhorn-transformer](https://github.com/lucidrains/sinkhorn-transformer ) ![](https://img.shields.io/github/stars/lucidrains/sinkhorn-transformer.svg?style=social )|![formula](https://render.githubusercontent.com/render/math?math=\mathcal{O}(\frac{{N}^2}{n_b}%2b{n_b}^2))|:heavy_check_mark:|<details><summary>EXPAND</summary><p>uses a cost matrix to limit attention between buckets</p></details>|
|[SAC: Accelerating and Structuring Self-Attention via Sparse Adaptive Connection](https://arxiv.org/abs/2003.09833v2 ) (1)|-|![formula](https://render.githubusercontent.com/render/math?math=\mathcal{O}({N}\cdot{k}\cdot{D}))|:heavy_check_mark:|<details><summary>EXPAND</summary><p>learns the q, k connections == dynamically creates a sparse attention matrix</p></details>|
|[Efficient Content-Based Sparse Attention with Routing Transformers](https://arxiv.org/abs/2003.05997v1 ) (11)|[routing-transformer](https://github.com/lucidrains/routing-transformer ) ![](https://img.shields.io/github/stars/lucidrains/routing-transformer.svg?style=social )|![formula](https://render.githubusercontent.com/render/math?math=\mathcal{O}({N}\cdot\sqrt{N}\cdot{D}))|:x:|<details><summary>EXPAND</summary><p>computes attention with same-cluster tokens (computed by online k-means)</p></details>|
|[Longformer: The Long-Document Transformer](https://arxiv.org/abs/2004.05150v1 ) (15)|[longformer](https://github.com/allenai/longformer ) ![](https://img.shields.io/github/stars/allenai/longformer.svg?style=social )|![formula](https://render.githubusercontent.com/render/math?math=\mathcal{O}({N}\cdot({k}%2b{g})\cdot{D}))|:heavy_check_mark:|<details><summary>EXPAND</summary><p>global + blocked attention</p></details>|
|[Neural Architecture Search for Lightweight Non-Local Networks](https://arxiv.org/abs/2004.01961v1 ) (2)|[AutoNL](https://github.com/LiYingwei/AutoNL ) ![](https://img.shields.io/github/stars/LiYingwei/AutoNL.svg?style=social )|![formula](https://render.githubusercontent.com/render/math?math=\mathcal{O}((\frac{H}{h}\cdot\frac{W}{w})\cdot(\frac{D}{k})^2))|:x:|<details><summary>EXPAND</summary><p>computes Q(KV) and also down samples q, k, v both in spatial and channel dimensions</p></details>|
|[ETC: Encoding Long and Structured Data in Transformers](https://arxiv.org/abs/2004.08483v2 ) (2)|-|![formula](https://render.githubusercontent.com/render/math?math=\mathcal{O}(({N}\cdot{g}%2b{g}^2%2b{N}\cdot{k})\cdot{D}))|:heavy_check_mark:|<details><summary>EXPAND</summary><p>combines global attention (star transformer with multiple global tokens) with local attention</p></details>|
|[Multi-scale Transformer Language Models](https://arxiv.org/abs/2005.00581v1 ) (1)|IN_PAPER|![formula](https://render.githubusercontent.com/render/math?math=\mathcal{O}({N}^2\cdot{D}))|:heavy_check_mark:|<details><summary>EXPAND</summary><p>UNet like + retina attetion is something close to BP-Transformer</p></details>|
|[Synthesizer: Rethinking Self-Attention in Transformer Models](https://arxiv.org/abs/2005.00743v1 ) (5)|-|![formula](https://render.githubusercontent.com/render/math?math=\mathcal{O}({N}^2\cdot{D}))|:heavy_check_mark:|<details><summary>EXPAND</summary><p>does not compute pairwise interactions</p></details>|
|[Jukebox: A Generative Model for Music](https://arxiv.org/abs/2005.00341v1 ) (9)|[jukebox](https://github.com/openai/jukebox ) ![](https://img.shields.io/github/stars/openai/jukebox.svg?style=social )|![formula](https://render.githubusercontent.com/render/math?math=\mathcal{O}({N}\cdot\sqrt{N}\cdot{D}))|:heavy_check_mark:|<details><summary>EXPAND</summary><p>better attention patterns from Sparse Transformer</p></details>|
|[GMAT: Global Memory Augmentation for Transformers](https://arxiv.org/abs/2006.03274v1 ) (0)|[gmat](https://github.com/ag1988/gmat ) ![](https://img.shields.io/github/stars/ag1988/gmat.svg?style=social )|![formula](https://render.githubusercontent.com/render/math?math=\mathcal{O}({m}\cdot({N}%2b{m})\cdot{D}))|:x:|<details><summary>EXPAND</summary><p>adds global tokens</p></details>|
|[Masked Language Modeling for Proteins via Linearly Scalable Long-Context Transformers](https://arxiv.org/abs/2006.03555v1 ) (0)|[google-research](https://github.com/google-research/google-research/tree/master/performer/fast_self_attention ) ![](https://img.shields.io/github/stars/google-research/google-research.svg?style=social )|![formula](https://render.githubusercontent.com/render/math?math=\mathcal{O}({N}\cdot{D}^2\cdot\log({D})))|:heavy_check_mark:|<details><summary>EXPAND</summary><p>calculate an unbiased stochastic approximation of the attention matrix</p></details>|
|[Hand-crafted Attention is All You Need? A Study of Attention on Self-supervised Audio Transformer](https://arxiv.org/abs/2006.05174v1 ) (0)|-|![formula](https://render.githubusercontent.com/render/math?math=\mathcal{O}({N}^2\cdot{D}))|:heavy_check_mark:|<details><summary>EXPAND</summary><p>does not compute pairwise interactions and uses fixed mask patters</p></details>|
|[Transformers are RNNs: Fast Autoregressive Transformers with Linear Attention](https://arxiv.org/abs/2006.16236v2 ) (1)|[fast-transformers](https://github.com/idiap/fast-transformers ) ![](https://img.shields.io/github/stars/idiap/fast-transformers.svg?style=social )|![formula](https://render.githubusercontent.com/render/math?math=\mathcal{O}({N}\cdot{D}^2))|:heavy_check_mark:|<details><summary>EXPAND</summary><p>uses phi(q)(phi(k)v) and also improves the sequential sampling step</p></details>|
|[Linformer: Self-Attention with Linear Complexity](https://arxiv.org/abs/2006.04768v3 ) (3)|[linformer-pytorch](https://github.com/tatp22/linformer-pytorch ) ![](https://img.shields.io/github/stars/tatp22/linformer-pytorch.svg?style=social )|![formula](https://render.githubusercontent.com/render/math?math=\mathcal{O}({N}\cdot{k}\cdot{D}))|:x:|<details><summary>EXPAND</summary><p>project key and value from n*d to k*d</p></details>|
|[Real-time Semantic Segmentation with Fast Attention](https://arxiv.org/abs/2007.03815v2 ) (0)|-|![formula](https://render.githubusercontent.com/render/math?math=\mathcal{O}({N}\cdot{D}^2))|:x:|<details><summary>EXPAND</summary><p>l2_norm(q)*(l2_norm(k)*v)</p></details>|
|[Fast Transformers with Clustered Attention](https://arxiv.org/abs/2007.04825v1 ) (0)|[fast-transformers](https://github.com/idiap/fast-transformers ) ![](https://img.shields.io/github/stars/idiap/fast-transformers.svg?style=social )|![formula](https://render.githubusercontent.com/render/math?math=\mathcal{O}({N}\cdot{k}\cdot{D}))|:x:|<details><summary>EXPAND</summary><p>groups queries together with LSH</p></details>|

## Articles

* [A Survey of Long-Term Context in Transformers](https://www.pragmatic.ml/a-survey-of-methods-for-incorporating-long-term-context/)

