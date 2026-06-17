# Simulating the 2D Time-Dependent Schrodinger Equation (TDSE)

This project is a Jupyter notebook simulation of a two-dimensional Gaussian wave packet evolving under the time-dependent Schrodinger equation. It includes free propagation, single-slit diffraction, double-slit interference, and finite-barrier quantum tunnelling.

The main file is:

```text
report.ipynb
```

No external data files are required.

## Requirements

- Python 3.10 or newer
- A working terminal
- Internet access for the first dependency installation
- Jupyter Notebook or JupyterLab

The Python dependencies are listed in `pyproject.toml`.

## Step-By-Step Setup

Open a terminal in the project folder:

```bash
cd PDE-Project
```

On Windows PowerShell, the path may look like:

```powershell
cd C:\Users\rafal\OneDrive\Dokumente\GitHub\PDE-Project
```

### 1. Create a virtual environment

Windows PowerShell:

```powershell
py -3 -m venv .venv
```

macOS/Linux:

```bash
python3 -m venv .venv
```

### 2. Activate the virtual environment

Windows PowerShell:

```powershell
.\.venv\Scripts\Activate.ps1
```

If PowerShell blocks activation, run:

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
.\.venv\Scripts\Activate.ps1
```

macOS/Linux:

```bash
source .venv/bin/activate
```

### 3. Upgrade pip

```bash
python -m pip install --upgrade pip
```

### 4. Install the project dependencies

```bash
python -m pip install -e .
```

### 5. Register the notebook kernel

```bash
python -m ipykernel install --user --name tdse-pde-project --display-name "Python (TDSE PDE Project)"
```

### 6. Start Jupyter

Use JupyterLab:

```bash
jupyter lab report.ipynb
```

Or use classic Jupyter Notebook:

```bash
jupyter notebook report.ipynb
```

## How To Run The Notebook

1. Open `report.ipynb` in Jupyter.
2. Select the kernel named `Python (TDSE PDE Project)`.
3. Run the notebook from top to bottom.
4. The animation cells can take some time because they generate embedded JavaScript animations.
5. If a cell appears slow, wait for it to finish before running the next one.

Recommended menu option:

```text
Kernel -> Restart Kernel and Run All Cells
```

## What The Notebook Produces

The notebook generates:

- a free Gaussian wave packet animation,
- a single-slit diffraction animation,
- a double-slit interference animation,
- integrated probability plots behind the barriers,
- a detector-screen profile for the double-slit experiment,
- a finite-barrier tunnelling animation,
- a static tunnelling probability-density plot.

## Notes For Running Animations

The notebook uses:

```python
HTML(my_anim.to_jshtml())
```

so no `ffmpeg` installation is required.

The animations are embedded directly in the notebook output. This can make the notebook file larger after execution.

## Troubleshooting

If Jupyter cannot find the kernel, repeat:

```bash
python -m ipykernel install --user --name tdse-pde-project --display-name "Python (TDSE PDE Project)"
```

If imports fail, make sure the virtual environment is active and reinstall:

```bash
python -m pip install -e .
```

If animations do not display immediately, wait until the cell finishes. The conversion to embedded HTML may take longer than a normal static plot.
