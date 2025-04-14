# PRML_project

# Hand-drawn Sketch Recognition

## Project Overview

This repository contains the implementation of a hand-drawn sketch recognition system using feature extraction techniques and machine learning classifiers. The project was developed as part of the CSL2050: Pattern Recognition and Machine Learning course.

## Abstract

This project focuses on recognizing hand-drawn sketches using feature extraction techniques such as Histogram of Oriented Gradients (HOG) and Local Binary Patterns (LBP), followed by classification using Support Vector Machines (SVM). The dataset comprises various categories of hand-drawn objects. Experiments are conducted with and without Principal Component Analysis (PCA) for dimensionality reduction. The project evaluates model performance based on classification accuracy and precision metrics.

## Technical Approaches

The repository implements multiple approaches for sketch recognition:

### Feature Extraction Methods
- **Histogram of Oriented Gradients (HOG)**: Computes gradient orientation histograms per cell
- **Local Binary Patterns (LBP)**: Encodes local texture patterns

### Classification Methods
- **SVM-based Classification**: Using linear SVM with different feature combinations
- **KNN Classification**: Implementation with various distance metrics and parameters
- **Dimensionality Reduction**: Optional PCA implementation to reduce feature dimensions

## Results

Our experiments yielded the following results:

| Approach | Accuracy | Precision | Notes |
|----------|----------|-----------|-------|
| HOG + SVM | 75.4% | 76.1% | Best overall performance |
| LBP + SVM | 64.2% | 65.0% | Sensitive to sketch noise |
| HOG + PCA + SVM | 71.8% | - | Good dimensionality reduction |
| LBP + PCA + SVM | 60.1% | - | Some information loss in PCA |

## Directory Structure

- `Project_report`: Detailed documentation of the project
- `PRML_project_SVM.ipynb`: Implementation of SVM-based approaches
- `PRML_project_knn.ipynb`: Implementation of KNN classifier
- `demo_PRML_Project_knn+CNN.ipynb`: Demo notebook with KNN and CNN implementations

## Dataset

The dataset consists of hand-drawn sketches organized by categories. Images are in PNG format, with each category having its own directory. Some of the categories include animals, household objects, vehicles, and more.

## Dependencies

- Python 3.x
- NumPy
- OpenCV (cv2)
- scikit-learn
- scikit-image
- Matplotlib
- TensorFlow/Keras (for CNN implementations)

## Usage

1. Clone the repository
2. Ensure all dependencies are installed
3. To run the SVM-based approach:
   ```
   jupyter notebook PRML_project_SVM.ipynb
   ```
4. To run the KNN-based approach:
   ```
   jupyter notebook PRML_project_knn.ipynb
   ```
5. For a demonstration with visual results:
   ```
   jupyter notebook demo_PRML_Project_knn+CNN.ipynb
   ```

## Contributors

- Sonic Vyas (b23cs1100@iitj.ac.in)
- Yash Kumar Singh (b23cs1102@iitj.ac.in)
- Shardul Vikram Singh (b23cs1067@iitj.ac.in)
- Sarthak Bhiwaji Kolekar (b23cs1065@iitj.ac.in)
- Shlok Kanani (b23cs1068@iitj.ac.in)

All contributors are from Indian Institute of Technology Jodhpur.

## Future Work

Potential improvements include:
- Implementing deep learning-based approaches (CNNs, transformers)
- Exploring ensemble methods combining multiple feature extractors
- Improving robustness to variations in drawing styles
- Expanding the dataset with more categories

## License

This project is available for academic and research purposes.
