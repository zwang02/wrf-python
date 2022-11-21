wrf-python-adapted
==============

Codes adapted from NCAR/wrf-python repository. 

https://github.com/NCAR/wrf-python 

In the adapted version, I have implemented the surfaced-based and most-unstable CAPE calculation into wrf module. The functions can be called in a similar way as wrf.cape_2d, but with wrf.sbcape_2d and wrf.mucape_2d respectively. The input and output follow the same convention as described in cape_2d documentation. For details, see below: 

https://wrf-python.readthedocs.io/en/latest/user_api/generated/wrf.cape_2d.html?highlight=cape




Installation
----------------------------

See detailed instructions from wrf-python documentation: 
https://wrf-python.readthedocs.io/en/latest/installation.html

On HPC Linux environments, the following lines works with python version 3.5.2 

    cd ../fortran/build_help

    gfortran -o sizes -fopenmp omp_sizes.f90

    python sub_sizes.py

    cd ..

    gfortran -E ompgen.F90 -fopenmp -cpp -o omp.f90

    f2py *.f90 -m _wrffortran -h wrffortran.pyf --overwrite-signature

    cd ..

    python setup.py clean --all

    python setup.py config_fc --f90flags="-mtune=generic -fopenmp" build_ext --libraries="gomp" build

    pip install .


Documentation
----------------------------------

http://wrf-python.rtfd.org


Citation
------------------

If you use this software, please cite the original software package as described at the [WRF-Python - Citation](
https://wrf-python.readthedocs.io/en/latest/citation.html) page. You may cite my adapted version as 

Wang, Z. (2022). wrf-python-adapted (Version 0.1) [Software]. Chicago, Illinois: University of Chicago. 




