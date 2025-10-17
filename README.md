# Captcha Solver (Client-side OCR)

MIT-licensed, zero-backend web app that attempts to solve simple image CAPTCHAs using in-browser OCR. It reads an image from the URL query parameter, shows the original image, preprocesses it on a canvas, and extracts text using Tesseract.js.

## Overview

- Pure front-end: HTML/CSS/JS only; no server required.
- Input via query parameter: pass the captcha image using ?url=https://example.com/sample.png
- Shows:
  - Original image (from the provided URL).
  - Preprocessed version used for OCR (scaled, grayscaled, binarized).
  - Recognized text result.
- CORS handling: Automatically proxies the OCR input through images.weserv.nl to avoid cross-origin canvas taint, while keeping the original image display unproxied.
- Performance: Loads Tesseract.js on demand and aims to produce a result within ~15 seconds on typical networks.

## Setup

- Requirements: Any modern browser (desktop or mobile) with JavaScript enabled.
- Install:
  - Clone or download this repository.
  - No build step needed.

- Open:
  - Double-click index.html to open it in your browser, or serve it with a static web server.

## Usage

- Quick start:
  - Open index.html.
  - Paste a captcha image URL into the input field and click “Solve”.
  - Or pass a URL directly:
    - file:///path/to/index.html?url=https://example.com/sample.png
  - The page will display the provided captcha image, preprocess it, and show the recognized text.

- Demo:
  - Click “Use Demo” to test with a public placeholder image containing “AB12C”.

- Notes:
  - Some captcha images are intentionally resistant to OCR (distortions, noise, segmentation). Accuracy may vary.
  - If the original image fails to load, the app still attempts OCR via a proxy.
  - The OCR process uses English language data and restricts character recognition to alphanumerics to improve results.

## License

This project is licensed under the MIT License.

Copyright (c) 2025 Captcha Solver Authors

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the “Software”), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.