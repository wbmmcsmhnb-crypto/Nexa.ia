<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>NEXA - IA Web</title>
    <style>
        body {
            margin: 0;
            background: #111;
            color: white;
            font-family: Arial, sans-serif;
        }

        header {
            background: #222;
            padding: 20px;
            text-align: center;
            font-size: 22px;
            border-bottom: 1px solid #333;
        }

        .container {
            padding: 20px;
            max-width: 600px;
            margin: auto;
        }

        #chatbox {
            height: 350px;
            overflow-y: auto;
            background: #181818;
            padding: 15px;
            border-radius: 10px;
            border: 1px solid #333;
        }

        .msg {
            margin: 12px 0;
            padding: 10px;
            border-radius: 8px;
            max-width: 80%;
            line-height: 1.4;
        }

        .user {
            background: #005eff;
            margin-left: auto;
        }

        .bot {
            background: #262626;
        }

        .input-area {
            margin-top: 15px;
            display: flex;
            gap: 10px;
        }

        input {
            flex: 1;
            padding: 12px;
            border-radius: 8px;
            border: none;
            background: #222;
            color: white;
        }

        button {
            background: #005eff;
            border: none;
            padding: 12px 20px;
            border-radius: 8px;
            color: white;
            font-size: 16px;
            cursor: pointer;
        }

    </style>
</head>
<body>

<header>
    IA NEXA – Site Web
</header>

<div class="container">
    <div id="chatbox"></div>

    <div class="input-area">
        <input type="text" id="userInput" placeholder="Écris un message à NEXA…">
        <button onclick="sendMsg()">Envoyer</button>
    </div>
</div>

<script>
    function sendMsg() {
        let input = document.getElementById("userInput");
        let chatbox = document.getElementById("chatbox");

        if (input.value.trim() === "") return;

        // Affichage du message utilisateur
        chatbox.innerHTML += `<div class="msg user">${input.value}</div>`;

        // IA - réponse simulée (mini modèle JS)
        setTimeout(() => {
            let reply = genererReponseIA(input.value);
            chatbox.innerHTML += `<div class="msg bot">${reply}</div>`;
            chatbox.scrollTop = chatbox.scrollHeight;
        }, 500);

        input.value = "";
    }

    // Mini "IA" en JavaScript
    function genererReponseIA(texte) {
        texte = texte.toLowerCase();

        // Quelques réponses intelligentes
        if (texte.includes("bonjour") || texte.includes("salut")) {
            return "Salut ! Je suis NEXA, ton IA. Comment puis-je t’aider ?";
        }

        if (texte.includes("comment ça va")) {
            return "Je fonctionne parfaitement. Et toi ?";
        }

        if (texte.includes("qui es tu") || texte.includes("t'es qui")) {
            return "Je suis NEXA, une IA intégrée dans ton site web.";
        }

        if (texte.includes("tyron")) {
            return "Tyron ? Le personnage sportif et mystérieux ? Oui je le connais.";
        }

        if (texte.includes("aide")) {
            return "Bien sûr, dis-moi ce dont tu as besoin et je m'en occupe.";
        }

        // Réponse automatique par défaut
        return "Analyse ➜ " + texte + "… Intéressant. Développe un peu !";
    }
</script>

</body>
</html>
