# Temperature-Converter


<!DOCTYPE html>
<html>
<head>
    <title>Temperature Converter</title>
    <style>
        body {
            font-family: Arial, sans-serif;
        }
        .converter {
            width: 300px;
            margin: 0 auto;
            padding: 20px;
            background-color: #f3f3f3;
            border-radius: 5px;
        }
        input[type="number"] {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
        }
        select {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
        }
        button {
            width: 100%;
            padding: 10px;
            background-color: #007bff;
            color: white;
            border: none;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <div class="converter">
        <h2>Temperature Converter</h2>
        <input type="number" id="inputTemperature" placeholder="Enter temperature">
        <select id="fromUnit">
            <option value="celsius">Celsius</option>
            <option value="fahrenheit">Fahrenheit</option>
            <option value="kelvin">Kelvin</option>
        </select>
        <button onclick="convertTemperature()">Convert</button>
        <p id="result"></p>
    </div>

    <script>
        function convertTemperature() {
            const inputTemperature = parseFloat(document.getElementById("inputTemperature").value);
            const fromUnit = document.getElementById("fromUnit").value;
            const resultElement = document.getElementById("result");

            let result;
            if (fromUnit === "celsius") {
                result = convertCelsius(inputTemperature);
            } else if (fromUnit === "fahrenheit") {
                result = convertFahrenheit(inputTemperature);
            } else {
                result = convertKelvin(inputTemperature);
            }

            resultElement.textContent = `Result: ${result.toFixed(2)} ${getToUnit()}`;
        }

        function convertCelsius(celsius) {
            return celsius;
        }

        function convertFahrenheit(fahrenheit) {
            return (fahrenheit - 32) * 5/9;
        }

        function convertKelvin(kelvin) {
            return kelvin - 273.15;
        }

        function getToUnit() {
            return document.getElementById("fromUnit").value === "celsius" ? "Celsius" :
                document.getElementById("fromUnit").value === "fahrenheit" ? "Celsius" : "Fahrenheit";
        }
    </script>
</body>
</html>
