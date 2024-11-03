---
 configure.py
```python
#! /usr/bin/env python
# -*- coding: utf-8 -*-

class Config:
  prefix      = "bin"          # Installation path

  compiler    = "INTEL"        # Compiler

  cflags      = "-O2 -std=c++11" # compiling flags for C++ programs
  fflags      = "-O2"          # compiling flags for Fortran programs
  ldflags     = ""             # linking flags for Fortran programs
  ompflag     = "-qopenmp"     # linker/compiler flag for openmp

  cc          = "icx"          # new C compiler
  cxx         = "icpx"         # new C++ compiler

  mpi_define  = "-D_MPI"       # should be -D_MPI for mpi code and empty for serial code.
  pcc         = "mpicc"        # C compiler
  pcxx        = "mpicxx"       # C++ compiler
  pfc         = "mpiifort"       # Fortran compiler

  blasname    = "MKL"             # BLAS   library
  blaslib     = "-qmkl=parallel" # BLAS   library
  lapacklib   = ""             # LAPACK library
  fftwlib     = "-L/opt/fftw3/lib/ -lfftw3_omp -lfftw3"     # FFTW   library
  gsl         = "-lgslcblas -lgsl"  # GSL    library

  f2pylib     = "--f90flags='-qopenmp ' --opt='-fast'" # adding extra libraries for f2py
  f2pyflag    = "--opt='-O2' " # adding extra options to f2py

  arflags     = "rc"           # ar flags

  make        = "make"
  def __init__(self, version):
    self.version = version
  def __getattr__(self,key):
    return None
```
