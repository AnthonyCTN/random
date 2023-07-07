# random
we enter several choices and then it takes one at random


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aléatoire</title>
</head>
<body>

    <nav>
        <ul>
            <li><a href="application.html">Accueil</a></li>
            <li><a href="asitepresentation.html">Exercice</a></li>
        </ul>
    </nav>

    <h1>Choix Aléatoire</h1>
    <label for="inputData">Entrez vos choix :</label>
    <input type="text" id="inputData" placeholder="Saisissez un Choix">
    <button onclick="ajouterDonnee()">Ajouter</button>
    <button onclick="choisirAleatoire()">Aléatoire</button>
    <ul id="dataList"></ul>
    <p id="randomResult"></p>
  
  
  
    <script >
  var data = [];

function ajouterDonnee() {
  var inputData = document.getElementById("inputData").value;
  if (inputData !== "") {
    data.push(inputData);
    document.getElementById("inputData").value = "";
    afficherDonnees();
  }
}

function afficherDonnees() {
  var dataList = document.getElementById("dataList");
  dataList.innerHTML = "";
  for (var i = 0; i < data.length; i++) {
    var li = document.createElement("li");
    li.appendChild(document.createTextNode(data[i]));
    dataList.appendChild(li);
  }
}

function choisirAleatoire() {
  if (data.length > 0) {
    var index = Math.floor(Math.random() * data.length);
    var randomResult = document.getElementById("randomResult");
    randomResult.textContent = "Donnée choisie : " + data[index];
  } else {
    var randomResult = document.getElementById("randomResult");
    randomResult.textContent = "Aucune donnée saisie.";
  }
}

    </script>
</body>
</html>
<style>
  body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 20px;
  background-color: #292f3f;
}

.container {
  max-width: 600px;
  margin: 0 auto;
  background-color: #fff;
  padding: 20px;
  border-radius: 5px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

h1 {
  text-align: center;
  color: #007bff;
}

label,
input,
button {
  display: block;
  margin-bottom: 10px;
  width: 100%;
  box-sizing: border-box;
  color: white;
text-align: center;
}

input{
    color: #0e0f0e;
}

input[type="text"] {
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 3px;
  font-size: 14px;
}

button {
  padding: 10px;
  background-color: #0e0f0e;
  color: #fff;
  border: none;
  border-radius: 3px;
  font-size: 14px;
  cursor: pointer;
}

button:hover{
    background-color: #131313;
}

ul {
  list-style-type: none;
  padding: 0;
  margin: 0;
}

li {
  padding: 5px 0;
}

#randomResult {
  font-weight: bold;
  margin-top: 20px;
}

@media screen and (max-width: 600px) {
  .container {
    padding: 10px;
  }

  input[type="text"],
  button {
    padding: 8px;
    font-size: 12px;
  }
}
li{
    color: #fff;
}

nav {
            background-color: #292f3f;
            padding: 10px;
           
        }

        nav ul {
            list-style-type: none;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
        }

        nav li {
            margin: 0 10px;
        }

        nav a {
            color: #fff;
            text-decoration: none;
            font-size: 18px;
        }

        nav a:hover {
            color: #007bff;
        }

        p{
            color: rgb(24, 181, 13);
        }

</style>
