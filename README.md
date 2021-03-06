[![PyPI version](https://badge.fury.io/py/tusc.svg)](https://badge.fury.io/py/tusc)
[![Documentation Status](https://readthedocs.org/projects/tusc/badge/?version=latest)](https://tusc.readthedocs.io/en/latest/?badge=latest)
[![Build Status](https://app.travis-ci.com/lucasmccabe/tusc.svg?branch=main)](https://app.travis-ci.com/lucasmccabe/tusc)
[![Downloads](https://pepy.tech/badge/tusc)](https://pepy.tech/project/tusc)
[![MIT license](https://img.shields.io/badge/License-MIT-blue.svg)](https://lbesson.mit-license.org/)

# TUSC 🐘: Toolbox for Understanding Some things in Combinatorics

> WIP Python library providing tools for combinatorial maths (partially-ordered sets, graph polynomials, etc.).

![elephant_header](https://raw.githubusercontent.com/lucasmccabe/tusc/main/assets/elephant_header.png)

## Table of Contents
* [Table of Contents](#table-of-contents)
* [Installation](#installation)
* [Example Usage](#example-usage)
* [Repo Organization](#repo-organization)
* [Requirements](#requirements)
* [Contact](#contact)
* [License](#license)


## Setup

### With pip:

```bash
pip install tusc
```

###### *(FYSA: this repository is tested on Python 3.8 only)*


## Example Usage

Retrieving the Tutte polynomial for the five-vertex cycle graph (C<sub>5</sub>):

```python
import tusc
import networkx as nx

C5 = nx.cycle_graph(5)
tutte_C5 = tusc.graph.polynomial.Tutte(C5)
tutte_C5.polynomial
```

```bash
'x^4 + x^3 + x^2 + x + y'
```

Evaluating the polynomial to find the number of acyclic orientations of C<sub>5</sub>:

```python
tutte_C5.evaluate(2, 0)
```

```bash
30
```

## Repo Organization

This repo is organized as follows:

```bash
tusc
├── tusc
│   ├── general  # general utilities, e.g. OEIS lookup
│   │   ├── utils
│   ├── graph  # graph problems, retrieving graph polynomials
│   │   ├── distance
│   │   ├── enumeration  # enumerative problems, e.g. counting spanning trees
│   │   ├── manipulation
│   │   ├── matching
│   │   ├── polynomial  # retrieving graph polynomials (e.g. Tutte, chromatic)
│   ├── posets    # constructing and analyzing partially-ordered sets
│   │   ├── utils
│   │   ├── example_posets
│   │   ├── poset
├── tests
│   ├── general
├── assets
├── docs
```


## Requirements
This project was created with:

- `requests==2.24.0`
- `numpy==1.19.5`
- `sympy==1.6.2`
- `networkx==2.5`


## Contact
- Lucas Hurley McCabe ([email](mailto:lucasmccabe@gwu.edu))

## License
[MIT](https://choosealicense.com/licenses/mit/)
