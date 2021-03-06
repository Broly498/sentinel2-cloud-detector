[![Package version](https://badge.fury.io/py/s2cloudless.svg)](https://pypi.org/project/s2cloudless/)
[![Supported Python versions](https://img.shields.io/pypi/pyversions/s2cloudless.svg?style=flat-square)](https://pypi.org/project/s2cloudless/)
[![Build status](https://travis-ci.org/sentinel-hub/sentinel2-cloud-detector.svg?branch=master)](https://travis-ci.org/sentinel-hub/sentinel2-cloud-detector)
[![Overall downloads](https://pepy.tech/badge/s2cloudless)](https://pepy.tech/project/s2cloudless)
[![Last month downloads](https://pepy.tech/badge/s2cloudless/month)](https://pepy.tech/project/s2cloudless)
[![Code coverage](https://codecov.io/gh/sentinel-hub/sentinel2-cloud-detector/branch/master/graph/badge.svg)](https://codecov.io/gh/sentinel-hub/sentinel2-cloud-detector)

# Sentinel Hub's cloud detector for Sentinel-2 imagery

**NOTE: s2cloudless masks are now available as a precomputed layer within Sentinel Hub. Check the [announcement blog post](https://medium.com/sentinel-hub/cloud-masks-at-your-service-6e5b2cb2ce8a) and [technical documentation](https://docs.sentinel-hub.com/api/latest/#/API/data_access?id=cloud-masks-and-cloud-probabilities).**

The **s2cloudless** Python package provides automated cloud detection in
Sentinel-2 imagery. The classification is based on a *single-scene pixel-based cloud detector*
developed by Sentinel Hub's research team and is described in more details
[in this blog](https://medium.com/sentinel-hub/improving-cloud-detection-with-machine-learning-c09dc5d7cf13).

## Installation

The package requires a Python version >= 3.6. The package is available on
the PyPI package manager and can be installed with

```
$ pip install s2cloudless
```

To install the package manually, clone the repository and
```
$ pip install .
```

One of `s2cloudless` dependencies is `lightgbm` package. If having problems during installation, please
check the [LightGBM installation guide](https://lightgbm.readthedocs.io/en/latest/Installation-Guide.html).

Before installing `s2cloudless` on **Windows**, it is recommended to install package `shapely` from
[Unofficial Windows wheels repository](https://www.lfd.uci.edu/~gohlke/pythonlibs/)

## Input: Sentinel-2 scenes

The inputs to the cloud detector are Sentinel-2 images. In particular, the cloud detector requires the following 10
Sentinel-2 band reflectances: B01, B02, B04, B05, B08, B8A, B09, B10, B11, B12, which are obtained from raw
reflectance value in the following way: `B_i/10000`.

You don't need to worry about any of this, if you're doing classification of scenes obtained using [Sentinel Hub
Process API](https://docs.sentinel-hub.com/api/latest/api/process/). The API is supported in Python with 
[sentinelhub-py](https://github.com/sentinel-hub/sentinelhub-py) package.

## Examples

Jupyter notebook on how to use the cloud detector to produce cloud mask or cloud probability map
can be found in the [examples folder](https://github.com/sentinel-hub/sentinel2-cloud-detector/tree/master/examples).

## License

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">
<img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a>
<br />
This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>.
