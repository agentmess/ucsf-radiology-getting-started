---
subtitle: "Python Tool Resources"
tags: [python]
---

## Python Resources 

The servers have several versions of python, with the default version being python 2.7. The best practice when coding in python is to set up a virtual environment with the libraries you will be using. To do this, follow these steps:

---

### Set up a virtual environment

- Use the following command to initialize the latest conda in the servers:
  - ``/netopt/rhel7/versions/python/Anaconda3-edge/bin/conda init bash tcsh``
  - Close the current terminal and open a new one for the changes to take place

- Use the following commands to set up the directory where the python environments and packages will be stored:
  - `mkdir /path/to/save/dir`
  - `conda config --append envs_dirs /path/to/save/dir/envs`
  - `conda config --append pkgs_dirs /path/to/save/dir/pkgs`

---

{{< notice note >}}

- Your home directory has limited space so it is recommended to pick a directory in a bigger filesystem. Please ask your colleagues or supervisor about which specific directories are allocated for your group.
{{< /notice >}}

---

- Use the following command to create a new [Anaconda] (includes numpy, scipy, pandas, matplotlib, jupyter, etc)] python environment named `environmentname` (this can be any word without spaces):

  - #### Python 2
    - `conda create -n environmentname python=2.7 anaconda -y`

  - #### Python 3
    - `conda create -n environmentname python=3.X  anaconda -y`
      - The python 3 versions available are `3.5`, `3.6`, `3.7`, and `3.8`

- To create an empty python environment, so you can add your own packages, just remove `anaconda` from the above command and install your own packages with:
  - `conda install packagename`

---

#### Using the new environment

- To activate the virtual environment use the following command:
  - `conda activate environmentname`
  - The name of the virtual environment will be displayed to the left of the command line
  - After activating the virtual environment, run the following command to update pip to the latest version:
    - `pip install -U pip -y`
- To deactivate the virtual environment use the following command:
  - `conda deactivate`

---

### Using a shared virtual environment

The following virtual environments were created and available for use under the directory `/netopt/share/bin/local/bone/conda_envs/envs/`:

- `brain_py-3.7`
- `dioscoridess_tf-1.12_py-3.6`
- `knee_pipeline_tf-1.12_py-3.6`
- `pytorch  `
- `tf-2.0_py-3.6`

They can be activated by running:

- ```conda activate /netopt/share/bin/local/bone/conda_envs/envs/tf-2.0_py-3.6```

---

### Copying and modifying a shared virtual environment

The shared environments are, by design, read only. If you would like to install other libraries in one of these environments, first clone it into a location of your choice:

- ```conda create --clone /netopt/share/bin/local/bone/conda_envs/envs/tf-2.0_py-3.6 --prefix PATH```

Where `PATH` is the full path to where you want the environment to be created. After that you are free to `conda activate` your new environment and install any libraries of choice.

---

### [Conda CheatSheet][condacheat]

---

### Advanced

- Refer to the Scientific Computing Services (SCS) [official Python tutorial][scspython] for more advanced options (requires UCSF login)

---

<!-- Links -->
[anaconda]: https://www.anaconda.com/open-source
[condacheat]: /materials/conda-cheatsheet.pdf
[scspython]: https://wiki.radiology.ucsf.edu/bin/view/SCS/Tutorials/PythonIntro/