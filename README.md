#  Automated_micro-section_drawing_digitalization
Scripts for automated digitalization of hand-drawn micro-section profiles – from preprocessing to spatial database.


#  Description

This repository provides a four-step, reproducible pipeline for converting hand-drawn field micro-section profiles into GIS-ready vector layers. The workflow was developed in colaboration with Institute of Archaeology, Czech Academy of Science in order to accelerate the digitization process of bulky section drawings of small test pits, i.e. probes.  The workflow covers image preprocessing, rectification, vectorization, and layer annotation.

Recommended execution order: Script1 → Script2 → Script3 → Script4

#  What’s included

## Notebooks

Script1_AutoFormPreprocessor.ipynb – cleans the scanned form, isolates the region of interest (ROI), and prepares inputs for downstream steps.

Script2_AutoRectifier.ipynb – rectifies/aligns the input image using a reference SCALE shapefile.

Script3_Autovectorizer.ipynb – detects and vectorizes layer boundaries; uses a scale template for robust scale detection via template matching.

Script4_LayerAnnotator.ipynb – adds attributes/labels to vectorized layers and prepares exports (Shapefile).

## Assets

SCALE.shp (+ sidecars like .dbf, .shx, etc.) — reference geometry for Script2 (rectification).

template_scale.jpg — scale template for Script3 (template matching of the scale on the form).

Sample_form.jpg — example input form you can use to verify the pipeline end-to-end.


# Quick start

1) Create the environment using requirements.txt.

2) Open Script1_AutoFormPreprocessor.ipynb

3) Set up the paths

4) Use your own scanned form or the provided Sampleform.jpg.

5) Run the notebook to clean the image and define the ROI for subsequent steps.

6) Open Script2_AutoRectifier.ipynb

7) Set up the paths

8) Ensure SCALE.shp (and sidecars) are available.

9) Run rectification/alignment and verify the output.

10) Open Script3_Autovectorizer.ipynb

11) Set up the paths

12) Ensure template.scale.jpg is available.

13) The notebook performs scale template matching, edge detection, and vectorization of layers.

14) Open Script4_LayerAnnotator.ipynb

15) Set up the paths

16) Load vector outputs, add layer attributes (IDs, descriptions, notes), and export for use in GIS.

Note on “scale”: in Script3, the scale refers to the visual ruler printed on the form (detected via template matching). In Script2, the SCALE shapefile serves as a geometric reference for rectification.

# How to cite

If you use any part of this workflow or code, please cite the repository:

APA (software / repository):
Hájek, F. (2025). Automated digitalization of hand-drawn micro-section profiles. GitHub repository. https://github.com/CSTAAR/Automated_micro-section_drawing_digitalization
