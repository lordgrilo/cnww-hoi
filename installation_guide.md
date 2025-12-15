# Installation Guide {.unnumbered}

This guide provides detailed installation instructions for all packages used in the tutorial series.

## System Requirements

**Minimum:**
- Python 3.8 or higher
- 8GB RAM
- 2GB free disk space

**Recommended:**
- Python 3.10 or higher
- 16GB RAM
- 5GB free disk space
- CUDA-compatible GPU (optional, for faster HOI computations)

## Installation Methods

### Method 1: Quick Install (Recommended for Most Users)

This method installs all packages at once using pip:

```bash
# Clone the repository
git clone https://github.com/yourusername/multivariate-information-theory-tutorial.git
cd multivariate-information-theory-tutorial

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install all dependencies
pip install -r requirements.txt

# Launch Jupyter
jupyter notebook
```

### Method 2: Conda Environment (Alternative)

If you prefer conda:

```bash
# Create conda environment
conda create -n infotheory python=3.10
conda activate infotheory

# Install core packages
conda install numpy scipy matplotlib seaborn pandas jupyter

# Install specialized packages via pip
pip install hoi frites xgi jax jaxlib mne networkx
```

### Method 3: Step-by-Step Installation

Install packages progressively as you work through the notebooks:

**For Notebooks 1-2 (Foundations):**
```bash
pip install numpy scipy matplotlib seaborn jupyter
```

**Add for Notebook 3 (HOI):**
```bash
pip install hoi jax jaxlib
```

**Add for Notebook 4 (Frites):**
```bash
pip install frites mne
```

**Add for Notebook 5 (XGI):**
```bash
pip install xgi networkx
```

## Platform-Specific Instructions

### Linux

Standard pip installation works for all packages:
```bash
pip install -r requirements.txt
```

### macOS

**For Apple Silicon (M1/M2/M3):**
```bash
# JAX requires special attention
pip install jax-metal  # For GPU acceleration
pip install -r requirements.txt
```

**For Intel Macs:**
```bash
pip install -r requirements.txt
```

### Windows

**Windows 10/11:**
```bash
# Install Visual C++ Build Tools first if you encounter compilation errors
pip install -r requirements.txt
```

## GPU Support (Optional but Recommended)

JAX can utilize GPUs for faster computation in HOI.

### NVIDIA GPUs (CUDA)

```bash
# Install CUDA-enabled JAX
pip install jax[cuda12]  # For CUDA 12.x
# OR
pip install jax[cuda11]  # For CUDA 11.x
```

Check CUDA availability:
```python
import jax
print(jax.devices())  # Should show GPU devices
```

### AMD GPUs (ROCm)

```bash
pip install jax[rocm]
```

### Apple Silicon (Metal)

```bash
pip install jax-metal
```

## Verifying Installation

### Quick Test Script

Save as `test_installation.py`:

```python
#!/usr/bin/env python
"""Test script to verify all packages are installed correctly."""

import sys

def test_package(name, import_name=None):
    """Test if a package can be imported."""
    if import_name is None:
        import_name = name
    try:
        __import__(import_name)
        print(f"✓ {name}")
        return True
    except ImportError as e:
        print(f"✗ {name}: {e}")
        return False

print("Testing required packages...\n")

packages = [
    ("NumPy", "numpy"),
    ("SciPy", "scipy"),
    ("Matplotlib", "matplotlib"),
    ("Seaborn", "seaborn"),
    ("Pandas", "pandas"),
    ("Jupyter", "jupyter"),
    ("HOI", "hoi"),
    ("JAX", "jax"),
    ("Frites", "frites"),
    ("MNE", "mne"),
    ("XGI", "xgi"),
    ("NetworkX", "networkx"),
]

results = [test_package(name, imp) for name, imp in packages]

print(f"\nPassed: {sum(results)}/{len(results)}")

if all(results):
    print("\n🎉 All packages installed successfully!")
    print("You're ready to start the tutorials!")
else:
    print("\n⚠️  Some packages failed to install.")
    print("Please review the error messages above.")
    sys.exit(1)
```

Run it:
```bash
python test_installation.py
```

### Individual Package Tests

**Test NumPy and SciPy:**
```python
import numpy as np
import scipy
print(f"NumPy: {np.__version__}")
print(f"SciPy: {scipy.__version__}")
```

**Test HOI:**
```python
import hoi
print(f"HOI version: {hoi.__version__}")

# Test basic functionality
from hoi.metrics import Oinfo
model = Oinfo(X=np.random.randn(3, 100))
print("HOI working correctly!")
```

**Test Frites:**
```python
import frites
print(f"Frites version: {frites.__version__}")
```

**Test XGI:**
```python
import xgi
print(f"XGI version: {xgi.__version__}")

# Create simple hypergraph
H = xgi.Hypergraph([[1, 2], [2, 3, 4]])
print(f"Created hypergraph with {H.num_nodes} nodes")
```

## Troubleshooting

### Common Issues

#### Issue: "No module named 'jax'"

**Solution:**
```bash
pip install --upgrade jax jaxlib
```

#### Issue: JAX doesn't detect GPU

**Solutions:**
1. Verify CUDA installation: `nvidia-smi`
2. Reinstall with correct CUDA version:
   ```bash
   pip install --upgrade jax[cuda12]
   ```
3. Check compatibility: https://github.com/google/jax#installation

#### Issue: MNE installation fails

**Solution:**
```bash
# Install dependencies first
conda install -c conda-forge mne
# OR
pip install mne --no-deps
pip install -r requirements.txt
```

#### Issue: "Kernel died" in Jupyter

**Possible causes:**
- Insufficient memory
- Package version conflicts

**Solutions:**
1. Close other applications
2. Create fresh virtual environment
3. Update all packages: `pip install --upgrade -r requirements.txt`

#### Issue: Import errors despite successful installation

**Solution:**
```bash
# Verify Python path
python -c "import sys; print('\n'.join(sys.path))"

# Ensure virtual environment is activated
which python  # Should point to venv/bin/python
```

### Getting Help

If you encounter issues:

1. **Check version compatibility**: Ensure Python ≥ 3.8
2. **Update pip**: `pip install --upgrade pip`
3. **Check GitHub Issues**: 
   - [HOI Issues](https://github.com/brainets/hoi/issues)
   - [Frites Issues](https://github.com/brainets/frites/issues)
   - [XGI Issues](https://github.com/xgi-org/xgi/issues)
4. **Open an issue** in this repository with:
   - Python version: `python --version`
   - OS and version
   - Full error message
   - Output of `pip list`

## Optional: Development Installation

For contributing or development:

```bash
# Clone with development dependencies
git clone https://github.com/yourusername/repo.git
cd repo

# Install in editable mode
pip install -e .

# Install development dependencies
pip install pytest black flake8 mypy
```

## Next Steps

Once installation is complete:

1. ✓ Verify with test script
2. ✓ Launch Jupyter: `jupyter notebook`
3. ✓ Open [Notebook 1](01_information_theory_foundations.ipynb)
4. ✓ Start learning!

---

::: {.callout-note}
## Keep Your Environment Updated

Packages are actively developed. Periodically update:
```bash
pip install --upgrade -r requirements.txt
```
:::
