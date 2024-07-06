SIMPLE INVENTORY ALERT
     
     It includes a form to input the inventory level and a button to check if the inventory is low.



<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Inventory Alert</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }
        .container {
            max-width: 400px;
            margin: auto;
            padding: 20px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        .alert {
            color: red;
            font-weight: bold;
        }
        .no-alert {
            color: green;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Inventory Alert System</h1>
        <form id="inventoryForm">
            <label for="inventory">Enter Inventory Level:</label>
            <input type="number" id="inventory" name="inventory" required>
            <button type="submit">Check Inventory</button>
        </form>
        <p id="alertMessage"></p>
    </div>

    <script>
        document.getElementById('inventoryForm').addEventListener('submit', function(event) {
            event.preventDefault();
            var inventoryLevel = document.getElementById('inventory').value;
            var alertMessage = document.getElementById('alertMessage');
            var threshold = 10; // Set your low inventory threshold here

            if (inventoryLevel < threshold) {
                alertMessage.textContent = 'Warning: Inventory is low!';
                alertMessage.className = 'alert';
            } else {
                alertMessage.textContent = 'Inventory level is sufficient.';
                alertMessage.className = 'no-alert';
            }
        });
    </script>
</body>
</html>

