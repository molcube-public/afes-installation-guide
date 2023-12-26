OpenMM-AToM
==

For AToM, we need to install 

 -  OpenMM
 -  CUDA Toolkit (if the automatically installed CUDA Toolkit is incompatible with existing device)
 -  AMBER Tools
 -  R
 -  and others

Depending on the version of AToM, some details may differ. We want to install packages step by step into a conda environment to reduce waiting time.

AToM v4.0.0 
- 

 - `conda create --name atom-v400-1` [to create a new conda environment. `atom-v400-1` can be any name you like]
 - `conda activate atom-v400-1`
 - `conda install -c conda-forge openmmforcefields`
 - `conda install -c conda-forge ambertools=23.3`
 - `conda install -c conda-forge cudatoolkit=11.7.0` [`11.7.0` may need to be adjusted according to your GPU device compatibility]
 - `conda install -c conda-forge openmm-atmmetaforce-plugin`
 - `conda install -c conda-forge configobj setproctitle r-base`
 - `git clone https://github.com/molcube-public/afes-openmm-atom-1/tree/v4.0.0rc-r1; cd v4.0.0rc-r1`
 - `python setup.py install`
 - `Rscript -e 'install.packages("UWHAM", repos = "http://cran.us.r-project.org")' `

AToM v8.1
-

- `conda create --name atom-v810-dev`
- `conda activate atom-v810-dev`
- `conda install -c conda-forge openmmforcefields`
- `conda install -c conda-forge openmm=8.1.0`
- `conda install -c conda-forge cudatoolkit=11.7.0` 
- `conda install -c conda-forge ambertools=23.3`
- `conda install -c conda-forge configobj setproctitle r-base`
- ... to be filled 
