<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>README Generator</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <script src="https://cdn.jsdelivr.net/npm/marked/marked.min.js"></script>
  <style>
    body { font-family: Arial, sans-serif; margin: 0; padding: 20px; background: #f4f6f8; }
    h1 { text-align: center; }
    .container { max-width: 1100px; margin: auto; background: white; padding: 20px; border-radius: 10px; box-shadow: 0 4px 10px rgba(0,0,0,0.1); }
    input, textarea { width: 100%; margin: 10px 0; padding: 10px; border-radius: 6px; border: 1px solid #ccc; }
    button { padding: 10px 15px; border: none; border-radius: 6px; cursor: pointer; background: #007bff; color: white; font-size: 16px; }
    .grid { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; }
    pre { background: #222; color: #0f0; padding: 15px; border-radius: 6px; overflow-x: auto; height: 340px; }
    .preview { background: #fafafa; padding: 15px; border-radius: 6px; border: 1px solid #ddd; height: 340px; overflow-y: auto; }
  </style>
</head>
<body>
  <h1>💼 GitHub README Generator</h1>
  <div class="container">
    <input type="text" id="projectName" value="Student Academic Performance Prediction">
    <textarea id="tagline">🎯 Predicting student performance using machine learning for smarter academic insights.</textarea>
    <textarea id="gif">https://media.giphy.com/media/3o7aD2saalBwwftBIY/giphy.gif</textarea>
    <textarea id="description">📊 A machine learning project that predicts student performance using factors like study hours, previous scores, sleep patterns, and activities. Built using Multiple Linear Regression and deployed with Streamlit.</textarea>
    <textarea id="features">Machine Learning Model, Streamlit Web App, Real-time Prediction, Data Visualization using Plotly</textarea>
    <textarea id="installation">⚙️ 1. Clone the repository\n2. Install dependencies: pip install -r requirements.txt\n3. Run: streamlit run app.py</textarea>
    <textarea id="usage">🚀 Enter student details like study hours, sleep time, and previous scores to get real-time predictions.</textarea>
    <textarea id="author">👩‍💻 Neelima Gangone</textarea>

    <button onclick="generateReadme()">Generate README</button>

    <div class="grid">
      <div>
        <h2>Markdown</h2>
        <pre id="output"></pre>
      </div>
      <div>
        <h2>Preview</h2>
        <div class="preview" id="preview"></div>
      </div>
    </div>
  </div>

  <script>
    function generateReadme() {
      const name = document.getElementById('projectName').value;
      const tagline = document.getElementById('tagline').value;
      const gif = document.getElementById('gif').value;
      const desc = document.getElementById('description').value;
      const install = document.getElementById('installation').value;
      const usage = document.getElementById('usage').value;
      const features = document.getElementById('features').value.split(',');
      const author = document.getElementById('author').value;

      let featureList = features.map(f => `- 🔹 ${f.trim()}`).join('\n');

      const readme = `# 🚀 ${name}\n\n<p align="center">\n  <img src="${gif}" width="400" />\n</p>\n\n## 🧠 ${tagline}\n\n## 📌 Description\n${desc}\n\n## ✨ Features\n${featureList}\n\n## ⚙️ Installation\n${install}\n\n## 🚀 Usage\n${usage}\n\n## 👩‍💻 Author\n${author}`;

      document.getElementById('output').textContent = readme;
      document.getElementById('preview').innerHTML = marked.parse(readme);
    }

    window.onload = generateReadme;
  </script>
</body>
</html>
