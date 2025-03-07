<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Medicine Temperature Tracker</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #121212;
            color: white;
            text-align: center;
        }
        .container {
            width: 80%;
            margin: auto;
            padding: 20px;
        }
        .card {
            background: #1e1e1e;
            padding: 20px;
            border-radius: 10px;
            margin-bottom: 20px;
        }
        .medicine-name {
            font-size: 24px;
            font-weight: bold;
        }
        .temp-tracker {
            display: flex;
            justify-content: space-around;
            padding: 10px;
        }
        .temp-box {
            background: #333;
            padding: 15px;
            border-radius: 10px;
            width: 120px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Medicine Temperature Tracker</h1>
        <div id="medicineList"></div>
    </div>

    <script>
        const medicines = [
            { name: "Paracetamol", temp: "25°C", city: "Delhi", status: "Stable" },
            { name: "Insulin", temp: "8°C", city: "Mumbai", status: "Critical" },
            { name: "Amoxicillin", temp: "18°C", city: "Bangalore", status: "Stable" },
            { name: "Vaccine A", temp: "5°C", city: "Kolkata", status: "Sensitive" },
        ];

        function renderMedicines() {
            const medicineList = document.getElementById("medicineList");
            medicineList.innerHTML = "";
            medicines.forEach(med => {
                const medicineCard = document.createElement("div");
                medicineCard.classList.add("card");
                medicineCard.innerHTML = `
                    <div class="medicine-name">${med.name}</div>
                    <div class="temp-tracker">
                        <div class="temp-box">Temp: ${med.temp}</div>
                        <div class="temp-box">City: ${med.city}</div>
                        <div class="temp-box">Status: ${med.status}</div>
                    </div>
                `;
                medicineList.appendChild(medicineCard);
            });
        }

        renderMedicines();
    </script>
</body>
</html>
