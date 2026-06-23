<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Inventory Management System</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:'Segoe UI',sans-serif;
}

body{
    background:#121212;
    color:#fff;
    padding:20px;
}

h1{
    text-align:center;
    color:#00bfff;
    margin-bottom:20px;
}

.dashboard{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(200px,1fr));
    gap:15px;
    margin-bottom:20px;
}

.card{
    background:#1f1f1f;
    padding:20px;
    border-radius:10px;
    text-align:center;
}

.card h2{
    color:#00bfff;
}

.form-container{
    background:#1f1f1f;
    padding:20px;
    border-radius:10px;
    margin-bottom:20px;
}

.form-container h2{
    color:#00bfff;
    margin-bottom:15px;
}

input{
    width:100%;
    padding:10px;
    margin:8px 0;
    border:none;
    border-radius:5px;
    background:#333;
    color:white;
}

button{
    background:#00bfff;
    color:white;
    border:none;
    padding:10px 20px;
    border-radius:5px;
    cursor:pointer;
    margin-top:10px;
}

button:hover{
    background:#0099cc;
}

table{
    width:100%;
    border-collapse:collapse;
    background:#1f1f1f;
}

th{
    background:#00bfff;
    padding:12px;
}

td{
    padding:12px;
    text-align:center;
    border-bottom:1px solid #333;
}

.delete-btn{
    background:red;
}

.delete-btn:hover{
    background:darkred;
}
</style>
</head>
<body>

<h1>📦 Inventory Management System</h1>

<div class="dashboard">
    <div class="card">
        <h2 id="totalProducts">0</h2>
        <p>Total Products</p>
    </div>

    <div class="card">
        <h2 id="totalStock">0</h2>
        <p>Total Stock</p>
    </div>

    <div class="card">
        <h2 id="remainingStock">0</h2>
        <p>Remaining Stock</p>
    </div>
</div>

<div class="form-container">
    <h2>Add New Product</h2>

    <input type="text" id="productName" placeholder="Product Name">

    <input type="text" id="category" placeholder="Category">

    <input type="number" id="totalQty" placeholder="Total Quantity">

    <input type="number" id="soldQty" placeholder="Sold Quantity">

    <input type="number" id="price" placeholder="Price">

    <button onclick="addProduct()">Add Product</button>
</div>

<table>
    <thead>
        <tr>
            <th>Product</th>
            <th>Category</th>
            <th>Total Stock</th>
            <th>Sold</th>
            <th>Remaining</th>
            <th>Price</th>
            <th>Action</th>
        </tr>
    </thead>

    <tbody id="inventoryTable">
    </tbody>
</table>

<script>
let products = [];

function addProduct() {

    let productName = document.getElementById("productName").value;
    let category = document.getElementById("category").value;
    let totalQty = parseInt(document.getElementById("totalQty").value);
    let soldQty = parseInt(document.getElementById("soldQty").value);
    let price = document.getElementById("price").value;

    if(productName === "" || category === "" || isNaN(totalQty) || isNaN(soldQty)){
        alert("Please fill all fields");
        return;
    }

    let remaining = totalQty - soldQty;

    let product = {
        productName,
        category,
        totalQty,
        soldQty,
        remaining,
        price
    };

    products.push(product);

    displayProducts();
    clearForm();
}

function displayProducts(){

    let table = document.getElementById("inventoryTable");
    table.innerHTML = "";

    let totalStock = 0;
    let totalRemaining = 0;

    products.forEach((product,index)=>{

        totalStock += product.totalQty;
        totalRemaining += product.remaining;

        table.innerHTML += `
        <tr>
            <td>${product.productName}</td>
            <td>${product.category}</td>
            <td>${product.totalQty}</td>
            <td>${product.soldQty}</td>
            <td>${product.remaining}</td>
            <td>₹${product.price}</td>
            <td>
                    Delete
                </button>
            </td>
        </tr>
        `;
    });

    document.getElementById("totalProducts").innerText = products.length;
    document.getElementById("totalStock").innerText = totalStock;
    document.getElementById("remainingStock").innerText = totalRemaining;
}

function deleteProduct(index){
    products.splice(index,1);
    displayProducts();
}

function clearForm(){
    document.getElementById("productName").value="";
    document.getElementById("category").value="";
    document.getElementById("totalQty").value="";
    document.getElementById("soldQty").value="";
    document.getElementById("price").value="";
}
</script>

</body>
</html>
