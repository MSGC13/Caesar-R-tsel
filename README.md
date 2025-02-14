<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Caesar-Rätsel</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #2b1b0f;
            color: white;
            padding: 20px;
        }
        h1 {
            color: gold;
        }
        .encrypted-text {
            font-size: 20px;
            margin-bottom: 20px;
            background: rgba(255, 255, 255, 0.1);
            padding: 10px;
            border-radius: 5px;
            display: inline-block;
        }
        .alphabet {
            margin: 20px 0;
            font-size: 18px;
            background: rgba(255, 255, 255, 0.1);
            padding: 10px;
            border-radius: 5px;
            display: inline-block;
        }
        .input-container {
            display: flex;
            flex-direction: column;
            align-items: center;
            margin-top: 20px;
        }
        .input-row {
            display: flex;
            justify-content: center;
            margin: 5px;
        }
        .input-row input {
            width: 40px;
            height: 40px;
            text-align: center;
            font-size: 20px;
            text-transform: uppercase;
            margin: 2px;
        }
        button {
            margin-top: 20px;
            padding: 10px 20px;
            font-size: 16px;
            cursor: pointer;
            background: gold;
            color: black;
            border: none;
            border-radius: 5px;
        }
        #result {
            margin-top: 20px;
            font-size: 18px;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <h1>Caesar-Rätsel</h1>
    <p>Nur wer die geheime Sprache der Hexen versteht, wird den nächsten Hinweis finden.</p>
    
    <div class="encrypted-text">
        IROJH DEM IXQNHOQ DER NULVWDOOH, HINAUS DXV GHV GRUIHV PLWWH. GRUW WO KROC UND RÄDER UXKQ, ZLUG VLFK GDV NÄCHSTE JHKHLPQLV AUFTUN.
    </div>
    
    <div class="alphabet">
        A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
    </div>
    
    <div class="input-container">
        <div class="input-row">
            <input type="text" maxlength="1"> <input type="text" maxlength="1"> <input type="text" maxlength="1"> <b>DEM</b> 
            <input type="text" maxlength="1"> <input type="text" maxlength="1"> <input type="text" maxlength="1"> <input type="text" maxlength="1"> <b>DER</b>
            <input type="text" maxlength="1"> <input type="text" maxlength="1"> <input type="text" maxlength="1"> <input type="text" maxlength="1"> <input type="text" maxlength="1">
        </div>
        <div class="input-row">
            <b>HINAUS</b> <input type="text" maxlength="1"> <input type="text" maxlength="1"> <input type="text" maxlength="1"> <input type="text" maxlength="1"> <input type="text" maxlength="1">
        </div>
        <div class="input-row">
            <b>WO</b> <input type="text" maxlength="1"> <b>UND RÄDER</b> <input type="text" maxlength="1"> <input type="text" maxlength="1"> <input type="text" maxlength="1"> <b>NÄCHSTE</b>
            <input type="text" maxlength="1"> <input type="text" maxlength="1"> <input type="text" maxlength="1"> <b>AUFTUN</b>
        </div>
    </div>
    
    <button onclick="checkSolution()">Prüfen</button>
    <p id="result"></p>
    
    <script>
        function checkSolution() {
            let inputs = document.querySelectorAll(".input-row input");
            let solution = "FOLGE DEM FUNKELN DER KRISTALLE, HINAUS AUS DES DORFES MITTE. DORT WO HOLZ UND RÄDER RUHN, WIRD SICH DAS NÄCHSTE GEHEIMNIS AUFTUN.".replace(/[^A-Z]/g, "");
            let userAnswer = Array.from(inputs).map(input => input.value.toUpperCase()).join("");
            
            if (userAnswer === solution) {
                document.getElementById("result").innerHTML = "✅ Richtig! Das nächste Geheimnis wird enthüllt!";
            } else {
                document.getElementById("result").innerHTML = "❌ Falsch! Versuche es erneut.";
            }
        }
    </script>
</body>
</html>
