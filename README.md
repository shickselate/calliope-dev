# FaceToBrain: MRI-Free Estimation of Deep Brain Targets from Facial Landmarks

This repository contains a Python pipeline for estimating individualised deep brain targets from a facial image — without requiring MRI. The system uses MediaPipe FaceMesh to extract 2D facial fiducials, aligns them to a 3D brain template using a similarity transform, and visualises the estimated targets over a standard MNI brain.

---

## 🚀 Features

- Extracts 3D facial fiducials from a single photo
- Estimates brain targets (e.g. ACC, SGC, ALIC, amygdala) via affine transform
- Visualises both fiducials and targets in interactive 3D plots
- Overlays on a mesh-reconstructed MNI brain (from NIfTI file)

---

## 📦 Requirements

Install dependencies with:

```bash
pip install opencv-python mediapipe matplotlib nibabel scikit-image plotly
```


## 📂 How It Works

1. Upload a facial photo (`.jpg` or `.png`)
2. MediaPipe detects 468 facial landmarks
3. A subset of fiducials is extracted:
   - Nasion
   - LOC (left outer canthus)
   - ROC (right outer canthus)
   - LPA (left preauricular)
   - RPA (right preauricular)
4. A similarity transform is computed between 2D facial fiducials and a 3D anatomical template
5. Deep brain targets are projected into the subject’s 3D space
6. *(Optional)* A 3D MNI brain is loaded from a NIfTI file and used for visual overlay

---

## 🧠 Targets Estimated

- ACC (anterior cingulate cortex)  
- PGC (pregenual cingulate)  
- SGC (subgenual cingulate)  
- L/R Amygdala  
- L/R ALIC (anterior limb of the internal capsule)

---

## 📊 Outputs

- Interactive 3D plot of subject-space fiducials and brain targets
- *(Optional)* 3D overlay on standard MNI brain surface
- Affine transformation matrix for reproducible targeting and analysis

---

## 📝 Notes

- Default brain template: `icbm_avg_152_t1_tal_nlin_symmetric_VI.nii`
- All spatial units are in millimetres (MNI convention)
- Targeting accuracy depends on facial image quality, resolution, and pose

