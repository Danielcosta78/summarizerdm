# SummarizerDM - Text Summarization Tool

SummarizerDM is a lightweight JavaScript library that transforms long texts into concise summaries. It's designed for easy integration via CDN and works entirely client-side.

## Features

- Simple text summarization algorithm
- Adjustable summary length
- Client-side processing (no server calls)
- Easy integration via CDN
- Watermark removal with license key

## CDN Installation

Add this script to your HTML file's `<head>` section:

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

1. Purchase a license key from [our website](#)
2. Include it in your configuration:
```javascript
licenseKey: 'YOUR_PURCHASED_KEY'
```

## Example

```html
<!DOCTYPE html>
<html>
<head>
  <title>My Summarization App</title>
  <style>
    /* Recommended styling for optimal UX */
    textarea, #summaryResult {
      width: 100%;
      padding: 12px;
      border: 1px solid #ddd;
      border-radius: 4px;
      font-family: sans-serif;
    }
    #summaryResult {
      background: #f9f9f9;
      margin-top: 20px;
      min-height: 100px;
    }
    .controls {
      margin: 15px 0;
      display: flex;
      gap: 15px;
      align-items: center;
    }
  </style>
</head>
<body>
  <h1>Document Summarizer</h1>
  
  <textarea id="myTextarea" rows="10" placeholder="Paste your article or document here...">
The quick brown fox jumps over the lazy dog. According to recent studies, foxes demonstrate remarkable adaptability in urban environments. Canine behavior experts note dogs often underestimate fox intelligence. This dynamic illustrates classic predator-prey relationships in modern ecosystems.
  </textarea>
  
  <div class="controls">
    <button id="summarizeBtn">Generate Summary</button>
    <label>
      Detail: 
      <input type="range" id="detailLevel" min="10" max="90" value="50">
      <span id="percentValue">50%</span>
    </label>
  </div>
  
  <div id="summaryResult"></div>

  <script src="https://cdn.jsdelivr.net/gh/Danielcosta78/summarizerdm@main/cdn/summarizerdm.min.js"></script>
  <script>
    // Initialize with advanced configuration
    Summarizer.initialize({
      inputId: 'myTextarea',
      outputId: 'summaryResult',
      sliderId: 'detailLevel',
      buttonId: 'summarizeBtn',
  </script>
</body>
</html>
```

## Support

For issues, feature requests, or enterprise solutions:
- [GitHub Repository](https://github.com/Danielcosta78/summarizerdm)
