# code-alpha-web-development-task-3
##file converter

##fileconverter.html

<!DOCTYPE html>
<html>
<head>
  <title>File Converter</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 20px;
    }

    .container {
      width: 400px;
      margin: 0 auto;
    }

    input[type="file"] {
      margin-bottom: 10px;
    }

    .output {
      border: 1px solid #ccc;
      padding: 10px;
      background-color: #f9f9f9;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>File Converter</h1>
    <input type="file" id="fileInput">
    <button onclick="convertFile()">Convert</button>
    <div class="output">
      <pre id="convertedText"></pre>
    </div>
  </div>

  <script src="script.js"></script>
</body>
</html>


##style.css

body {
  font-family: Arial, sans-serif;
  margin: 20px;
}

.container {
  width: 400px;
  margin: 0 auto;
}

input[type="file"] {
  margin-bottom: 10px;
}

.output {
  border: 1px solid #ccc;
  padding: 10px;
  background-color: #f9f9f9;
}

##script.js

function convertFile() {
  var fileInput = document.getElementById('fileInput');
  var file = fileInput.files[0];
  
  var reader = new FileReader();

  reader.onload = function(event) {
    var text = event.target.result;
    var convertedText = text.toUpperCase();
    var output = document.getElementById('convertedText');
    output.textContent = convertedText;
  };

  reader.readAsText(file);
}
