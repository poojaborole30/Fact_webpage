# Fact_webpage
This is Created a very simple web page with a single button. When the button is clicked, it should fetch a random "fact" from a public API (e.g., https://catfact.ninja/fact for cat facts, or a similar simple public API) and display it on the page. Use async/await for the API call. 
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Random Cat Fact</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 20px;
      text-align: center;
    }
    #fact {
      margin-top: 20px;
      font-size: 1.2em;
      color: #333;
    }
  </style>
</head>
<body>

  <h1>Cat Fact Generator</h1>
  <button onclick="getCatFact()">Get a Cat Fact</button>
  <div id="fact"></div>

  <script>
    async function getCatFact() {
      try {
        const response = await fetch('https://catfact.ninja/fact');
        const data = await response.json();
        document.getElementById('fact').textContent = data.fact;
      } catch (error) {
        document.getElementById('fact').textContent = 'Failed to fetch a fact. Please try again.';
        console.error(error);
      }
    }
  </script>

</body>
</html>

