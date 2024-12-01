# SilenceMap-Adaptation-and-Extensions
SilenceMap-Adaptation-and-Extensions replicates and extends the [SilenceMap framework](https://github.com/Chamanzar/SilenceMap/tree/v1.0) for EEG-based BCI (Brain-Computer Interface) applications. The repository focuses on EEG preprocessing, SSVEP analysis, source localization, and Center of Mass (COM) calculations, while integrating novel techniques to enhance neural decoding accuracy.

## Key Features

1. **EEG Preprocessing:**
  - Step-by-step guide for preparing EEG data, including filtering, artifact removal, and channel mapping.
  - Integration with interactive tools for parameter adjustments.
2. **SSVEP Analysis:**
  - Implementation of steady-state visual evoked potential (SSVEP) paradigms.
  - Frequency-specific analysis to highlight neural responses in specific regions.
3. **Source Localization:**
  - Accurate localization of neural activity using advanced techniques.
  - Visualizations of neural sources projected onto MRI slices.
4. **Center of Mass (COM) Calculations:**
  - Interactive calculation and visualization of COM for lesion regions.
  - Comparison between EEG-derived COM and MRI-based ground truth.
5. **Interactive Tools:**
  - Sliders for threshold adjustment and slice selection to dynamically visualize and analyze data.
  - Real-time overlay of lesion masks on MRI slices.
6. **Novel Extensions:**
  - Exploration of advanced neural decoding methods, including WAVEFRONT and CSD-STGAT.
  - Testing novel models and paradigms to improve classification performance.

## Improvements from Original SilenceMap Framework
- **Interactive Visualizations**: Added interactive sliders for thresholding and slice selection to streamline data exploration.
- **COM Accuracy**: Enhanced COM calculations with visual overlays and export options.
- **Documentation and Modularization**: Organized notebook into clear sections for preprocessing, analysis, and visualization, improving readability and reproducibility.

## Datasets

The datasets used in this project were obtained from the CMU KiltHub repository: [Pediatric patients with lobectomy: MRI and EEG](https://kilthub.cmu.edu/articles/dataset/Pediatric_patients_with_lobectomy_MRI_and_EEG_/12402416). 

### Dataset Structure
```
datasets/
├── MRI_dataset/
│   ├── OT_defaced.nii.gz
│   ├── SN_defaced.nii.gz
│   └── UD_defaced.nii.gz
├── EEG_Dataset/
│   ├── DH/
│   │   ├── DH_SSVEP.bdf
│   ├── OT/
│   │   ├── OT_SSVEP_L.bdf
│   │   ├── OT_SSVEP_R.bdf
│   │   └── OT_SSVEP.bdf
│   ├── SN/
│   │   ├── SN_SSVEP_L.bdf
│   │   ├── SN_SSVEP_R.bdf
│   │   └── SN_SSVEP.bdf
│   ├── UD/
│   │   ├── UD_SSVEP_L.bdf
│   │   └── UD_SSVEP_R.bdf
├── EEG_Stimuli/
│   ├── maskandtest_m1.mat
│   ├── maskandtest_m2.mat
│   ├── vis_SSVEP.m
│   ├── vis_SSVEP_L.m
│   └── vis_SSVEP_R.m
├── EEG experiment protocol_KiltHub_vF.pdf
└── README_Chamanzar_vF.txt
```

### Steps to Download:
1. Download the datasets directly from [Kilthub](https://kilthub.cmu.edu/articles/dataset/Pediatric_patients_with_lobectomy_MRI_and_EEG_/12402416). 
2. Organize the downloaded files as shown in the directory structure above. Make sure that the naming conventions as shown in the structure above.

**Note**: The `datasets/` folder is **not included in this repository** to comply with the dataset's usage and licensing restrictions. Users are required to download the data directly from the source and ensure they have the appropriate permissions for its use.


## Installation and Setup
1. Clone this repository:
   ```
   git clone https://github.com/yourusername/SilenceMap-Adaptation-and-Extensions.git
   cd SilenceMap-Adaptation-and-Extensions
   ```
2. Install Python dependencies.
   Make sure you have Python 3.8+ installed. Then, install the required dependencies:
   ```
   pip install -r requirements.txt
   ```
3. Freesurfer Installation and Setup
   This project uses Freesurfer for MRI preprocessing and coregistration. Follow these steps to install and configure Freesurfer:
   1) Install Freesurfer:
      - Download and install Freesurfer from [https://surfer.nmr.mgh.harvard.edu/].
      - Follow the installation guide for your operating system.
   2) Set Environment Variables:
      -  Add the following to your `.bashrc` or `.zshrc`:
      ```
      export FREESURFER_HOME=/path/to/freesurfer
      source $FREESURFER_HOME/SetUpFreeSurfer.sh
      ```
   3) Run `recon-all`:
      - Process the MRI data using the `recon-all` command (replace `<subject_name>` with the actual subject name):
        ```
        recon-all -s <subject_name> -i /path/to/input_mri.nii.gz -all
        ```
      - This will process the MRI data and generate the necessary outputs in the `FREESURFER_HOME/subjects/subject_name/` directory.
   4) Coregister EEG and MRI Data:
      - Use the `mne coreg` GUI to coregister the EEG electrode positions with the MRI:
        ```
        mne coreg
        ```
      - Save the coregistration file as `coreg-trans.fif` into the appropriate directory.

## Usage
1. Prepare Data:
   - Place the downloaded data from Kilthub in the `datasets/` directory.
   - Run MRI preprocessing using FreeSurfer and generate surfaces.
2. Launch the Jupyter Notebook:
  ```
  jupyter notebook
  ```
3. Run the `Part1-SilenceMap_Replication.ipynb` Notebook. Follow the step-by-step instructions in the notebook to preprocess EEG data, compute COMs, and visualize the results.
4. View the generated results (from the notebook above) in the `results/` directory.


## Notebooks

1. `Part1-SilenceMap_Replication.ipynb`:
  - Replicates key findings from the SilenceMap framework.
  - Includes COM calculations, interactive thresholding, and lesion mask analysis.

## Contributions and Acknowledgments

This project builds upon the [SilenceMap framework](https://github.com/Chamanzar/SilenceMap/tree/v1.0), which is described in the paper [*Neural Silences can be Localized Rapidly Using Noninvasive Scalp EEG*](https://www.nature.com/articles/s42003-021-01768-0), incorporating feedback from the original authors (Chamanzar et al.) and leveraging advanced tools for EEG-based BCI research. Contributions are welcome! Please submit pull requests or open issues for discussion.
