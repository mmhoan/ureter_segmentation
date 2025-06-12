# Ureter Segmentation Using Dual-Energy CT-Based Two-Material Decomposition

This repository provides a pretrained nnU-Net model for automatic segmentation of the ureter using dual-energy CT-derived virtual unenhanced (VUE) images.

---

## Overview

This model was trained on VUE images generated from late excretory phase (LEP) scans using two-material decomposition. Ground truth was created from contrast-filled ureter regions. The nnU-Net framework (v1.6.6) was used for training and inference.

The segmentation target is the upper urinary tract, specifically the ureter.

---

## Model Download

Pretrained model weights are available at the following link:

📦 [Download ureter segmentation model](https://drive.google.com/file/d/11L__FilGi0da0DAA84NnVvRlDuz1cK3U/view?usp=drive_link)

After downloading, unzip the file and place the contents under the following path:

nnUNet_trained_models/nnUNet/3d_fullres/Task099_Ureter_VUE/nnUNetTrainerV2__nnUNetPlansv2.1_big/

> Create the directory manually if it doesn't already exist.

---
## Inference

To run inference on new NIfTI-format images, use the following script:

### 🔧 `run_inference.sh`

```bash
#!/bin/bash

INPUT_FOLDER="/path/to/your/input"
OUTPUT_FOLDER="/path/to/save/output"

nnUNet_predict \
  -i "$INPUT_FOLDER" \
  -o "$OUTPUT_FOLDER" \
  -t "Task099_Ureter_VUE" \
  -m "3d_fullres" \
  -tr "nnUNetTrainerV2" \
  -p "nnUNetPlansv2.1_big" \
  -f 0 \
  --disable_tta
```

Make the script executable and run:

```bash
chmod +x run_inference.sh
./run_inference.sh
```
## Environment
Python 3.8+

nnU-Net v1.6.6

PyTorch (GPU recommended)

nibabel, SimpleITK, numpy

You can install required dependencies using:
pip install nnunet simpleitk nibabel
## Citation
If you use this model or code, please cite the corresponding paper:

Moon M, et al.
Feasibility of Training Data Extraction for Ureter Segmentation Using Dual-Energy CT-Based Two-Material Decomposition
In preparation / Under review

## License
This model and associated code are shared for academic and research purposes only.


---
