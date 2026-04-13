<h1 align="center">🚀 Few-shot Learning with Prototypical Networks (ProtoNet)</h1>

<p align="center">
  <b>Meta-learning for classification with limited data</b><br>
  <b>Test Accuracy: 97.46% 🔥</b>
</p>

<hr>

<h2>📌 Overview</h2>

<p>
This project implements <b>Prototypical Networks (ProtoNet)</b>, a powerful approach for 
<b>few-shot learning</b>, where a model learns to classify data using only a few examples per class.
</p>

<p>
Instead of training a traditional classifier, ProtoNet learns an <b>embedding space</b> 
where samples from the same class are clustered together.
</p>

<hr>

<h2>🧠 Key Idea</h2>

<ul>
  <li>Learn a meaningful <b>embedding space</b></li>
  <li>Compute a <b>prototype (mean vector)</b> for each class</li>
  <li>Classify query samples based on <b>distance to prototypes</b></li>
</ul>

<h3>🔄 Pipeline</h3>

<pre>
Support Set → Compute Prototype → Compare Query → Predict Class
</pre>

<hr>

<h2>📦 Dataset</h2>

<ul>
  <li><b>Dataset:</b> Omniglot</li>
  <li>1623 character classes</li>
  <li>20 samples per class</li>
</ul>

<p>
Omniglot is widely used for few-shot learning because it contains a large number of classes 
with very few samples each.
</p>

<hr>

<h2>🏗️ Model Architecture</h2>

<ul>
  <li>4-layer Convolutional Neural Network (CNN)</li>
  <li>Each block includes:</li>
</ul>

<pre>
Conv2D → BatchNorm → ReLU → MaxPool
</pre>

<ul>
  <li>Output: embedding vector</li>
</ul>

<p>
The model maps images into a feature space where similar samples are closer together.
</p>

<hr>

<h2>🔁 Training Strategy</h2>

<ul>
  <li>Training is performed using <b>episodic learning</b></li>
  <li>Each episode simulates a few-shot task</li>
</ul>

<h3>Example Configuration</h3>

<pre>
5-way 5-shot
→ 5 classes
→ 5 samples per class
</pre>

<h3>Training Logs</h3>

<pre>
Episode 0   | Acc: 0.93  
Episode 200 | Acc: 1.00  
Episode 800 | Acc: 1.00  
Episode 950 | Acc: 0.97  
</pre>

<p>
The model converges quickly and achieves near-perfect training accuracy.
</p>

<hr>

<h2>🧪 Evaluation</h2>

<pre>
Test Accuracy: 0.9746 (~97.46%)
</pre>

<h3>Comparison</h3>

<ul>
  <li>ProtoNet paper: ~99.7%</li>
  <li>This implementation: ~97.46%</li>
</ul>

<p>
This is a strong result for a basic implementation without heavy optimization.
</p>

<hr>

<h2>🖼️ Episode Visualization</h2>

<p align="center">
  <img src="image.png" width="80%">
</p>

<h3>Explanation</h3>

<ul>
  <li>Each row represents one class</li>
  <li><b>S0 → S4:</b> Support samples</li>
  <li><b>Q:</b> Query sample</li>
</ul>

<h3>How it works</h3>

<ul>
  <li>Compute prototype from support samples</li>
  <li>Embed query image</li>
  <li>Compute distance to all prototypes</li>
  <li>Select nearest class</li>
</ul>

<h3>Observation</h3>

<ul>
  <li>Query images visually match their support class</li>
  <li>Classes are clearly separated</li>
</ul>

<p>
This confirms that the model has learned a meaningful embedding space.
</p>

<hr>

<h2>📊 Results Analysis</h2>

<ul>
  <li>✅ High test accuracy (~97%)</li>
  <li>✅ Fast convergence</li>
  <li>✅ Stable training behavior</li>
  <li>⚠️ Slight gap compared to state-of-the-art (~99%)</li>
</ul>

<hr>

<h2>⚠️ Limitations</h2>

<ul>
  <li>Simple CNN backbone</li>
  <li>No embedding normalization</li>
  <li>Training only on 5-way tasks</li>
</ul>

<hr>

<h2>🚀 Future Improvements</h2>

<ul>
  <li>Add L2 normalization to embeddings</li>
  <li>Use deeper backbone (e.g., ResNet)</li>
  <li>Train with harder tasks (20-way)</li>
  <li>Apply to more complex datasets (miniImageNet)</li>
</ul>

<h2>🎯 Conclusion</h2>

<ul>
  <li>✔ Successfully implemented ProtoNet from scratch</li>
  <li>✔ Learned a strong embedding space</li>
  <li>🔥 Achieved high accuracy close to benchmark</li>
</ul>

<hr>

<h2>👨‍💻 Author</h2>

<p>
Developed as part of a deep learning / computer vision study project.
</p>

<p align="center">
⭐ If you find this project useful, consider giving it a star!
</p>