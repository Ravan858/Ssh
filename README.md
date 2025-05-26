<!DOCTYPE html>
<html>
<head>
  <title>Camera Access</title>
</head>
<body>
  <h2>Camera Access Example</h2>
  <video id="camera" width="320" height="240" autoplay></video>
  <br>
  <button onclick="startCamera()">Start Camera</button>

  <script>
    function startCamera() {
      navigator.mediaDevices.getUserMedia({ video: true })
        .then(function(stream) {
          document.getElementById('camera').srcObject = stream;
        })
        .catch(function(error) {
          alert("Camera access denied or not available.");
          console.error(error);
        });
    }
  </script>
</body>
</html>
