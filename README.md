[indexed-images-to-pdf](https://dirkarnez.github.io/indexed-images-to-pdf/)
===========================================================================
### Notes
- [pdfmake](http://pdfmake.org/) does not support set page size for each page, therefore i use [PDFKit](https://pdfkit.org/) instead

### TODOs
- [x] Sortable on UI
- [ ] WebAssembly JPEG compression
  - [AntoineViau/webassembly-jpeg: Read and write jpeg with WebAssembly](https://github.com/AntoineViau/webassembly-jpeg) 
    - [Demo](https://antoineviau.com/webassembly-jpeg/index.html)
- [ ] Binarization
  - ```javascript
    function binarizeImage(imageData, threshold) {
      const data = imageData.data;
      for (let i = 0; i < data.length; i += 4) {
        // Calculate grayscale value (using a common weighted average formula)
        const grayscale = (data[i] * 0.299 + data[i + 1] * 0.587 + data[i + 2] * 0.114);
        
        // Apply global thresholding: set to black (0) or white (255)
        const color = grayscale >= threshold ? 255 : 0;
        
        data[i] = color;     // Red channel
        data[i + 1] = color; // Green channel
        data[i + 2] = color; // Blue channel
        // data[i + 3] remains the alpha channel (opacity)
      }
      return imageData;
    }
    ```
