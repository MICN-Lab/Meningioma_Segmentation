# Meningioma Segmentation GUI v1.1

Windows desktop application for research use in MRI-based meningioma segmentation. The GUI provides a local workflow for loading T1 contrast-enhanced and FLAIR MRI studies, running a bundled nnU-Net v1 model, reviewing tumor and edema masks, and inspecting generated output files.

This software is intended for academic, non-commercial research use only. It is not a certified medical device and must not be used as the sole basis for clinical decision-making.

Meningioma Segmentation GUI showing loaded MRI views, segmentation overlays, mask legend, log output, and resource monitors:

<img width="1008" height="752" alt="meningioma_gui" src="https://github.com/user-attachments/assets/8449efa5-446b-4a10-8a92-643979a00338" />

## What the GUI Provides

- Input selection for NIfTI files, NIfTI folders, or DICOM folders.
- Two-channel model workflow for T1 contrast-enhanced MRI and FLAIR MRI.
- Automatic DICOM-to-NIfTI conversion when DICOM input is selected.
- nnU-Net-compatible preprocessing and inference.
- Bundled model inference for `Task001_Meningioma`.
- Axial, coronal, and sagittal image viewers.
- Segmentation overlay review with mask legend.
- Tumor and edema label visualization.
- Lesion volume progression chart.
- Runtime log with preprocessing and inference status.
- Live CPU, RAM, GPU, and process memory indicators.
- Optional low-RAM override for expert users.

## Segmentation Labels

- `1`: Tumor
- `2`: Edema

The overlay viewer is intended for visual quality control. Outputs should be reviewed by qualified users against the original imaging data.

## Typical Workflow

1. Select one or more NIfTI files, or select a folder containing NIfTI or DICOM data.
2. Choose an output directory.
3. Confirm T1ce/FLAIR assignment if the GUI reports uncertainty.
4. Run segmentation.
5. Review axial, coronal, and sagittal overlays.
6. Inspect the volume chart and output folder.


## Download and Run
# Download under this link: - OwnCloud mirror: https://owncloud.damutten.ch/s/nFnt5R6Gg9q69kd

The `.exe` must remain inside the extracted `MeningiomaSegmentation` folder together with its `_internal` runtime folder.


## Low-RAM Override

The `Allow low-RAM run` checkbox is off by default. With the default safety behavior, the pipeline checks available RAM before and during inference. If the checkbox is enabled, the GUI bypasses the startup free-RAM stop and runtime memory pause guard.

This option is intended only for expert users on constrained research workstations. Enabling it can increase the risk of system slowdown, process failure, or out-of-memory termination.

## Validation

The packaged executable was built and smoke-tested on Windows. Validation included:

- source syntax checks
- GUI startup smoke test
- PyInstaller one-folder executable build
- packaged executable smoke test
- checksum generation
- split archive byte-count verification

These checks verify package integrity and startup behavior. They do not constitute clinical validation.

## Citation

This application uses nnU-Net. Please cite:

Isensee F, Jaeger PF, Kohl SAA, Petersen J, Maier-Hein KH. nnU-Net: a self-configuring method for deep learning-based biomedical image segmentation. Nature Methods. 2020. https://doi.org/10.1038/s41592-020-01008-z

The Zurich Neurosurgical Toolkit license also requests citation of the University of Zurich as the software source and the publications listed in `LICENSE.txt` where applicable.

## License

Academic non-commercial use only. By downloading or using the software, users agree to the license terms distributed with the repository and packaged application.

