---
#author: "Stéfan van der Walt"
#date: "February 2019"
colorlinks: true
fontsize: 12pt
bibliography: paper.bib
---

## Scientific Python: A Mature Computational Ecosystem for Microscopy

Stéfan van der Walt^1\*^

^1.^ Berkeley Institute for Data Science, University of California, Berkeley USA.\
^\*^ Corresponding author: stefanv@berkeley.edu

Over the past decade, the Scientific Python ecosystem has matured into
a fully fledged data analysis environment.  Python, as a language for
*science*, draws strength from being a *general purpose programming
language*: its ecosystem extends far beyond that of a scientific-only
language.  For example, Python has high-quality tools that can be used
to ingest data from the internet or to control acquisition hardware,
process the resulting data, store it in a database, and present it to
collaborators via a web application or through interactive notebooks.

But Python has also seen rapid adoption in scientific computing
itself, and there now exists a variety of libraries for handling
N-dimensional array computation, processing table data, calculating
scientific functions, plotting results, and disseminating results as
programs accompanied by rich, interactive documents.  Python is also
prominent in data science [@stackoverflow-python] and *the* key player
in machine learning [@octoverse-ml-blog]---specifically, deep
learning, which has seen an explosion of applications in microscopy.

Assessing the needs of a typical data analyst in microscopy, we
identify key challenges along with the libraries that address them:

* **Numerical data processing**: Regardless of whether experiments
  deal with images or other input formats, they all have associated
  numerical data—often best represented as arrays of numbers.
  Examples are 1-dimensional arrays for time-series, and
  3-dimensional arrays for single-band volumetric data.  The `NumPy`
  library [@van2011numpy] provides N-dimensional arrays, with methods
  for performing associated calculations.  `NumPy` is under active
  development, both by its community, and a team funded by the Moore &
  Sloan Foundations at the Berkeley Institute for Data Science. <!-- 
  An
  example of a recent addition to the library, under guidance of the
  [project roadmap](https://www.numpy.org/neps/roadmap.html), is the
  `__array_function__` protocol, that allows external libraries to
  pass objects that behave like NumPy arrays through standard NumPy
  pipelines unscathed.  -->Other prominent packages in this space include
  `xarray` [@hoyer2017xarray], which provides labeled axes for
  N-dimensional arrays, and [zarr](https://zarr.readthedocs.io), which
  implements chunked, compressed, N-dimensional arrays.

* **Image processing**: Almost all forms of microscopy involve image
  processing, such as segmentation, denoising, morphological analysis,
  region analysis, feature detection, and registration.
  `scikit-image` is a library with roots in two-dimensional image
  processing that has since been developed to include many
  N-dimensional capabilities.  The term `scikit` (SciPy toolkit)
  indicates a package that is developed separately from the `SciPy`
  library, but according to similarly rigorous standards, often using
  the same processes, documentation formats, and so forth.

* **Visualization**: Matplotlib has long been the de-facto standard in
  Python for producing high quality, 2D publication figures.  More
  recently, a number of web-enabled packages have emerged, such as
  Bokeh for interactive 2D display,
  and [ipyvolume](https://github.com/maartenbreddels/ipyvolume)
  and
  [ITK Jupyter Widgets](https://github.com/InsightSoftwareConsortium/itk-jupyter-widgets) for
  interactive 3D visualization in Jupyter
  notebooks.  [`spimagine`](https://github.com/maweigert/spimagine)
  provides accelerated 3D visualization of time lapsed volumetric data,
  and Mayavi [@ramachandran2011mayavi] delivers general 3D
  visualization through VTK.  This space is still actively developing.

* **Parallel processing / batch pipelines**: Acquisition, especially
  on modern devices, produce large volumes of data, which often cannot
  be processed on a single laptop.  The `dask` library provides
  mechanisms for developing code on a laptop, that can subsequently be
  executed on multiple cores, or multiple machines (nodes).  It
  provides integration with cluster batch submissions systems such as
  SLURM, and can launch workers in the cloud through, e.g.,
  Kubernetes. Task progress can be monitored via a browser dashboard.

Using these libraries, several additional specialist libraries have
been developed for solving problems pertinent to microscopy.  These
include CellProfiler [@Carpenter2006] for quantifying cell phenotypes,
skan [@NunezIglesias2018ANP] for the analysis of fine structure
skeletons through graphs, Trackpy [@allanTrackpy] for particle
tracking in any number of dimensions, PyCroscopy [@pycroscopy] for
analysis of nanoscale materials imaging data, and Ilastik
[@sommer2011ilastik] for interactive image classification and
segmentation.

A large amount of microscopy is currently done in the Java ecosystem.
It is encouraging to note that one of the explicit goals of ImageJ2 [@rueden2017imagej2] is
better inter-operability with libraries such as OpenCV
[@opencv_library] and scikit-image [@scikit-image].

We are also watching the building of online communities and
infrastructure, such as Pangeo [@Abernathey2017], with interest: these
are excellent platforms through which to evaluate the suitability of
various libraries for domain-specific, large data analysis
tasks---knowledge that can then be fed back into tool development.

In this talk, we examine the scientific Python ecosystem, explore
various of its key components, and argue that it is a mature and
powerful toolset with application across a wide array of
microscopy-related tasks.

References:
\

\setlength{\itemsep}{0em}
\setlength{\parskip}{0em}
