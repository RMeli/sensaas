## sensaas


[![badgepython](https://forthebadge.com/images/badges/made-with-python.svg)](https://www.python.org/downloads/release/python-370/)  [![forthebadge](https://forthebadge.com/images/badges/built-with-science.svg)](https://chemoinfo.ipmc.cnrs.fr/)

**SENSAAS** is a shape-based alignment program to superimpose molecules as described in the publication [SenSaaS: Shape-based Alignment by Registration of Colored Point-based Surfaces](https://onlinelibrary.wiley.com/doi/full/10.1002/minf.202000081).

**Documentation**: Full documentation is available at [https://sensaas.readthedocs.io/en/latest/.](https://sensaas.readthedocs.io/en/latest/.)

**Website**: A web demo is available at https://chemoinfo.ipmc.cnrs.fr/SENSAAS/index.html

**Tutorial**: This video on YouTube XXXX provides a tutorial


## Requirements

SENSAAS relies on the open-source library Open3D. The current release of SENSAAS uses **Open3D version 0.12.0 along with Python3.7**. Visit the following URL for downloading the appropriate package: [https://anaconda.org/open3d-admin/open3d/files](https://anaconda.org/open3d-admin/open3d/files) or for using Open3D Python packages distributed via PyPI and Conda (more information at [http://www.open3d.org/docs/release/getting_started.html](http://www.open3d.org/docs/release/getting_started.html)). For example, for windows-64, you can download '*win-64/open3d-0.12.0-py37_0.tar.bz2*'


## Virtual environment for python with conda

Install conda or Miniconda from [https://conda.io/miniconda.html](https://conda.io/miniconda.html)  
Then, complete the installation:

	conda update conda
	conda create -n sensaas
	conda activate sensaas
	conda install python=3.7 numpy
 
 After donwloading the appropriate version of Open3D:
  
 	conda install open3d-0.12.0-py37_0.tar.bz2

(Option) Additional packages for using scripts in the directory utils or visualization with PyMol:

  	conda install perl
  	install -c conda-forge rdkit
  	conda install -c schrodinger -c conda-forge pymol-bundle
  
Retrieve and unzip SENSAAS repository

## Linux

Install:

1. Python3.7 and numpy
2. Open3D version 0.12.0 (more information at [http://www.open3d.org/docs/release/getting_started.html](http://www.open3d.org/docs/release/getting_started.html))

(Option) Install additional packages for using scripts in the directory utils or visualization with PyMOL:

4. perl (usually it is already installed)
5. RDKit (Open-Source Cheminformatics Software; more information at [https://rdkit.org](https://rdkit.org) or [https://github.com/rdkit/rdkit](https://github.com/rdkit/rdkit))
6. PyMOL (a molecular viewer; more information at [https://pymolwiki.org](https://pymolwiki.org))
  
Retrieve and unzip SENSAAS repository

## MacOS

	Not tested

## Information on the third-party program nsc
nsc is used to efficiently generate point cloud of molecules. It is written in C and was developed by Frank Eisenhaber who kindly accepted its use in SENSAAS:
   *  references :
   *  1. F.Eisenhaber, P.Lijnzaad, P.Argos, M.Scharf
   *     "The Double Cubic Lattice Method: Efficient Approaches to
   *     Numerical Integration of Surface Area and Volume and to Dot
   *     Surface Contouring of Molecular Assemblies"
   *     Journal of Computational Chemistry (1995) v.16, N3, pp.273-284
   *  2. F.Eisenhaber, P.Argos
   *     "Improved Strategy in Analytic Surface Calculation for Molecular
   *     Systems: Handling of Singularities and Computational Efficiency"
   *     Journal of Computational Chemistry (1993) v.14, N11, pp.1272-1280

Executables nsc (for Linux) and ncs-win (for windows) are included in the repository. In case it does not work on your system, you may have to compile it using the source file nsc.c in directory src:

Linux ('nsc' is used to set the variable nscexe in python script sensaas.py):
	cc src/nsc.c -lm
rename a.out as nsc:
	cp a.out nsc
	
Windows ('nsc-win.exe' is used to set the variable nscexe in python script sensaas.py):
The current executable nsc-win.exe was compiled by using [http://www.codeblocks.org](http://www.codeblocks.org)
rename the executable as nsc-win.exe

Alternative to the use of nsc to generate point cloud:
We recommend the use of nsc program but it exists an alternative by using PyMOL. Please contact us.

## Run Sensaas
To align a Source molecule on a Target molecule, run:
	
	sensaas.py sdf molecule-target.sdf sdf molecule-source.sdf slog optim
Example:
	se

## License
Code released under [the 3-Clause BSD License](https://opensource.org/licenses/BSD-3-Clause)

## Copyright
Copyright (c) 2018-2021, CNRS, Inserm, Université Côte d'Azur, Dominique Douguet and Frédéric Payan, All rights reserved.

## Reference
[Douguet D. and Payan F., SenSaaS: Shape-based Alignment by Registration of Colored Point-based Surfaces,
   '*Molecular Informatics*', **2020**, 8, 2000081.](https://onlinelibrary.wiley.com/doi/full/10.1002/minf.202000081). doi: 10.1002/minf.202000081
   
