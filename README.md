[indexed-images-to-pdf](https://dirkarnez.github.io/indexed-images-to-pdf/)
===========================================================================
### Notes
- [pdfmake](http://pdfmake.org/) does not support set page size for each page, therefore i use [PDFKit](https://pdfkit.org/) instead

### TODOs
- [ ] Sortable on UI (using signal.js)
  - ```html
    <!DOCTYPE html>
    <html>
    <head>
    <style>
    .container {
      display: flex;
      background-color: DodgerBlue;
    }
    
    .container div {
      background-color: #f1f1f1;
      margin: 10px;
      padding: 20px;
      font-size: 24px;
    }
    </style>
    </head>
    <body>
    
    <h1>Create a Flex Container</h1>
    
    <div class="container">
      <div>Item 1</div>
      <div>Item 2</div>
      <div>Item 3</div>  
      <div>Item 4</div>
      <div>Item 5</div>
    </div>
    
    </body>
    </html>
    ```
