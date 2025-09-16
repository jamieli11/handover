# Handover Documentation
## Summary

This document provides a list of materials to be handed over for all related work, including the ML marker detection model, dataset cleaning code, and data analysis tools for LabsVision.

---

## 1. ML Marker Detection Model

### Deliverables:
- **Model Weights**: Latest trained model weights with optimal performance (pt, ONNX and TensorRT engine models)
- **Source Code**: Complete codebase with newly implemented features
  - Inference module for running predictions on unlabeled datasets with qualitative visualization of results
  - Evaluation module for performance assessment with newly implemented metrics
  - Improved training module with corrected loss calculation and newly added TensorBoard writer for better model monitoring during training
  - Data module for dataset preparation, including dataset information JSON generation code and interactive dataset verification and checking tools
- **Documentation**: README with setup and usage instructions; model improvements description, results & analysis
- **Performance Metrics**: Include legacy metrics: f1 score and roc_auc_score and newly implemented metrics: detection f1-Score, boundary f1-score, and segmentation IoU (sIoU) for comprehensive performance assessment


### Location:
- **Model files**: 
  - S3 URI `s3://labscubed-dev/labscubedone/cubeone-2.0/labsvision_corpus/Ml_marker_detect/Model_weights/`
- **Code repository**: <https://github.com/LabsCubed-Inc/ML_marker_detect/tree/dev/jamie>
- **Documentation**: 
    - See repository [README](https://github.com/LabsCubed-Inc/ML_marker_detect/blob/dev/jamie/README.md) for model usage. 
    - For detailed model improvements record, see [here](https://github.com/jamieli11/work-daily-log/issues/4).

---

## 2. Data Cleaning Code

### Deliverables:
- **SAM2 Data Cleaner**: Data cleaner based on SAM2 model, including the following newly added code:
  - Data cleaner script
  - Data preparation and quality check code
  - Single frame model training configurations
- **Datasets**: 
  - S3 URI `s3://labscubed-dev/labscubedone/cubeone-2.0/labsvision_corpus/Ml_marker_detect/Dataset/`,  [chevron_cleaned_250828.zip](https://labscubed-dev.s3.us-east-2.amazonaws.com/labscubedone/cubeone-2.0/labsvision_corpus/Ml_marker_detect/Dataset/chevron_cleaned_250828.zip) (cleaned from [chevron_cube10_final.zip](https://labscubed-dev.s3.us-east-2.amazonaws.com/labscubedone/cubeone-2.0/labsvision_corpus/Ml_marker_detect/Dataset/chevron_cube10_final.zip) using SAM2 with manual filtering).
- **Documentation**: User guide and performance analysis

### Location:
- **Code repository**: <https://github.com/jamieli11/sam2/tree/dev/jamie>
- **Documentation**: See repository [README_LabsCubed](https://github.com/jamieli11/sam2/blob/dev/jamie/README_LabsCubed.md) for model usage. Preliminary performance analysis can be found [here](https://github.com/jamieli11/work-daily-log/issues/3). 

---

## 3. Analysis and Additional Tools

### Deliverables:
- **Labsvision Result Analysis Code**: Tools for analyzing and visualizing detection results

### Location:
- Analysis tools: <https://github.com/jamieli11/Labsvision_analysis_tools>

---

## 4. Reports and Documentation

### Deliverables:
- **Work Review**: Weekly review reports
- **Technical Documentation**: Detailed records of technical issues
- **Installation Guide**: Add Docker building guide for branch release-3.0.9 and branch chevron-cubeten-ml-experimental

### Location:
- Weekly review: <https://github.com/jamieli11/work-daily-log/blob/main/Weekly%20Review.md>
- Technical Documentation: <https://github.com/jamieli11/work-daily-log/issues>
- Installation Guide: 
  - branch [`release-3.0.9`](https://github.com/LabsCubed-Inc/labsvision/blob/dev/jamie/release-3.0.9/INSTALL.md)
  - branch [`chevron-cubeten-ml-experimental`](https://github.com/LabsCubed-Inc/labsvision/blob/dev/jamie/chevron-cubeten-ml-experimental/INSTALL.md)

---

## 5. Work in Progress and Future Work

### 5.1 [ML Marker Detection Model Loss Function Optimization](https://github.com/jamieli11/work-daily-log/issues/5)
**Status**: Initial research and testing completed

**Issue Identified**: Current loss function is not optimal for segmentation tasks

**Progress Made**:
- Conducted comparative testing of alternative loss functions
- Initial results show potential improvments
- Identified dice loss + bce loss as promising candidate

**Recommended Next Steps**:
- Complete full-scale testing with the improved loss function
- Validate results on test dataset
- Update model training pipeline accordingly

**Code Location**: <https://github.com/LabsCubed-Inc/ML_marker_detect/tree/dev/jamie/losses>

### 5.2 [SAM2 Data Cleaner Model Fine-tuning](https://github.com/jamieli11/sam2/blob/dev/jamie/README_LabsCubed.md)
**Status**: Training code completed, execution pending

**Objective**: Enhance SAM2 model performance for data cleaning tasks

**Current Situation**:
- Training code fully developed and tested
- Training halted due to insufficient server disk space
- All preprocessing and configuration files ready

**Recommended Next Steps**:
- Resolve server storage limitations
- Execute fine-tuning process with prepared training data
- Evaluate improved model performance on data cleaning tasks

**Code Location**: <https://github.com/jamieli11/sam2/tree/dev/jamie>