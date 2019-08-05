# Presentation for AFRL at the Wright Brothers Institute 8/6/2019

## Installing from source

Requirements: You must have CMake>=2.8.12 and a C++11 compatible compiler (GCC>=4.8) to build.

You must also have RISE enabled along with its various extensions in order to use the slide version of the notebook.  This can be done by 
the following,

```
conda install jupyter
conda install -c conda-forge rise
conda install -c conda-forge jupyter_nbextensions_configurator
```
Then clone the repo,
```
  git clone https://github.com/infophysics/AFRL.git
```
Then install both TDA and Automata,
```
  cd AFRL/TDA
  python setup.py install
  cd ../Automata
  python setup.py install
```



### Support

* Bugs: Please report bugs to the [issue tracker on Github](https://github.com/infophysics/AFRL/issues) such that we can keep track of them and eventually fix them.  Please explain how to reproduce the issue (including code) and which system you are running on.
* Help: Help can be provided also via the issue tracker by tagging your issue with 'question'
* Contributing:  Please fork this repository then make a pull request.  In this pull request, explain the details of your change and include tests.

## Technical implementation

This package is a [pybind11](https://pybind11.readthedocs.io/en/stable/intro.html) wrapper of several persistent homology algorithm implementations as well as general purpose plotting and a computation of the [Persistent Homology Dimension](https://people.math.osu.edu/schweinhart.2/MeasuringShapeWithTopology.pdf)

* Implementation also based on [this](http://www.benjack.io/2018/02/02/python-cpp-revisited.html)

See AUTHORS.md for information on the developers.

## Citation

When you use `TDA`, please say so in your slides or publications (for publications, see Zenodo link above).  You can mention this in addition to how you cite TDA.  This is important for us being able to get funding to support this project.
