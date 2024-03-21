standalone BLaDE program and pyALF library
==

There are three major steps. 

Most steps are taken according to MSLD workshop. https://github.com/BrooksResearchGroup-UM/MSLD-Workshop/tree/main/0Install_Tools/Linux


I. Set up environment
-

- create a new folder
- `git clone https://github.com/molcube-public/afes-blade-1.git`
- `git clone https://github.com/molcube-public/afes-pyalf-1.git`
- `conda create -n bld-w-alf-test1 python=3.9` # create a new conda environment, here we use name `bld-w-alf-test1`
- `conda activate bld-w-alf-test1`
- `conda install -c conda-forge mamba`
- `conda install -c "nvidia/label/cuda-11.6.2" cuda` # For newer cards (e.g. L4 tensor card), use newer CUDA version (e.g. 12.1.0).
- `mamba install -y -c conda-forge gcc==11.4 gxx==11.4 gfortran==11.4 make cmake binutils fftw openmpi  mpi4py sysroot_linux-64==2.17 readline==8.2 rdkit openbabel pandas   biopython  mdtraj  jsonpickle` # run this line twice if error is encountered. Use gcc==12.2 if CUDA version is 12.1.x.

II. Compile standalone BLaDE program
-

- `cd afes-blade-1`
- comment out 'source module' in Compile.sh
- `bash Compiled.sh` 

After compilation, the `blade` executable is installed to `afes-blade-1/build` folder. 

Remember to set `OMP_NUM_THREADS` (as 1) and `CUDA_VISIBLE_DEVICES` environment variables.

III. Install pyALF to conda environment 
-

- `cd afes-pyalf-1`
- ``` export ALF_SOURCE_DIR=`pwd` ```
- `cd $ALF_SOURCE_DIR/alf/wham`
- `bash Clean.sh`
- `cmake ./`
- `make wham`
- `cd $ALF_SOURCE_DIR/alf/dca`
- `bash Clean.sh`
- `cmake ./`
- `make all`
- `cd $ALF_SOURCE_DIR`
- `pip install -e .`
- `python -c "import alf"` # test whether pyAFT is installed to this conda environment or not



