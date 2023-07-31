# voice_to_text

<!DOCTYPE html>

<html>
  
  <head>
    
    <title>Speech Recognition</title>
    
  </head>
  
  <body>
    
    <div>
    
      <button onclick="startRecognition()">Start Recognition</button>
      
      <button onclick="stopRecognition()">Stop Recognition</button>
      
    </div>
    
    <div>
    
      <textarea id="output"></textarea>
      
    </div>
    
    <script>
    
      const output = document.getElementById('output');
      
      const SpeechRecognition = window.SpeechRecognition || window.webkitSpeechRecognition;
      
      const recognition = new SpeechRecognition();
      
      recognition.lang = 'en-US';
      
      recognition.interimResults = true;
      
      recognition.onresult = function(event) {
      
        const transcript = event.results[event.results.length - 1][0].transcript;
        
        output.value += transcript;
        
      }
      
      function startRecognition() {
      
        recognition.start();
        
      }
      
      function stopRecognition() {
      
        recognition.stop();
        
      }
      
    </script>
    
  </body>
  
</html>

