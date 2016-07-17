# SymEngine Python Wrappers

Python wrappers to the C++ library [SymEngine](https://github.com/symengine/symengine),
a fast C++ symbolic manipulation library.

[![Build Status](https://travis-ci.org/symengine/symengine.py.svg)](https://travis-ci.org/symengine/symengine.py) [![Build status](https://ci.appveyor.com/api/projects/status/97hn32jomyyn2aft/branch/master?svg=true)](https://ci.appveyor.com/project/isuruf/symengine-py-l1jmr/branch/master)

## Installation

Install prerequisites.

    CMake        >= 2.8.7
    Python2      >= 2.6      or Python3 >= 3.3
    Cython       >= 0.19.1   and != 0.24
    SymEngine    >= 0.1.0
    SciKit-Build >= 0.1.0

For SymEngine, only a specific commit (see symengine_version.txt) is supported.
Latest git master branch may not work as there may be breaking changes in SymEngine.
Cython v0.24 is not supported yet.

Python wrappers can be installed by,

    python setup.py install

Additional options to setup.py are

    python setup.py install build
        --symengine-dir=/path/to/symengine/install/dir          # Path to SymEngine install directory or build directory
        --compiler=mingw32|msvc|cygwin                          # Select the compiler for Windows
        --generator=cmake-generator                             # CMake Generator
        --build-type=Release|Debug                              # Set build-type for multi-configuration generators like MSVC
        --define="var1=value1;var2=value2"                      # Give options to CMake

Standard options to setup.py like `--user`, `--prefix` can be used to configure install location

Use SymEngine from Python as follows:

    >>> from symengine import var
    >>> var("x y z")
    (x, y, z)
    >>> e = (x+y+z)**2
    >>> e.expand()
    2*x*y + 2*x*z + 2*y*z + x**2 + y**2 + z**2

You can read Python tests in `symengine/tests` to see what features are
implemented.
