---
title: Getting Started
weight: 1
next: /docs/guide
prev: /docs
---

## Quick Start 

Two repositories were created from this project, one contains the structural optimization algorithms and the other has everything related to the development of deep learning methods.


- {{< icon "github" >}}&nbsp;[kssgarcia/DeepLearningOpt](https://github.com/kssgarcia/DeepLearningOpt)
- {{< icon "github" >}}&nbsp;[kssgarcia/OptTopolgy](https://github.com/kssgarcia/OptTopolgy)


## Topology optimization repo

- BESO method [BESO.py](https://github.com/kssgarcia/OptTopolgy/blob/main/BESO.py)
- ESO stress based method  [ESO_stress_based.py](https://github.com/kssgarcia/OptTopolgy/blob/main/ESO_stress_based.py)
- ESO stiff based method [ESO_stiff_based.py](https://github.com/kssgarcia/OptTopolgy/blob/main/ESO_stiff_based.py)
- SIMP method [SIMP.py](https://github.com/kssgarcia/OptTopolgy/blob/main/SIMP.py)``

### Instructions

{{% steps %}}

### Clone repository

```sh
git clone https://github.com/kssgarcia/OptTopolgy.git
```

### Download the required packages running the following command

```sh
conda env create -f environment.yml
```

### Install solidspy

```sh
pip install solidspy
```

{{% /steps %}}

## Optimization with deep learning repo

- [SIMP_multi.py](https://github.com/kssgarcia/DeepLearningOpt/blob/main/simp/SIMP_multi.py) code used for generate training dataset.
- [CNN.py](https://github.com/kssgarcia/DeepLearningOpt/blob/main/neural_network/CNN.py) code used for training neural network.
- [load_model.py](https://github.com/kssgarcia/DeepLearningOpt/blob/main/neural_network/CNN2.py) code used for load neural network.
- [SIMP_multi_dist.py](https://github.com/kssgarcia/DeepLearningOpt/blob/main/neural_network/SIMP_multi_dist.py) code used for generate dataset with a distributed load.


### Instructions

{{% steps %}}

### Clone repository

```sh
git clone https://github.com/kssgarcia/DeepLearningOpt.git
```

### Download the required packages running the following command

```sh
conda env create -f environment.yml
```

### Install solidspy

```sh
pip install solidspy
```

{{% /steps %}}


## Next

Explore the following sections to start adding more contents:

{{< cards >}}
  {{< card link="../guide/organize-files" title="Organize Files" icon="document-duplicate" >}}
  {{< card link="../guide/configuration" title="Configuration" icon="adjustments" >}}
  {{< card link="../guide/markdown" title="Markdown" icon="markdown" >}}
{{< /cards >}}