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

## Getting Started
1. Clone this repository:
   ```
   git clone https://github.com/yourusername/SilenceMap-Adaptation-and-Extensions.git
   cd SilenceMap-Adaptation-and-Extensions
   ```
2. Install required dependencies:
   ```
   pip install -r requirements.txt
   ```
3. Launch the Jupyter Notebook:
  ```
  jupyter notebook
  ```

## Contributions and Acknowledgments

This project builds upon the [SilenceMap framework](https://github.com/Chamanzar/SilenceMap/tree/v1.0), which is described in the paper [*Neural silences can be localized rapidly using noninvasive scalp EEG*](https://www.nature.com/articles/s42003-021-01768-0), incorporating feedback from the original authors (Chamanzar et al.) and leveraging advanced tools for EEG-based BCI research. Contributions are welcome! Please submit pull requests or open issues for discussion.
