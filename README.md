# iPhone Camera-Hole Inspection (AOI)

## ⚠️ Confidential / Proprietary
This repository is **confidential** and intended only for authorized reviewers/collaborators.  
Due to confidentiality obligations, **training data, production images, and certain deployment details are not included**.  

---

## Overview
This project implements an **AOI (Automated Optical Inspection)** pipeline for **iPhone camera-hole sidewall inspection**, targeting defects that vary significantly in scale and appearance. The system is designed to be robust under **reflective/low-contrast conditions** common in glass/metallic surfaces and to operate under **production constraints** suitable for real-time line deployment. 

---

## Key Ideas
- **Hybrid segmentation** approach to handle both **small** and **large** defect types within the camera-hole sidewall region.
- Pipeline tuning for **generalization** across variations (lighting, reflections, viewpoint) using robust preprocessing + deployment validation.
- **Production-oriented inference optimization** to meet runtime constraints.

---

## What the System Does
1. **Input**: camera-hole region images (single images, folder, video stream)
2. **Preprocessing**: normalization + optional ROI cropping for the sidewall region
3. **Hybrid Segmentation**:
   - branch/model/strategy optimized for **small defects**
   - branch/model/strategy optimized for **large defects**
4. **Postprocessing**:
   - mask cleanup (morphology / connected components)
   - defect measurement (area, length, bounding geometry)
5. **Decision**:
   - PASS/FAIL based on defect presence and severity thresholds

---

## Tech Stack
- **Language**: Python
- **Libraries**: PyTorch, OpenCV
