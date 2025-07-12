# SummarizerDM - Text Summarization Tool

SummarizerDM is a lightweight JavaScript library that transforms long texts into concise summaries. It's designed for easy integration via CDN and works entirely client-side.

## Features

- Adjustable summary length
- Client-side processing (no server calls)
- Easy integration via CDN
- Watermark removal with license key

## CDN Installation

Add this script to HTML:

```html
<script src="https://cdn.jsdelivr.net/gh/Danielcosta78/summarizerdm@main/cdn/summarizerdm.js"></script>
```

## Basic Usage

1. Add the required HTML elements:
```html
<textarea id="textInput">Paste your text here...</textarea>
<input type="range" id="summaryLevel" min="10" max="90" value="20" step="10">
<button id="summarizeBtn">Summarize</button>
<div id="summaryOutput"></div>
```

2. Initialize the summarizer:
```javascript
Summarizer.initialize({
  inputId: 'textInput',
  outputId: 'summaryOutput',
  sliderId: 'summaryLevel',
  buttonId: 'summarizeBtn',
  licenseKey: 'YOUR_LICENSE_KEY' // Optional
});
```

## License Options

The free version includes a "Summarized by SummarizerDM" watermark. To remove:

1. Purchase a license key from [Buy](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=X287KB44TC2PW&currency_code=USD)
2. Include it in your configuration:
```javascript
licenseKey: 'YOUR_PURCHASED_KEY'
```

## Example

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>SummarizerJS Demo</title>
  <style>
    body {
      font-family: sans-serif;
      background: #f9f9f9;
      max-width: 800px;
      margin: 40px auto;
      padding: 20px;
    }
    textarea, input[type="range"], button {
      width: 100%;
      margin-top: 10px;
      font-size: 16px;
    }
    #summaryOutput {
      margin-top: 20px;
      padding: 15px;
      background: #fff;
      border: 1px solid #ccc;
      white-space: pre-wrap;
    }
    label {
      font-weight: bold;
      margin-top: 20px;
      display: block;
    }
  </style>
</head>
<body>

  <h2>SummarizerJS – Test Page</h2>

  <label for="textInput">Enter your text:</label>
  <textarea id="textInput" rows="10" placeholder="Paste a long text here..."></textarea>

  <label for="summaryLevel">Summary level (% of original): <span id="percentLabel">20</span>%</label>
  <input type="range" id="summaryLevel" min="10" max="90" value="20" step="10" 
         oninput="document.getElementById('percentLabel').textContent = this.value">

  <button id="summarizeBtn">Summarize</button>

  <div id="summaryOutput">The summary will appear here...</div>

  <script
    src="https://cdn.jsdelivr.net/gh/Danielcosta78/summarizerdm@main/cdn/summarizerdm.js">
  </script>
  <script>
    Summarizer.initialize({
      inputId: 'textInput',
      outputId: 'summaryOutput',
      sliderId: 'summaryLevel',
      buttonId: 'summarizeBtn',
      licenseKey: 'REMOVE-WATERMAR'
    });
  </script>
</body>
</html>
```

## Support

For issues, feature requests, or enterprise solutions:
- [GitHub](https://github.com/Danielcosta78/)
