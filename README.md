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

## Configuration Options

| Option     | Required | Description                                                                 |
|------------|----------|-----------------------------------------------------------------------------|
| `inputId`  | Yes      | ID of the textarea element containing the text to summarize                 |
| `outputId` | Yes      | ID of the element where the summary will be displayed                       |
| `sliderId` | No       | ID of the range input controlling summary length (10-90%)                   |
| `buttonId` | No       | ID of the button that triggers summarization (omit for auto-update)         |
| `licenseKey` | No    | License key to remove "Summarized by SummarizerDM" watermark                |

## How It Works

1. Splits text into sentences
2. Analyzes word frequency (focusing on words with 4+ characters)
3. Scores sentences based on important word frequency
4. Selects top sentences according to the specified percentage
5. Preserves original sentence order in the output

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
  <script src="https://cdn.jsdelivr.net/gh/Danielcosta78/summarizerdm@main/cdn/summarizerdm.js"></script>
</head>
<body>
  <textarea id="myTextarea" rows="10">Long text to summarize...</textarea>
  <div id="summaryResult"></div>
  
  <script>
    Summarizer.initialize({
      inputId: 'myTextarea',
      outputId: 'summaryResult',
      licenseKey: 'PAID_LICENSE_KEY'
    });
  </script>
</body>
</html>
```

## Support

For issues, feature requests, or enterprise solutions:
- [GitHub Repository](https://github.com/Danielcosta78/summarizerdm)
