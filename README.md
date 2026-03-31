# Fluorescence Image Analysis Pipeline

This repository contains scripts for fluorescence image analysis and downstream data visualization developed for human glioma slice cultures.

## Repository contents

This repository includes three scripts:

1. **Data analysis in R**  
   Processes exported measurement tables and generates graphs for visualization and comparison of results.

2. **QuPath image analysis**  
   Main QuPath workflow for image-based analysis of fluorescence whole-slice images.

3. **QuPath sigma and threshold test for image analysis**  
   Used to test sigma and threshold settings on a subset of images in order to determine suitable average values for cell detection in the main QuPath analysis.

---

## Workflow overview

### 1. QuPath image analysis
Run the **QuPath image analysis** script first on your fluorescence image.

**Input:**  
Whole-slice fluorescence images

**Analysis steps:**  
- Cell detection and measurements in each channel  
- Classification of triple-overlap detections  
- Division of the slice into tiles  
- Removal of tiles containing fewer than 3 cells  
- Tile measurements and viability classification  

**Output:**  
CSV files containing exported measurements

---

### 2. Data analysis in R
Run the **Data analysis in R** script after the QuPath analysis.

This script uses the exported CSV files to:
- organize the measurement data
- calculate summary values
- generate plots and graphs for visualization

---

### 3. Sigma and threshold testing
The **QuPath sigma and threshold test** script was run on a subset of images to determine suitable detection settings.

This script was used to:
- test sigma and threshold values on selected images
- calculate average settings
- define parameters for the main QuPath image analysis workflow

---

## Suggested workflow order

1. Run **QuPath sigma and threshold test for image analysis** to determine suitable detection settings  
2. Run **QuPath image analysis** on whole-slice fluorescence images  
3. Export measurement results to CSV files  
4. Run **Data analysis in R** to generate plots and perform downstream analysis  

---

## Input data

The pipeline is designed for:

- whole-slice fluorescence images

---

## Output data

The workflow produces:

- CSV files with cell- and tile-level measurements
- graphical summaries generated in R

---

## Notes

- File paths in the scripts may need to be updated to match your local folder structure.
- The sigma/threshold test script was developed using a subset of images to estimate suitable average settings for the main image analysis.
- Depending on the dataset, threshold and sigma settings may need adjustment.

---

## Author

Kathrine Pii Frederiksen
