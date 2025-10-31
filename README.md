[indexed-images-to-pdf](https://dirkarnez.github.io/indexed-images-to-pdf/)
===========================================================================
### Notes
- [pdfmake](http://pdfmake.org/) does not support set page size for each page, therefore i use [PDFKit](https://pdfkit.org/) instead

### TODOs
- [ ] Sortable on UI (using signal.js)
  - ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Flex Container - Data-driven</title>
    <style>
    .container {
      display: flex;
      background-color: DodgerBlue;
      flex-wrap: wrap;
    }
    
    .container div {
      position: relative;
      background-color: #f1f1f1;
      margin: 10px;
      padding: 20px;
      font-size: 24px;
      cursor: pointer;
    }
    
    .button {
      position: absolute;
      top: 5px;
      right: 5px;
      background-color: #007BFF;
      color: white;
      border: none;
      border-radius: 5px;
      padding: 5px;
      cursor: pointer;
      font-size: 12px;
    }
    </style>
    </head>
    <body>
    
    <h1>Create a Flex Container</h1>
    
    <div class="controls">
      <input type="text" id="newItem" placeholder="New item text">
      <button onclick="addItem()">Add Item</button>
    </div>
    
    <div class="container" id="flexContainer"></div>
    
    <script>
    let items = ['Item 1', 'Item 2', 'Item 3', 'Item 4', 'Item 5'];
    
    function renderItems() {
      const container = document.getElementById('flexContainer');
      container.innerHTML = ''; // Clear existing items
      items.forEach((item, index) => {
        const div = document.createElement('div');
        div.textContent = item;
    
        const upButton = document.createElement('button');
        upButton.textContent = '↑';
        upButton.className = 'button';
        upButton.onclick = function(e) {
          e.stopPropagation(); // Prevent triggering item click
          moveItem(index, 'up');
        };
    
        const downButton = document.createElement('button');
        downButton.textContent = '↓';
        downButton.className = 'button';
        downButton.onclick = function(e) {
          e.stopPropagation(); // Prevent triggering item click
          moveItem(index, 'down');
        };
    
        div.appendChild(upButton);
        div.appendChild(downButton);
        div.onclick = function() { removeItem(index); };
        div.classList.add('item');
        container.appendChild(div);
      });
    }
    
    function addItem() {
      const newItemText = document.getElementById('newItem').value;
      if (newItemText.trim() === '') {
        alert('Please enter some text to add an item.');
        return;
      }
      
      items.push(newItemText); // Add new item to the array
      document.getElementById('newItem').value = ''; // Clear input
      renderItems(); // Re-render items
    }
    
    function removeItem(index) {
      items.splice(index, 1); // Remove item from the array
      renderItems(); // Re-render items
    }
    
    function moveItem(index, direction) {
      if (direction === 'up' && index > 0) {
        [items[index], items[index - 1]] = [items[index - 1], items[index]]; // Swap in the array
      } else if (direction === 'down' && index < items.length - 1) {
        [items[index], items[index + 1]] = [items[index + 1], items[index]]; // Swap in the array
      }
      renderItems(); // Re-render items
    }
    
    // Initial render
    renderItems();
    </script>
    
    </body>
    </html>
    ```
