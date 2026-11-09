# Hybrid-Quantum-Classical-Model-for-Image-Classification
This project explores and benchmarks the performance of Quantum Machine Learning (QML) using a Variational Quantum Classifier (VQC) against a Classical Machine Learning approach (Support Vector Machine - SVM) for image classification tasks using the MNIST dataset (restricted to digits 0 and 1). Dimensionality is reduced to 4 bits (4 qubits) using Qiskit and Scikit-Learn.

# Pipeline Overview
1. Data Preparation & Reduction: Loads the MNIST dataset (mnist_784), filters for binary classes (0 and 1), and applies PCA (Principal Component Analysis) to reduce dimensions from 784 down to 4 components (retaining approximately 54.85% of total variance). Features are then scaled to the range [0, pi] for quantum encoding.
2. Quantum Circuit Design: Constructs a 4-qubit quantum circuit consisting of:
   - Feature Map: ZZFeatureMap (reps=2, entanglement='full').
   - Ansatz: RealAmplitudes (reps=3, entanglement='full', 16 trainable parameters, circuit depth of 47).
3. Model Training & Optimization:
   - Quantum VQC: Uses the COBYLA optimizer (maxiter=100) combined with StatevectorSampler (Ideal Simulator).
   - Classical Baseline: Uses a Support Vector Machine (SVM with an RBF kernel) as a benchmark.
4. Evaluation & Benchmarking: Evaluates performance using Accuracy, Precision, Recall, F1-Score, and Training Time.

# Benchmarking Results
While the classical SVM achieves exceptional performance very quickly due to the compressed 4-dimensional representation, this project demonstrates the feasibility and capability of a Variational Quantum Classifier (VQC) on a simulated quantum system, achieving an impressive 82.0% accuracy.

# Requirements
pip install qiskit qiskit-machine-learning qiskit-aer scikit-learn pandas seaborn matplotlib
