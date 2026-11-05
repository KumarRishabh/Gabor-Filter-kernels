INTERACTIVE LINE-FIELD WORKFLOW

Unzip this archive while preserving its folder structure.
Python 3.10 or later is required.

1. Open a terminal in this folder.
2. Create and activate a Python environment if desired.
3. Install dependencies:
   python -m pip install -r requirements.txt
4. Open the notebook:
   python -m jupyterlab python_notebooks/interactive_line_field_pipeline.ipynb
5. Run all cells. Change image near the top to inspect any of the eight images,
   then rerun the following cells. Gabor response/model inspection is interactive.

Contents
- One notebook: all numerical implementations are visible inside it.
- Eight input NPZ files: working RGB image, approved mask, fixed center/scale,
  and archived extraction metadata.
- Eight baseline trajectory NPZ files: three saved Bayesian model fields.
- Eight polynomial trajectory NPZ files.
- Eight pooled held-out prediction NPZ files: exact original comparison scores.
- requirements.txt and FILES.csv (inventory and SHA256 checksums).

No project .py scripts, src folder, model chains, Downloads images, or encoded
JSON data blocks are needed. Keep data/ and output/ beside python_notebooks/.

What is recomputed
Fresh Gabor energies and peaks, smoothness-based selection of measured
candidates, and fixed-setting optimization fits of all four models.

What is reused
The approved binary masks, completed Bayesian trajectories/uncertainty, and
original nested four-fold held-out predictions. Live optimization fits do not
rerun the completed HMC comparison. Pointwise angular uncertainty is conditional
on mask, center, candidate selection and tuning; it is not a whole-curve band.

The last notebook cell saves PNG/SVG/CSV files under output/notebook-results/.
The scientific code can be read without running the notebook; interaction
requires a live Jupyter kernel and the listed dependencies.
