Write code for a plagarism checker. Design it with Tailwind CSS. Display how much of the content is AI generated.

Output:
Here's a simple plagiarism checker that compares the input text with a predefined AI-generated text. It uses Tailwind CSS for styling. The checker calculates the percentage of AI-generated content in the input text and displays the result.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Plagiarism Checker</title>
  <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
</head>
<body class="bg-gray-100">
  <div class="container mx-auto px-4 py-8">
    <h1 class="text-3xl font-bold mb-4">Plagiarism Checker</h1>
    <div class="bg-white p-6 rounded shadow">
      <label for="inputText" class="block mb-2">Enter your text:</label>
      <textarea id="inputText" class="w-full h-48 p-2 border border-gray-300 rounded mb-4"></textarea>
      <button id="checkPlagiarism" class="bg-blue-500 text-white px-4 py-2 rounded">Check Plagiarism</button>
      <div id="result" class="mt-4"></div>
    </div>
  </div>
  <script>
    const inputText = document.getElementById("inputText");
    const checkPlagiarismButton = document.getElementById("checkPlagiarism");
    const result = document.getElementById("result");

    const aiGeneratedText = "This is an example of AI-generated text. It is designed to demonstrate the capabilities of language models.";

    function checkPlagiarism() {
      const input = inputText.value;
      const words = input.split(/\s+/);
      const aiWords = aiGeneratedText.split(/\s+/);

      let aiGeneratedCount = 0;

      words.forEach((word, index) => {
        if (aiWords[index] && word === aiWords[index]) {
          aiGeneratedCount++;
        }
      });

      const plagiarismPercentage = (aiGeneratedCount / words.length) * 100;

      result.innerHTML = `The input text contains <strong>${plagiarismPercentage.toFixed(2)}%</strong> AI-generated content.`;
    }

    checkPlagiarismButton.addEventListener("click", checkPlagiarism);
  </script>
</body>
</html>
```

This plagiarism checker compares the input text with the predefined AI-generated text word by word. It calculates the percentage of AI-generated content in the input text and displays the result. Note that this is a simple example and may not be suitable for detecting plagiarism in real-world scenarios. For more accurate plagiarism detection, you may want to use more advanced algorithms or third-party APIs.
