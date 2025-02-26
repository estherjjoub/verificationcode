<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vérification du Code</title>
    <style>
        /* Mise en page générale avec un fond doré */
        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(45deg, #f0c27b, #4b1248); /* Dégradé doré */
            margin: 0;
            padding: 0;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .container {
            background-color: white;
            padding: 40px;
            border-radius: 10px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
            text-align: center;
            max-width: 400px;
            width: 100%;
            box-sizing: border-box;  /* Assure que la largeur totale ne dépasse pas 100% */
        }

        h1 {
            font-size: 24px;
            margin-bottom: 20px;
            color: #333;
        }

        input {
            width: 100%;
            padding: 15px;
            font-size: 18px;
            border: 2px solid #ccc;
            border-radius: 5px;
            margin-bottom: 20px;
            box-sizing: border-box;  /* Assure que la largeur prend en compte les bordures */
            transition: border-color 0.3s ease-in-out;
        }

        input:focus {
            border-color: #5e81f4;
            outline: none;
        }

        button {
            width: 100%;
            padding: 15px;
            font-size: 18px;
            background-color: #5e81f4;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        button:hover {
            background-color: #3a63d3;
        }

        #message {
            margin-top: 15px;
            font-size: 16px;
        }

        .success {
            color: green;
        }

        .error {
            color: red;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Veuillez entrer le code :</h1>
        <form id="codeForm">
            <input type="text" id="codeInput" placeholder="Entrez le code" required>
            <button type="submit">Vérifier</button>
        </form>
        <p id="message"></p>
    </div>

    <script>
        document.getElementById("codeForm").addEventListener("submit", function(event) {
            event.preventDefault();  // Empêche le comportement par défaut (rechargement de la page)
            
            const enteredCode = document.getElementById("codeInput").value.trim(); // Récupère la valeur du champ de saisie
            const message = document.getElementById("message"); // Le paragraphe qui affichera le message
            
            // Vérifie si le code entré est correct
            if (enteredCode === "421") {
                message.textContent = "Code bon. Dirigez-vous vers la marmotte grandeur nature...";
                message.className = "success";  // Applique la classe 'success' pour colorer le message en vert
            } else {
                message.textContent = "Code faux. Veuillez contacter un animateur si besoin d'aide.";
                message.className = "error";  // Applique la classe 'error' pour colorer le message en rouge
            }
        });
    </script>
</body>
</html>
