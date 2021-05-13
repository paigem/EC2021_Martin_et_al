# EC2021_Martin_et_al


## Frequency-domain analysis of large datasets
Climate model datasets are typically stored as global snapshots, i.e. chunked in time rather than space. For many workflows, this chunking works well (e.g. computations across spatial domains at every point in time). However, this storage format can create serious challenges for processing long time series at each point in space, as is the case for frequency-domain analysis. For large datasets with frequent (e.g. daily) output, it is not feasible to process each spatial point as a single time series, even with the help of distributed computing such as Dask.

In this notebook, we show an example workflow for performing frequency-domain analysis on large datasets in the Pangeo Cloud environment. Specifically, we compute the terms in the surface spectral temperature variance budget of a 0.1˚ horizontal resolution global ocean model with daily output. This analysis involves the computation of cross spectra to yield processed data in the frequency (rather than the time) domain. To compute a frequency-domain Fourier transform, we need information from the entire time series and thus cannot work with data that is chunked in time. Hence, this workflow first requires a complete rechunking of the data (using the Rechunker package) from global snapshots to spatially chunked time series. We then compute the Fourier transform on this rechunked data to obtain output in frequency space. Although computationally intensive, we are able to carry out this computation using distributed computing via Dask Gateway and adaptive scaling of the Dask cluster. 



[![badge](https://img.shields.io/static/v1.svg?logo=Jupyter&label=Pangeo+Binder&message=GCE+us-central1&color=blue)](https://binder.pangeo.io/v2/gh/pangeo-data/pangeo-binder-template/master?urlpath=lab)

[![badge](https://img.shields.io/static/v1.svg?logo=Jupyter&label=Pangeo+Binder&message=AWS+us-west-2&color=orange)](https://aws-uswest2-binder.pangeo.io/v2/gh/pangeo-data/pangeo-binder-template/master?urlpath=lab)


#### info on customized badges:

options: https://shields.io
link creator: https://shields.io/endpoint

[![badge](https://img.shields.io/static/v1.svg?label=Project&message=Jupyter&logo=Jupyter)](https://jupyter.org)
