# Support Vector Machine (SVM) with Kernels

This project implements a Support Vector Machine (SVM) classifier with different kernel functions, primarily focusing on the Radial Basis Function (RBF) kernel. The code includes functions for training SVMs, handling multiclass classification, predicting classes, and visualizing the results.

--Main Functions

1. RBF Kernel
The RBF kernel is the best type of kernel here as it is the only type that can classify nonseparable data correctly. It works by mapping input features to a higher dimension using an infinite number of dimensions.

2. `svmtrain`
This function takes the data along with `C` and `gamma` parameters, passes the data to the RBF kernel, and then solves the equation using `cvxopt` to get the alpha values. It identifies the correct support vectors based on these alphas, calculates the weight and bias terms, and returns the following:
- `alpha_filtered`
- `support_vectors`
- `support_vector_labels`
- `b`

These outputs are essential for further functions.

3. `svmtrainmulticlass`
This function is the main entry point for training the SVM. It uses a one-vs-all approach to predict the classes. The models returned from `svmtrain` are collected into a list for further use.

4. `Predictclasses`
Using the trained models, this function predicts the class of test data points. It loops through each model to get the scores and determines the class based on the index of the highest score.

5. Visualization
This function visualizes the data points and decision boundaries. It calculates a mesh grid based on the min and max points, passes the grid points to the `Predictclasses` function, and then plots the classes and background based on the predictions to match the color of the labels.

How to Use

1. Training: Use `svmtrainmulticlass` to train the SVM models with your dataset.
2. Prediction: Use `Predictclasses` with your test data points to classify them.
3. Visualization: Visualize the classification results using the `Visualization` function to see the decision boundaries and data points.

--Dependencies

- Python
- NumPy
- cvxopt
- Matplotlib (for visualization)

--Installation

pip install numpy cvxopt matplotlib
