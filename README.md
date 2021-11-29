# OSagnosticDESops
Procedure to install SageMath on WSL2

## Problem 0, Individual Assignment 3
### step 1: Installing prerequisites,  
check perl: $ which perl

install all the prerequisite via the command: 

$ sudo apt-get install  bc binutils bzip2 ca-certificates cliquer cmake curl ecl eclib-tools fflas-ffpack flintqs g++ g++ gcc gcc gfan gfortran glpk-utils gmp-ecm lcalc libatomic-ops-dev libboost-dev libbraiding-dev libbrial-dev libbrial-groebner-dev libbz2-dev libcdd-dev libcdd-tools libcliquer-dev libcurl4-openssl-dev libec-dev libecm-dev libffi-dev libflint-arb-dev libflint-dev libfreetype6-dev libgc-dev libgd-dev libgf2x-dev libgiac-dev libgivaro-dev libglpk-dev libgmp-dev libgsl-dev libhomfly-dev libiml-dev liblfunction-dev liblrcalc-dev liblzma-dev libm4rie-dev libmpc-dev libmpfi-dev libmpfr-dev libncurses5-dev libntl-dev libopenblas-dev libpari-dev libpcre3-dev libplanarity-dev libppl-dev libpython3-dev libreadline-dev librw-dev libsqlite3-dev libssl-dev libsuitesparse-dev libsymmetrica2-dev libz-dev libzmq3-dev libzn-poly-dev m4 make nauty openssl palp pari-doc pari-elldata pari-galdata pari-galpol pari-gp2c pari-seadata patch perl pkg-config planarity ppl-dev python3 python3 python3-distutils r-base-dev r-cran-lattice sqlite3 sympow tachyon tar tox xcas xz-utils yasm

### step 2: Install SageMath
Download the latest version of SageMath for Linux on https://www.sagemath.org/download-source.html

Extract the archive: $ tar xvf sage-9.4.tar.gz (here I use the 9.4 version)

Change into that directory: $ cd sage-9.4

Run the configure script by $ ./configure using the default setting

Start the build process via multiprocessing $ MAKE='make -j12' make (would take a very long time if try single process)

### Step3: Write a shell script to make it easier to use SageMath with Jupyter notebook under ~ directory.
#!/bin/bash

\# Switch to desired windows directory

cd /mnt/c/Users/zhuli/'OneDrive - Uppsala universitet'/'Introduction to Data Science'

\# Start the Jupyter notebook

sage  --notebook jupyter

\# Alternatively you can run JupyterLab - delete the line above, and uncomment the line below

#SAGE_ROOT/sage --notebook jupyterlab
