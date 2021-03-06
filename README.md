# Creating webapps with Binder that have Seaborn, VPython, and other useful dependencies

[![Binder](https://mybinder.org/badge.svg)](https://mybinder.org/v2/gh/fomightez/appmode/master)

This repository demonstrates how to create webapps with Binder. This is similar to how Shiny apps work in R.
Using the `appmode` Jupyter plugin, a notebook's code will be run, and then only the markdown cells and
code outputs will be shown.

You can check out the `appmode` repository here: https://github.com/oschuett/appmode

----

### Post-Fork Differences
- I added seaborn and other useful dependencies to the `environment.yml` file after forking this from [here](https://github.com/binder-examples/appmode).  
(To determine which ones I could place in `environment.yml` to have conda handle install, I opened a Binder from appmode Binder-example and then launched terminal then searched, such as `conda search seaborn` to see if available in conda-forge, based on [here](https://conda.io/docs/user-guide/tasks/manage-pkgs.html#searching-for-packages). Nothing returned for those, like `vpython`, that are not available.)
- Updated `launch binder` button to point to my fork. Also, for now I set it to open by default into the Jupyter environment Dashboard in this vanilla fork. This is because I plan to mainly use the Jupyter environment spawned from here, using the awesome MyBinder system, for developing or viewing previously made notebooks that I am not ready to share publically.  
To change things to open in appmode, later I can just change to `?urlpath=apps%2Findex.ipynb` (or similar depending on notebook name) at the end of the link. Or if I need it to spawn into the notebook form, use at the end`?urlpath=notebooks%2Findex.ipynb`, as described [here](https://github.com/oschuett/appmode#description). 
- OUTDATED, see https://github.com/binder-examples/appmode --->: Placed dependencies conda cannot handle in EXECUTABLE `postBuild` file. (Note that because the `postBuild` approach for some reason wasn't working for my fork of qgrid-notebooks (I strongly suspect that issue was because you cannot use the browser interface to edit the postBuild file, which I have since stopped doing), I later found I could actually add the items that conda doesn't handle but pip does to the `environment.yml` using the solution at http://repo2docker.readthedocs.io/en/latest/samples.html#conda-mixed-requirements , see [here](https://github.com/fomightez/qgrid-notebooks/blob/master/environment.yml) for an example where I replace the `pip install` lines in `postBuild` with lines in `environment.yml`.

