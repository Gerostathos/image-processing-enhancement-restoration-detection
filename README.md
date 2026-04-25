# Image Processing: Enhancement, Restoration, and Detection

This project contains a notebook-based image analysis and computer vision workflow. It was developed as an image analysis and processing assignment and covers a sequence of practical tasks involving grayscale transformations, image enhancement, sharpening, restoration, edge detection, line detection, corner detection, and geometric image alignment.

The original assignment notebook has been split into three smaller Jupyter notebooks to make the project easier to read, run, and render on GitHub. The implementation uses Python libraries such as OpenCV, NumPy, Matplotlib, scikit-image, scikit-learn, and SciPy.

---

## Project Overview

The project includes the following tasks:

1. **Grayscale intensity transformation**
   - Applies a piecewise intensity transformation.
   - Compares the original and transformed image visually and through histograms.

2. **Brightness and color enhancement of a dark forest image**
   - Uses gamma correction.
   - Applies CLAHE for local contrast enhancement.
   - Combines enhancement with HSV-based color boosting.
   - Compares enhancement strategies visually.

3. **Brightness enhancement of a pollen image**
   - Applies gamma correction and CLAHE.
   - Compares the effect of global and local enhancement methods.

4. **Image sharpening**
   - Implements unsharp masking.
   - Implements high-boost filtering.
   - Compares sharpening strength and visual quality.

5. **Image restoration / approximation**
   - Investigates a possible transformation pipeline between two images.
   - Uses inversion, gamma correction, Gaussian blur, and histogram matching.

6. **Edge, line, and corner detection**
   - Applies edge detection methods including Canny, Sobel, Prewitt-style filtering, Roberts, Laplacian, and LoG.
   - Uses Hough line detection to estimate roof/window line orientations.
   - Applies Harris and Shi-Tomasi corner detection.
   - Uses DBSCAN clustering to localize window regions.

7. **Billiard cue alignment and image combination**
   - Estimates cue orientation using line detection.
   - Rotates and compares images using SSIM.
   - Extracts cue regions using thresholding, morphology, connected components, and geometric constraints.
   - Blends extracted cue information into a target image.

---

## Repository Structure

```text
image-processing-enhancement-restoration-detection/
│
├── README.md
├── requirements.txt
├── .gitignore
│
├── data/
│   ├── First-photo-of-the-moon-from-Chandrayaan-2_ISRO.jpg
│   ├── image_1.jpg
│   ├── image_2.jpg
│   ├── image11.jpg
│   ├── image31.png
│   ├── image32.png
│   ├── image33.png
│   ├── nature_dark_forest.jpg
│   └── pollen-500x430px-96dpi.jpg
│
└── notebooks/
    ├── 01_image_enhancement_preprocessing.ipynb
    ├── 02_restoration_sharpening.ipynb
    └── 03_detection_geometry_analysis.ipynb
```

---

## Notebooks

The project is organized into three smaller notebooks:

1. **`01_image_enhancement_preprocessing.ipynb`**  
   Covers Tasks 1–3:
   - grayscale intensity transformation,
   - histogram comparison,
   - gamma correction,
   - CLAHE,
   - HSV-based color and brightness enhancement.

2. **`02_restoration_sharpening.ipynb`**  
   Covers Tasks 4–5:
   - unsharp masking,
   - high-boost filtering,
   - image restoration / approximation,
   - inversion,
   - gamma correction,
   - Gaussian blur,
   - histogram matching.

3. **`03_detection_geometry_analysis.ipynb`**  
   Covers Tasks 6–7:
   - edge detection,
   - Hough line transform,
   - roof/window angle estimation,
   - Harris and Shi-Tomasi corner detection,
   - DBSCAN-based window localization,
   - billiard cue angle estimation,
   - rotation and SSIM comparison,
   - cue extraction and blending.

The notebooks are intended to be run in numerical order because each one corresponds to a different stage of the original assignment workflow.

---

## Data and Image Files

The notebooks depend on the image files stored in the `data/` folder.

Because the notebooks are located inside the `notebooks/` folder, image paths should be written as relative paths such as:

```python
"../data/image_1.jpg"
"../data/nature_dark_forest.jpg"
"../data/image31.png"
```

Avoid absolute local paths such as:

```python
"C:/Users/..."
```

or:

```python
"C:\\Users\\..."
```

These paths will not work for other users after the project is uploaded to GitHub.

Before making the repository public, make sure that the included images are allowed to be shared publicly. If any image is copyrighted or assignment-restricted, remove it from the repository and document how to obtain it locally instead.

---

## How to Run

### 1. Clone the repository

```bash
git clone https://github.com/Gerostathos/image-processing-enhancement-restoration-detection.git
cd image-processing-enhancement-restoration-detection
```

### 2. Create and activate a virtual environment

```bash
python -m venv .venv
```

Windows:

```bash
.venv\Scripts\activate
```

macOS / Linux:

```bash
source .venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Open Jupyter Notebook

```bash
jupyter notebook
```

Then open the notebooks from the `notebooks/` folder.

Recommended order:

```text
notebooks/01_image_enhancement_preprocessing.ipynb
notebooks/02_restoration_sharpening.ipynb
notebooks/03_detection_geometry_analysis.ipynb
```

Run the cells in each notebook from top to bottom.

---

## Main Libraries Used

- OpenCV
- NumPy
- Matplotlib
- scikit-image
- scikit-learn
- SciPy

---

## Notes

- The project is notebook-based and intended for exploratory image processing experiments.
- The original large notebook was split into three smaller notebooks to improve readability and GitHub rendering.
- The notebooks contain both code cells and explanatory markdown cells.
- Some tasks rely on manual parameter exploration and visual comparison.
- If the notebooks were originally developed with local Windows paths, update them to relative `../data/...` paths before uploading to GitHub.
- The generated visual outputs are shown inside the notebooks and do not need to be stored separately unless desired.

---

## Possible Future Improvements

Possible extensions include:

- converting repeated code blocks into reusable Python functions,
- moving helper functions into a separate `src/` folder,
- adding a small `outputs/` folder for selected generated results,
- adding clearer image-source documentation,
- adding automated checks that all required images exist before running each notebook.
