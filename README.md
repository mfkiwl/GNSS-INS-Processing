# GNSS/INS Processing

## About

This repository comprises Jupyter Notebooks presenting the outcomes of my MSc Thesis titled 'Development of a holistic open-source processing pipeline for drone-based hyperspectral line scanning systems'. The main goal was to establish an open-source workflow for the Post-Processing Kinematic (PPK) correction of Global Navigation Satellite System (GNSS) data. This corrected GNSS data was then integrated with Inertial Navigation System (INS) data using an Extended Kalman Filter (EKF). The ultimate goal was to provide precise positioning (X,Y,Z) and orientation (𝜙,𝜃,𝜓) informations for sensors mounted on Unmanned Aerial Vehicles (UAVs) (Multi/Hyperspectral cameras...).

## Implementation Details
### 1. Data Preparation
The automated workflow begins with the 'Convert_To_Rinex.ipynb' notebook, which establishes the foundation for converting APX-15 observations recorded in Trimble *.T04 proprietary format to the universally accepted RINEX format. This notebook integrates with tools like [runpkr00](https://kb.unavco.org/article/trimble-runpkr00-latest-versions-744.html) and [TEQC](https://www.unavco.org/software/data-processing/teqc/teqc.html), facilitating conversion and merging of RINEX (Receiver Independant Exchange Format) files to ensure seamless integration of observation and navigation data, eliminating potential gaps. Subsequently, the 'Download_Corrections_Files.ipynb' notebook automates the retrieval of crucial correction files for PPK from diverse GNSS sources, using FTP (File Transfer Protocol) and allowing customization based on parameters like date and nearest permanent station. This comprehensive workflow optimizes data processing by preparing a complete dataset for further analysis with open-source tools.
### 2. Data Processing
In the data processing phase, serving as a crucial link between data preparation and data fusion,the notebook 'PPK.ipynb' focuses on applying the PPK method to enhance the positional accuracy of raw GNSS observations.The notebook seamlessly integrates [RTKlib](https://www.rtklib.com/) into the automated workflow, utilizing raw GNSS data in RINEX format and correction files previously downloaded to perform differential corrections and improve the rover's positional accuracy.
### 3. Data visualization

