<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>README - Gyro-Bricks: Special Edition</title>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700&display=swap" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Share+Tech+Mono&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary-glow-color: #00f9ff;
            --background-dark: #0d001a;
            --ui-border-color: rgba(0, 249, 255, 0.5);
        }

        html, body {
            margin: 0;
            padding: 0;
            background: var(--background-dark);
            color: #e0f7fa;
            font-family: 'Share Tech Mono', monospace;
            line-height: 1.7;
        }
        
        body::before {
            content: '';
            position: fixed;
            top: 0; left: 0;
            width: 100%; height: 100%;
            background: linear-gradient(135deg, #1a0033, var(--background-dark));
            z-index: -2;
        }

        @keyframes move-twinkle-back {
            from {background-position:0 0;}
            to {background-position:-10000px 5000px;}
        }

        #stars {
            position: fixed;
            top: 0; left: 0;
            width: 100%; height: 100%;
            z-index: -1;
            background: transparent url('data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABAAAAAQCAYAAAAf8/9hAAAAAXNSR0IArs4c6QAAAHBJREFUOE+tkssJwDAUQ++dGChgI2AhOrCKOoR+dDRCoJN01BJo2AowUMFA9A0qgAqO7j99iN8/3YdM//c3iP8A8B8o4AEi8A/E/wB4D4xYAEi8BvwL4D8gVoAEi8AvEN8A8BCoAhIsgHwD+D8QqwASLIAvAMsX4C4gVoAEi6AL8G4i1gAkWQAfgf4N4DBKjS/k9f5cAAAAASUVORK5CYII=') repeat;
            animation: move-twinkle-back 200s linear infinite;
        }
        
        .container {
            max-width: 900px;
            margin: 2em auto;
            padding: 2em 3em;
            background: rgba(20, 5, 40, 0.75);
            backdrop-filter: blur(12px) saturate(150%);
            border: 2px solid var(--ui-border-color);
            box-shadow: 0 0 35px rgba(0, 249, 255, 0.4);
            border-radius: 10px;
        }

        @keyframes flicker {
            0%, 18%, 22%, 25%, 53%, 57%, 100% {
                text-shadow:
                0 0 5px rgba(0, 249, 255, 0.7),
                0 0 15px rgba(0, 249, 255, 0.7),
                0 0 30px var(--primary-glow-color);
            }
            20%, 24%, 55% { text-shadow: none; }
        }

        h1, h2 {
            font-family: 'Orbitron', sans-serif;
            color: var(--primary-glow-color);
            text-align: center;
        }

        h1 {
            font-size: 2.8em;
            margin-bottom: 0.2em;
            animation: flicker 4s infinite alternate;
        }

        h2 {
            font-size: 1.8em;
            margin-top: 1.8em;
            margin-bottom: 1em;
            border-bottom: 1px solid var(--ui-border-color);
            padding-bottom: 0.5em;
            text-align: left;
        }

        p, li {
            font-size: 1.1em;
        }

        a {
            color: var(--primary-glow-color);
            text-decoration: none;
            font-weight: bold;
            transition: all 0.3s ease;
        }

        a:hover {
            text-decoration: underline;
            text-shadow: 0 0 8px var(--primary-glow-color);
        }

        blockquote {
            border-left: 4px solid var(--primary-glow-color);
            padding-left: 1.5em;
            margin: 1.5em 0;
            font-style: italic;
            color: #c0d8e0;
        }

        .game-image {
            max-width: 100%;
            height: auto;
            border-radius: 8px;
            border: 2px solid var(--ui-border-color);
            box-shadow: 0 0 15px rgba(0, 249, 255, 0.3);
            display: block;
            margin: 1em auto;
        }
        
        .image-caption {
            text-align: center;
            font-style: italic;
            font-size: 0.9em;
            color: #aaa;
        }
        
        .play-button-container {
            text-align: center;
            margin: 2em 0;
        }

        .play-button {
            display: inline-block;
            background: linear-gradient(45deg, var(--primary-glow-color), #00aaff);
            border: none;
            padding: 15px 35px;
            font-family: 'Orbitron', sans-serif;
            font-size: 1.3em;
            color: var(--background-dark);
            border-radius: 5px;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 0 15px rgba(0, 249, 255, 0.5);
            text-decoration: none;
        }

        .play-button:hover {
            box-shadow: 0 0 30px rgba(0, 249, 255, 0.8);
            transform: translateY(-3px) scale(1.05);
            text-decoration: none;
        }
        
        ul {
            list-style: none;
            padding-left: 0;
        }

        ul li {
            padding-left: 1.5em;
            position: relative;
            margin-bottom: 0.5em;
        }

        ul li::before {
            content: '🌀';
            position: absolute;
            left: 0;
            color: var(--primary-glow-color);
            text-shadow: 0 0 5px var(--primary-glow-color);
        }
        
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 1.5em;
            box-shadow: 0 0 15px rgba(0, 249, 255, 0.2);
        }

        th, td {
            padding: 12px 15px;
            text-align: left;
            border: 1px solid var(--ui-border-color);
        }
        
        thead {
            background: rgba(0, 249, 255, 0.1);
        }

        th {
            font-family: 'Orbitron', sans-serif;
            font-size: 1.1em;
            color: var(--primary-glow-color);
        }

        code {
            background-color: rgba(0, 249, 255, 0.1);
            padding: 0.2em 0.4em;
            border-radius: 3px;
            font-family: 'Share Tech Mono', monospace;
        }
        
        pre {
            background-color: rgba(0, 10, 20, 0.8);
            border: 1px solid var(--ui-border-color);
            border-radius: 5px;
            padding: 1em;
            overflow-x: auto;
        }
        
        pre code {
            background: none;
            padding: 0;
        }

        @media (max-width: 768px) {
            .container {
                margin: 1em;
                padding: 1.5em;
            }
            h1 { font-size: 2em; }
            h2 { font-size: 1.5em; }
            p, li { font-size: 1em; }
        }
    </style>
</head>
<body>

    <div id="stars"></div>

    <div class="container">
        <h1>Gyro-Bricks: Special Edition</h1>
        <blockquote>
            <p>Le Casse-Briques. Réinventé. En 360 Degrés.</p>
        </blockquote>
        
        <img src="URL_DE_VOTRE_GIF_OU_SCREENSHOT.gif" alt="Gameplay de Gyro-Bricks" class="game-image">
        <p class="image-caption">Il est fortement recommandé de remplacer cette image par une capture d'écran ou un GIF animé de votre jeu !</p>

        <div class="play-button-container">
            <a href="URL_DU_JEU_EN_LIGNE" class="play-button"><strong>Jouer à Gyro-Bricks Maintenant ! »</strong></a>
        </div>

        <h2 id="a-propos">À Propos du Jeu</h2>
        <p>
            Le principe est familier : un paddle, une balle, et des briques à détruire. Mais la révolution est dans l'arène. Au lieu d'un simple mouvement horizontal, vous contrôlez votre paddle sur un périmètre circulaire complet, protégeant le cœur d'un réacteur contre des vagues de briques de plus en plus menaçantes.
        </p>
        <p>
            Ce gameplay unique crée des trajectoires imprévisibles, des réactions en chaîne explosives et demande une stratégie totalement nouvelle.
        </p>

        <h2 id="caracteristiques">Caractéristiques Principales</h2>
        <ul>
            <li>🌀 <strong>Arène Dynamique à 360° :</strong> Anticipez des rebonds complexes et couvrez tous les angles pour survivre.</li>
            <li>🎨 <strong>Esthétique Rétro-Futuriste :</strong> Plongez dans une ambiance néon-lumineuse inspirée de la science-fiction des années 80, avec une bande-son techno entraînante.</li>
            <li>🚀 <strong>Système de Pouvoirs Stratégiques :</strong> Collectez du <strong>mana</strong> et déchaînez des capacités dévastatrices comme des <strong>Explosions</strong>, des <strong>Super Coups</strong> ou l'<strong>Attraction de la Balle</strong>.</li>
            <li>🧱 <strong>Des Briques aux Effets Uniques :</strong> Affrontez des briques <strong>Tireuses</strong>, <strong>Mobiles</strong>, <strong>Régénératrices</strong> ou encore <strong>de Chaos</strong>.</li>
            <li>🏆 <strong>Plus de 100 Succès :</strong> Des défis simples aux exploits légendaires, prouvez votre maîtrise du jeu.</li>
            <li>📊 <strong>Statistiques Détaillées :</strong> Suivez vos performances, vos meilleurs scores et votre progression.</li>
            <li>📱 <strong>Multi-plateforme :</strong> Jouez avec précision sur ordinateur (souris/clavier) ou en déplacement grâce à des commandes tactiles optimisées.</li>
        </ul>

        <h2 id="modes-de-jeu">Modes de Jeu</h2>
        <ol>
            <li><strong>Mode Normal :</strong> La campagne principale. Progressez à travers des niveaux de difficulté croissante et affrontez des boss redoutables tous les cinq niveaux.</li>
            <li><strong>Mode Boss Fight :</strong> L'épreuve d'habileté pure. Plus de briques, juste vous contre des boss titanesques dans des combats chronométrés.</li>
            <li><strong>Mode Survie (Faille Temporelle) :</strong> Survivez le plus longtemps possible face à des vagues de briques infinies tandis que l'arène se rétrécit inexorablement.</li>
            <li><strong>Mode Puzzle :</strong> Un défi cérébral. Avec un seul lancer, trouvez la trajectoire parfaite pour atteindre la cible en un minimum de rebonds.</li>
        </ol>

        <h2 id="comment-jouer">Comment Jouer</h2>
        <h3>Jouer en Ligne</h3>
        <p>La manière la plus simple de jouer est de se rendre sur le lien suivant :</p>
        <p><strong><a href="URL_DU_JEU_EN_LIGNE">Jouer à Gyro-Bricks</a></strong><br>
        <em>(Remplacez ce lien par l'URL où vous hébergez le jeu, par exemple votre lien GitHub Pages)</em></p>

        <h3>Jouer Localement</h3>
        <p>Si vous souhaitez exécuter le jeu sur votre propre machine :</p>
        <ol>
            <li>Clonez ce dépôt :
                <pre><code>git clone https://github.com/VOTRE_NOM_UTILISATEUR/VOTRE_DEPOT.git</code></pre>
            </li>
            <li>Naviguez dans le dossier du projet :
                <pre><code>cd VOTRE_DEPOT</code></pre>
            </li>
            <li>Ouvrez le fichier <code>BrickBreaker360_test.html</code> (ou <code>index.html</code> si vous l'avez renommé) directement dans votre navigateur web.</li>
        </ol>

        <h2 id="commandes">Commandes</h2>
        <table>
            <thead>
                <tr>
                    <th>Action</th>
                    <th>Commande Souris/Clavier</th>
                    <th>Commande Tactile (Paysage)</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td><strong>Déplacer le Paddle</strong></td>
                    <td>Mouvement de la souris</td>
                    <td>Glisser sur la <strong>zone extérieure droite</strong> de l'écran</td>
                </tr>
                <tr>
                    <td><strong>Lancer la Balle / Pouvoir 1</strong></td>
                    <td>Clic Gauche / Espace</td>
                    <td>Appuyer sur la <strong>zone intérieure droite</strong> de l'écran</td>
                </tr>
                <tr>
                    <td><strong>Pouvoir 2</strong></td>
                    <td>Clic Droit / Entrée</td>
                    <td>Appuyer sur le <strong>deuxième bouton de pouvoir</strong> à gauche</td>
                </tr>
                <tr>
                    <td><strong>Changer la Vitesse</strong></td>
                    <td>Molette / Flèches Haut & Bas</td>
                    <td>Utiliser le <strong>slider de vitesse</strong> en bas à gauche</td>
                </tr>
                <tr>
                    <td><strong>Activer Pouvoir 1 (mobile)</strong></td>
                    <td>-</td>
                    <td>Appuyer sur le <strong>premier bouton de pouvoir</strong> à gauche</td>
                </tr>
            </tbody>
        </table>

        <h2 id="technologies">Technologies Utilisées</h2>
        <p>Ce jeu est construit entièrement avec des technologies web standard, sans aucune dépendance externe (framework).</p>
        <ul>
            <li>HTML5</li>
            <li>CSS3</li>
            <li>JavaScript (ES6+)</li>
        </ul>

        <h2 id="credits">Crédits et Remerciements</h2>
        <ul>
            <li><strong>Musiques :</strong> Les musiques libres de droits proviennent de la chaîne YouTube <strong>Infraction & NCM</strong>.</li>
            <li><strong>Effets Sonores :</strong> Les effets sonores ont été téléchargés depuis <a href="https://pixabay.com/fr/sound-effects/" target="_blank" rel="noopener noreferrer">Pixabay</a>.</li>
            <li><strong>Développement :</strong> Ce jeu a été développé par <strong>HMZ</strong> avec l'aide des outils d'intelligence artificielle <strong>Gemini Pro (Google)</strong> et <strong>Kimi K2 (Moonshot AI)</strong>.</li>
        </ul>

        <h2 id="licence">Licence</h2>
        <p>Ce projet est distribué sous la licence MIT. Voir le fichier <code>LICENSE.txt</code> pour plus de détails.<br>
        <em>(Note : vous devrez choisir une licence et créer le fichier correspondant. La licence MIT est un bon choix pour la permissivité).</em></p>
    </div>

</body>
</html>
