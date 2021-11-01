# QMCkl: Quantum Monte Carlo Kernel Library

![Build Status](https://github.com/TREX-CoE/qmckl/workflows/test-build/badge.svg?branch=master)

The domain of quantum chemistry needs a library in which the main
kernels of Quantum Monte Carlo (QMC) methods are implemented. In the
library proposed in this project, we expose the main algorithms in a
simple language and provide a standard API and tests to enable the
development of high-performance QMCkl implementations taking
advantage of modern hardware.

See the [source code](https://github.com/TREX-CoE/qmckl/blob/master/org/qmckl.org)
to read the documentation.


To clone the repository, use:
```
git clone https://github.com/TREX-CoE/qmckl.git
```

# Installation

The simplest way to obtain the source files of QMCkl is to download a source
distribution. This particular repository is for maintainers, who write the kernels
in org-mode files and produce the source code and the documentation from these files.

## For maintainers

```
./autogen.sh
./configure --prefix=$PWD/_install

make
make check
```

## For users

Obtain a source distribution and run

```
./configure 
make
make check
sudo make install
sudo make installcheck
```

## Verificarlo CI

Since Verificarlo should not be a dependency of QMCkl, all Verificarlo
functions are called only when the support is explicitely enabled (and ignored
by the preprocessor otherwise). To enable vfc_ci support, the library should be
configured with the following command :

```
./configure --prefix=$PWD/_install \ --enable-vfc_ci --host=x86_64 \ CC="verificarlo-f" FC="verificarlo-f"
```

where CC and FC are set to verificarlo-f, and support is explicitely enabled
with the --enable-vfc_ci flag. Configuring the library with the "standard"
command will cause all calls to Verificarlo related functions to be ignored,
and the library will be built as usual.


------------------------------

![European flag](https://trex-coe.eu/sites/default/files/inline-images/euflag.jpg)
[TREX: Targeting Real Chemical Accuracy at the Exascale](https://trex-coe.eu) project has received funding from the European Union’s Horizon 2020 - Research and Innovation program - under grant agreement no. 952165. The content of this document does not represent the opinion of the European Union, and the European Union is not responsible for any use that might be made of such content.

