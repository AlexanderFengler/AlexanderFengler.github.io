---
layout: post
title: Make a python package pip installable
categories: [python, pip, package, mac]
comments: true
excerpt: A very reduced mini-tutorial on the steps necessary to make a python package pip installable
---

### Basic setup

At best start from a fresh [`conda`](https://docs.conda.io/en/latest/) / [`mamba`](https://mamba.readthedocs.io/en/latest/) environment and make sure the `setuptools` package (usually is) as well as the `twine` package (usually is not) are available. If not then simply type,

```python
pip install setuptools
pip install twine
```

### Make a distribution

Two steps to making a source distribution (the file which you will upload to [PyPI](https://pypi.org/) later).
First, check if your `setup.py` file provides all necessary meta-data to make [PyPI](https://pypi.org/) happy. Run this check with,

```bash
python setup.py check
```

If no errors are raise, then proceed with creating the source distribution,

```bash
python setup sdist
```

This will create (if not available) a `dist` folder and a `tar.gz` file with a file name roughly like `packagename-version.tar.gz`.

### Test upload
We can now test-run an upload to [PyPI](https://pypi.org/) via the [TestPyPI](https://testpypi.org/) server (Test Python Package Index).  
To upload our just-created source distribution, we will type the following in the terminal.

```bash
twine upload --repository-url hhtps://test.pypi.org/legacy/ dist/packagename-version.tar.gz
```

### Test install

To test-run an install from [TestPyPI](https://pypi.org/), we type,

```bash
pip install --index-url https://test.pypi.org/simple/ packagename --user
```

One may run into issues with dependencies, in which case the extra argument `--extra-index-url https://pypi.org/simple` can (it did in my case) help. 
The full command in this case:

```bash
pip install --index-url https://test.pypi.org/simple/ --extra-index-url https://pypi.org/simple/ packagename --user
```

### The real thing

If the test install suceeded (consider trying it in fresh conda / mamba environments across a few python versions), we can now confidently upload our distribution to 
to [PyPI](https://pypi.org/). Simply type,

```bash
twine upload dist/packagename-version.tar.gz
```

You will be asked for your username and password. Once the upload finished, you can try installing your package via the standard `pip install` command like so,

```bash
pip install packagename
```

#### Some Credits

This tutorial is a slightly adapted, mostly much reduced version of [this excellent blog post](https://betterscientificsoftware.github.io/python-for-hpc/tutorials/python-pypi-packaging/).
