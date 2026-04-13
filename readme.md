<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Few-shot Learning with Prototypical Networks</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      line-height: 1.6;
      margin: 40px;
      background-color: #f9f9f9;
      color: #333;
    }
    h1, h2, h3 {
      color: #2c3e50;
    }
    code {
      background: #eee;
      padding: 2px 6px;
      border-radius: 4px;
    }
    pre {
      background: #272822;
      color: #f8f8f2;
      padding: 15px;
      border-radius: 6px;
      overflow-x: auto;
    }
    .container {
      max-width: 900px;
      margin: auto;
      background: white;
      padding: 30px;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }
    img {
      width: 100%;
      border-radius: 10px;
      margin: 20px 0;
    }
    .badge {
      display: inline-block;
      padding: 5px 10px;
      background: #27ae60;
      color: white;
      border-radius: 5px;
      font-size: 14px;
    }
  </style>
</head>

<body>
<div class="container">

<h1>🚀 Few-shot Learning with Prototypical Networks (ProtoNet)</h1>

<p>
This project implements <b>Prototypical Networks (ProtoNet)</b>, a powerful method for 
<b>few-shot learning</b>, where a model can classify data using only a few examples per class.
</p>

<div class="badge">Test Accuracy: ~97.46% 🔥</div>

<hr>

<h2>🧠 Key Idea</h2>

<ul>
  <li>Learn a meaningful <b>embedding space</b></li>
  <li>Compute a <b>prototype (mean vector)</b> for each class</li>
  <li>Classify by selecting the <b>nearest prototype</b></li>
</ul>

<p><b>Pipeline:</b></p>

<pre>
Support set → compute prototypes  
Query → compare distances → predict class
</pre>

<p>
Instead of learning a fixed classifier, ProtoNet learns how to compare samples in an embedding space.
</p>

<hr>

<h2>📦 Dataset</h2>

<ul>
  <li><b>Dataset:</b> Omniglot</li>
  <li>1623 character classes</li>
  <li>20 samples per class</li>
</ul>

<p>
Omniglot is widely used for few-shot learning because it contains many classes with very few samples.
</p>

<hr>

<h2>🏗️ Model Architecture</h2>

<ul>
  <li>4-layer CNN encoder</li>
  <li>Each block: Conv → BatchNorm → ReLU → MaxPool</li>
  <li>Output: embedding vector</li>
</ul>

<p>
The network learns to map images into a space where samples from the same class cluster together.
</p>

<hr>

<h2>🔁 Training Strategy</h2>

<ul>
  <li>Training is done in <b>episodes</b></li>
  <li>Each episode simulates a <b>N-way K-shot task</b></li>
</ul>

<pre>
Example: 5-way 5-shot
→ 5 classes, 5 samples per class
</pre>

<p><b>Training Progress:</b></p>

<pre>
Episode 0   → Accuracy: 0.93  
Episode 200 → Accuracy: 1.00  
Episode 800 → Accuracy: 1.00  
</pre>

<p>
The model converges quickly and achieves near-perfect training accuracy.
</p>

<hr>

<h2>🧪 Evaluation</h2>

<pre>
Test Accuracy: 0.9746 (~97.46%)
</pre>

<p><b>Comparison with benchmark:</b></p>

<ul>
  <li>ProtoNet paper: ~99.7%</li>
  <li>This implementation: ~97.46%</li>
</ul>

<p>
This is a strong result for a simple implementation without heavy tuning.
</p>

<hr>

<h2>🖼️ Episode Visualization</h2>

<img src="image.png" alt="ProtoNet Episode Visualization">

<p>
Each row represents a class:
</p>

<ul>
  <li><b>S0 → S4:</b> Support samples</li>
  <li><b>Q:</b> Query sample</li>
</ul>

<p><b>How it works:</b></p>

<ul>
  <li>Compute prototype from support samples</li>
  <li>Compare query embedding to all prototypes</li>
  <li>Select nearest class</li>
</ul>

<p><b>Observation:</b></p>

<ul>
  <li>Query samples visually match their support set</li>
  <li>Classes are clearly separated</li>
</ul>

<p>
This demonstrates that the model has learned a meaningful embedding space.
</p>

<hr>

<h2>📌 Results Analysis</h2>

<ul>
  <li>✅ High accuracy (~97%)</li>
  <li>✅ Fast convergence</li>
  <li>✅ Clear class separation in embedding space</li>
  <li>⚠️ Slight gap compared to paper (~99%)</li>
</ul>

<hr>

<h2>🚀 Future Improvements</h2>

<ul>
  <li>Normalize embeddings (L2 normalization)</li>
  <li>Use deeper backbone (ResNet)</li>
  <li>Train with higher N-way tasks (e.g., 20-way)</li>
  <li>Apply to more complex datasets (miniImageNet)</li>
</ul>

<hr>

<h2>🎯 Conclusion</h2>

<p>
✔ Successfully implemented Prototypical Networks from scratch  
</p>

<p>
✔ Learned a robust embedding space for few-shot classification  
</p>

<p>
🔥 Achieved strong performance close to state-of-the-art  
</p>

</div>
</body>
</html>