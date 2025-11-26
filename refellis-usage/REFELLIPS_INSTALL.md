# Installing RefEllips on Arch Linux

[Refellips documentation](https://refellips.readthedocs.io/en/main/index.html) 

Robertson, H., et al. refellips: A Python package for the analysis of variable angle spectroscopic ellipsometry data. *SoftwareX*, 20 (101225), 2022. [DOI: 10.1016/j.softx.2022.10122](https://doi.org/10.1016/j.softx.2022.10122)

Robertson, H. refellips: Ellipsometry data analysis in Python. *ORSO Workshop 2022*.  [YouTube Record](https://www.youtube.com/watch?v=rcwWq8ANckc)

---

This document provides a concise guide to installing **RefEllips** on Arch Linux and describes the required modifications to fix character‑encoding issues that occur when loading HORIBA ellipsometry
data generated on Windows systems (spe files).

------------------------------------------------------------------------

## 1. Installation on Arch Linux

RefEllips is a Python-based ellipsometry analysis tool. On Arch Linux, the recommended installation method is via **pip** inside a virtual environment assuming the following dependencies are already installed: pip, virtualenv, numpy, matplotlib, jupyterlab and ipykernel

### **Step 1 --- Create and activate a virtual environment**

``` bash
python -m venv --system-site-packages refellips-env
source refellips-env/bin/activate
```

### **Step 2 --- Install RefEllips**

Since refellips used functions from [refnx](https://github.com/refnx/refnx), this must be installed as well. Using pip:

``` bash
pip install "refnx[all]"
pip install  refellips
```

### **Step 3 --- Setting virtual environment un Jupyter**

To use the virtual environment in Jupyter notebooksas a python kernel, install it via ipykernel
```bash
python -m ipykernel install --user --name=refellips-env --display-name "Python 3 (refellips)"
```


------------------------------------------------------------------------

## 2. Fixing Encoding Issues (Windows → Unix)

HORIBA ellipsometers generate data files that include **Windows-1252**
encoded characters (notably degree symbols, µ, and non‑ASCII headers).\
RefEllips assumes **UTF-8**, causing parsing errors.

### **Location of the problematic function**

Inside the package, the error originates from file reading function

    refellips.dataSE.open_HORIBAfile

For other formats the same problem may apply. Nevertheless the following should fix them as well.
    
### **Required modification**

Replace the encoding in the original `dataSE()` calls in 

    $VENV/lib/python3.13/site-packages/refellips/dataSE.py:528

where $VENV stands for the directory where the vtual environment is allocates (usually in the Home directory). In particular exchange "ANSI" by "cp1252" in the line 528 from the dataSE.py file.

### **Why this works**

-   HORIBA Windows software uses **CP1252** encoding by default.
-   Linux tools expect **UTF‑8**, causing failures when encountering
    characters like `°` (0xB0 in CP1252).
-   Replacing undecodable bytes allows RefEllips to load datasets
    safely.
-   For scientific usage, these replaced characters do **not** affect
    the numerical spectra.

------------------------------------------------------------------------
