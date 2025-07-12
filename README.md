<h1>🧠 MNIST Ensemble CNN Classifier</h1>

<p>This project implements an <strong>ensemble of Convolutional Neural Networks (CNNs)</strong> to classify handwritten digits from the MNIST dataset using the raw <code>.idx</code> files. The ensemble improves prediction accuracy by averaging the outputs of multiple trained models.</p>

<h2>📦 Features</h2>
<ul>
  <li>Loads MNIST data directly from IDX files</li>
  <li>Applies data augmentation using Keras <code>ImageDataGenerator</code></li>
  <li>Builds CNN models with batch normalization and dropout</li>
  <li>Trains an ensemble of 5 CNNs</li>
  <li>Displays misclassified test samples for visual analysis</li>
</ul>

<h2>🧰 Dependencies</h2>
<pre><code>pip install numpy matplotlib tensorflow scikit-learn
</code></pre>

<h2>📁 File Structure</h2>
<pre><code>.
├── train-images.idx3-ubyte       # Raw training images
├── train-labels.idx1-ubyte       # Raw training labels
├── t10k-images.idx3-ubyte        # Raw test images
├── t10k-labels.idx1-ubyte        # Raw test labels
├── model_1.h5 to model_5.h5      # Saved CNN models
└── ensemble_cnn_mnist.py         # Main Python script
</code></pre>

<h2>🚀 How to Run</h2>
<ol>
  <li>Download the MNIST dataset from <a href="http://yann.lecun.com/exdb/mnist/">Yann LeCun's website</a>.</li>
  <li>Place the IDX files in the same directory as the script.</li>
  <li>Run the script with Python:</li>
</ol>
<pre><code>python ensemble_cnn_mnist.py
</code></pre>

<h2>📊 Sample Training Logs</h2>
<pre><code>🔁 Training model 1
Epoch 1/50 - accuracy: 0.9363 - val_accuracy: 0.9797
Epoch 5/50 - accuracy: 0.9842 - val_accuracy: 0.9918
Epoch 10/50 - accuracy: 0.9915 - val_accuracy: 0.9938
...
Epoch 27/50 - accuracy: 0.9960 - val_accuracy: 0.9948

🔁 Training model 2
Epoch 1/50 - accuracy: 0.9336 - val_accuracy: 0.9182
Epoch 5/50 - accuracy: 0.9848 - val_accuracy: 0.9882
Epoch 10/50 - accuracy: 0.9923 - val_accuracy: 0.9940
</code></pre>

<h2>✅ Final Results</h2>
<ul>
  <li><strong>Ensemble Test Accuracy:</strong> 99.71%</li>
  <li><strong>Total Misclassified Samples:</strong> 29</li>
</ul>

<p><img src="https://upload.wikimedia.org/wikipedia/commons/2/27/MnistExamples.png" width="500"/></p>

<h2>🧠 Model Architecture</h2>
<ul>
  <li>2 Conv2D layers → BatchNorm → MaxPooling → Dropout</li>
  <li>2 Conv2D layers → BatchNorm → MaxPooling → Dropout</li>
  <li>Dense(256) → BatchNorm → Dropout</li>
  <li>Dense(10) with softmax</li>
</ul>

<h2>📌 Notes</h2>
<ul>
  <li>Models are saved as <code>model_1.h5</code> to <code>model_5.h5</code>.</li>
  <li>You may see a warning about HDF5 format being legacy; it's safe to ignore or switch to <code>.keras</code> format.</li>
  <li>Adjust the ensemble size by modifying the training loop.</li>
</ul>

<h2>📜 License</h2>
<p>This project is licensed under the MIT License.</p>