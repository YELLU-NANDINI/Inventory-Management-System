# Inventory-Management-System
HTML (index.html):
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Inventory Management System</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>Inventory Management System</h1>
    <div class="container">
        <div class="add-item">
            <label for="item-name">Item Name:</label>
            <input type="text" id="item-name" />
            <label for="quantity">Quantity:</label>
            <input type="number" id="quantity" />
            <button id="add-btn">Add Item</button>
        </div>
        <div class="inventory-list">
            <h2>Current Inventory:</h2>
            <ul id="item-list"></ul>
        </div>
    </div>
    <script src="script.js"></script>
</body>
</html>
JavaScript (script.js):
let inventory = [];
document.getElementById("add-btn").addEventListener("click", addItem);
function addItem() {
    const itemName = document.getElementById("item-name").value;
    const quantity = parseInt(document.getElementById("quantity").value);
    const item = { name: itemName, quantity: quantity };
    inventory.push(item);
    displayInventory();
}
function displayInventory() {
    const itemList = document.getElementById("item-list");
    itemList.innerHTML = "";
    inventory.forEach((item) => {
        const listItem = document.createElement("li");
        listItem.textContent = `${item.name} (${item.quantity} units)`;
        itemList.appendChild(listItem);
    });
}
CSS (style.css):
container {
    max-width: 800px;
    margin: 40px auto;
    padding: 20px;
    background-color: #f0f0f0;
    border: 1px solid #ddd;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}
add-item {
    margin-bottom: 20px;
}
add-item label {
    display: block;
    margin-bottom: 10px;
}
add-item input {
    width: 100%;
    padding: 10px;
    margin-bottom: 20px;
    border: 1px solid #ccc;
}
add-item button {
    background-color: #4CAF50;
    color: #fff;
    padding: 10px 20px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}
inventory-list {
    margin-top: 40px;
}
inventory-list h2 {
    margin-top: 0;
}
inventory-list ul {
    list-style: none;
    padding: 0;
    margin: 0;
}
inventory-list li {
    padding: 10px;
    border-bottom: 1px solid #ccc;
}
inventory-list li:last-child {
    border-bottom: none;
}
