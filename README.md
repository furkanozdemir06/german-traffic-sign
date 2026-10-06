🚦 German Traffic Sign Recognition with CNN

A Convolutional Neural Network that recognizes 43 types of German traffic signs from small images, from speed limits and stop signs to wild animal crossings. Traffic sign recognition is a core building block of driver-assistance and autonomous driving systems.

🎯 Result
Metric	Score
Validation accuracy	~99.8%
Validation loss	~0.009
Classes	43
📦 Dataset

GTSRB - German Traffic Sign Recognition Benchmark, also available on Kaggle. The project combines the training, test and meta (reference sign) images into 51,882 images across 43 classes. The dataset is not included in this repository because of its size.

🔧 How It Works
Data loading: build image path and label tables from the Train, Test and Meta folders and map class IDs to sign names (for example 14 → Stop).
Exploration: plot the label distribution and preview one example of every class.
Preprocessing: convert BGR to RGB, resize every image to 30x30 pixels and scale pixel values to 0-1.
Split: 80% training and 20% validation.
Model: a custom CNN with three convolutional blocks (32 → 64 → 128 filters), Batch Normalization, Max Pooling and increasing Dropout (0.2 → 0.5), followed by a 512-unit dense layer and a 43-class softmax output.
Training: Adam optimizer, sparse categorical cross-entropy, 20 epochs with Early Stopping on validation loss.
Export: the trained model is saved as .h5, and converted to a lightweight TensorFlow Lite model for mobile and embedded use.
🛠️ Tech Stack

Python, TensorFlow/Keras, OpenCV, pandas, NumPy, scikit-learn, Matplotlib, Seaborn

📁 Files
GermanTrafficSign.ipynb: the full notebook, from data loading to model export
