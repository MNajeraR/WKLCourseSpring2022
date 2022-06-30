

Instalación de TreeCorr
(macOS Monterrey - version 12.3.1, 2.4 GHz 8-Core Intel Core i9, 32 GB, MacPorts & Anaconda3, gcc11)

conda update conda
envName=TCEnv
envPath="$HOME/$envName"
mkdir $envPath && conda create python=$pythonV --prefix "$envPath"
conda install -c conda-forge treecorr -p $envPath
conda install jupyter-notebook -p $envPath

( LA ULTIMA INSTRUCCION MUESTRA:
Collecting package metadata (current_repodata.json): done
Solving environment: failed with initial frozen solve. Retrying with flexible solve.
Collecting package metadata (repodata.json): done
Solving environment: failed with initial frozen solve. Retrying with flexible solve.

PackagesNotFoundError: The following packages are not available from current channels:

  - jupyter-notebook

Current channels:

  - https://repo.anaconda.com/pkgs/main/osx-64
  - https://repo.anaconda.com/pkgs/main/noarch
  - https://repo.anaconda.com/pkgs/r/osx-64
  - https://repo.anaconda.com/pkgs/r/noarch

To search for alternate channels that may provide the conda package you're
looking for, navigate to

    https://anaconda.org

and use the search bar at the top of the page.
)

(HAY ERROR EN EL DOCUMENTO:
conda activate $envPath$

NO DEBE IR EL ÚLTIMO "$"
)

conda activate $envPath
git clone https://github.com/rmjarvis/TreeCorr.git
cd TreeCorr/tests
time ./run_all_tests 2>&1 | tee run_all_tests.log
(
real	28m45.904s
user	350m47.690s
sys	16m48.660s
)

conda deactivate

(conda env remove -p $envPath)
