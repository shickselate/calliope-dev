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
