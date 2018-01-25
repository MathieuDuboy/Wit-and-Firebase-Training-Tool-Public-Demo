# Firebase & Wit Training Tool
Un outil de gestion et d'entrainement des intentions (sur Wit.ai) & des réponses associées (sur Firebase).<br />Le but de cet outil est de se passer des fichiers Excel illisibles et non-exploitables
<table style="border:none"><tr><td>
<img src="https://github.com/MathieuDuboy/Wit-and-Firebase-Training-Tool/blob/master/Capture%20d%E2%80%99e%CC%81cran%202018-01-25%20a%CC%80%2009.50.40.png" width="100%"/></td><td> <img src="https://github.com/MathieuDuboy/Wit-and-Firebase-Training-Tool/blob/master/Capture%20d%E2%80%99e%CC%81cran%202018-01-25%20a%CC%80%2009.52.13.png" width="100%"/> </td><td><img src="https://github.com/MathieuDuboy/Wit-and-Firebase-Training-Tool/blob/master/Capture%20d%E2%80%99e%CC%81cran%202018-01-25%20a%CC%80%2009.52.40.png" width="100%"/></td></tr></table>

## Description
Cet outil est adaptable et configurable à n'importe quel projet Wit.ai & Firebase via un fichier [config.php](https://github.com/MathieuDuboy/Wit-and-Firebase-Training-Tool/blob/master/configuration/config.php) . <br />
Il permet de :
- Obtenir un petit visuel sur le nombre total d'utilisateur du Chatbot et d'autres stats (note moyenne, nombre de messages, etc)
- Ajouter une nouvelle valeur d'intention dans le Chatbot sans passer par Wit.ai ni Firebase
- Ajouter et programmer la réponse automatique du ChatBot (image, lien, texte, ...) sans passer par Firebase
- Ajouter des expressions (Vocalement ou Textuellement) dans cette nouvelle valeur d'intention pour entrainer Wit.ai
- Supprimer des expressions dans cette nouvelle intention en cas d'erreur
- Accéder directement à la console Wit.ai et la console Firebase de votre projet en 1 clic

## Pré-Requis
- Téléchargez et installez [MAMP](https://www.mamp.info/en/) (pour MAC) ou [WAMP](http://www.wampserver.com/) (pour Windows)
- Crééz une App [Wit.ai](https://wit.ai/) et récupérez le [token](https://wit.ai/docs/quickstart) de celle-ci
- Crééz un projet [Firebase](https://console.firebase.google.com/) et récupérez les identifiants sur la page principal de votre projet.

## Installation
Après avoir installé MAMP sur votre ordinateur :
- Téléchargez le [dossier .zip](https://github.com/MathieuDuboy/Wit-and-Firebase-Training-Tool/archive/master.zip) et décompréssez-le.
- Copiez le dossier décompréssé sur votre bureau et renommez-le en **Training_Tool** pour + de facilité.
- Dans MAMP, définissez ce dossier par défaut en procédant ainsi :
	- MAMP > Préférences > Web Server > Document Root > Cliquez sur l'icone dossier et selectionnez Training_Tool sur votre bureau.
- Cliquez sur OK et Relancez les serveurs (Gros bouton Vert ou Rouge)
- Le serveur est prêt. Il faut ensuite configurer le fichier dans [/configuration/config.php](https://github.com/MathieuDuboy/Wit-and-Firebase-Training-Tool/blob/master/configuration/config.php)
- Renseignez :
	- Le nom de votre projet : _Anabelle_
	- La Clé Token de votre App Wit.ai : _12312AZE123AZE23_
    - Le lien direct vers votre App Wit.ai : _https://wit.ai/mathieuduboy/XXXXX_
    - Le lien direct vers votre App Firebase : _https://console.firebase.google.com/project/XXXXXXX/database_
    - Les clés secretes issues de Firebase :
```
<script>
  // Initialize Firebase
  var config = {
    apiKey: "XXXX",
    authDomain: "XXXX.firebaseapp.com",
    databaseURL: "https://XXXX.firebaseio.com",
    projectId: "XXXX",
    storageBucket: "XXXX.appspot.com",
    messagingSenderId: "XXXX"
  };
  firebase.initializeApp(config);
</script>
```
- Tout est prêt : Ouvrez votre navigateur et dirigez-vous vers votre Dashboard à cette adresse : http://localhost:8888/index.php

## Manuel d'utilisation
**Ajouter une nouvelle valeur d'intention dans Firebase sans passer par Wit.ai**

<table><tr><td width="25%"><img src="https://github.com/MathieuDuboy/Wit-and-Firebase-Training-Tool/blob/master/Capture%20d%E2%80%99e%CC%81cran%202018-01-25%20a%CC%80%2011.26.06.png" width="100%"/>
</td><td>Sans passer par l'interface Wit.ai ni celle de Firebase, ajoutez ici une nouvelle valeur d'intention et paramétrez ensuite la réponse du ChatBot.</td></tr></table>

**Dans le menu de gauche, cliquez sur :**
- Les actions > Ajouter une valeur
ou bien depuis le Dashboard, cliquez sur :
- Nouvelle Intention dans Wit.ai et Firebase > Ajouter

**Ajouter et programmer la réponse automatique du ChatBot (image, lien, texte, ...) sans passer par Firebase**

Une fois arrivé sur la page _newintent.php_, renseignez les champs puis **Validez** :
- Nom de la valeur **(OBLIGATOIRE)**
	- Ce sera ici le nom de la valeur de l'intention dans Wit.ai mais aussi dans Firebase. Elles sont exactement les mêmes et doivent respecter ce format Bla_bla_bla (pas d'espace, pas de tirets, pas d'accents nu autres caractères spéciaux).
- Action **(OBLIGATOIRE)**
	- Renseignez ici une phrase qui résumé l'action de votre utilisateur, ce qu'il cherche à connaitre ou effectuer
- Image *Optionnel
	- Renseignez ici l'URL complet de l'image à afficher
- Lien (URL) *Optionnel
	- Renseignez ici l'URL complet du lien vers lequel envoyer l'utilisateur du ChatBot
- Catégorie *Optionnel
- Sous-Catégorie *Optionnel
- Réponse **(OBLIGATOIRE)**
	- Au format texte, elle ne doit pas dépasser 300 caractères.

**Ajouter des expressions (Vocalement ou Textuellement) dans cette nouvelle valeur d'intention pour entrainer Wit.ai**

<table><tr><td width="25%"><img src="https://github.com/MathieuDuboy/Wit-and-Firebase-Training-Tool/blob/master/Capture%20d%E2%80%99e%CC%81cran%202018-01-25%20a%CC%80%2009.52.13.png" width="100%"/>
</td><td>Efectuez ici un copié/collé de multiples expressions à ajouter à une valeur d'intention ou bien entrainez directement vocalement cette valeur d'intention en dictant à l'interface des expressions. Ce processus de création vocale est 10x plus rapide que celui effectué par Excel.</td></tr></table>

**Attention** : _l'ajout de plus de 100 expressions à la fois peut durer quelques secondes. Ne pas arreter le chargement de la page une fois l'opération lancée !_

**Pour entrainter une valeur, dirigez-vous depuis le menu de gauche sur :**
- Les actions > Ajouter des Expressions
ou bien directement depuis le Dashboard depuis :
- Ajouter des Expressions directement dans Wit.ai > Ajouter
ou alors si vous connaissez directement le nom d'une valeur d'intention, depuis le Dahsboard :
- Ajoutez dans la barre de recherche le nom de la veleur > Validez
Vous arriverez directement dans la page d'entraintement de cette valeur.

**Pour ajouter des expressions par saisie texte :**
- Remplissez vos expressions les unes sous les autres **(ATTENTION une ligne = une expression)**
- Cliquez sur **+ Ajouter** et confirmez votre envoi vers Wit.ai
- Patientez le temps du chargement

**Pour ajouter des expressions par dictée vocale :**
- Cliquez sur le petit icone Micro
- Parlez en dictant une expression
- Faites une pause d'une seconde, vous entendrez un bip vous signinfiant que vous pouvez dicter une autre expression
- Une fois la dictée terminée, vous pouvez retoucher textuellement vos expressions et Validez votre envoi vers Wit.ai
- Patientez le temps du chargement

**Supprimer des expressions dans cette nouvelle intention en cas d'erreur**

<table><tr><td width="25%"><img src="https://github.com/MathieuDuboy/Wit-and-Firebase-Training-Tool/blob/master/Capture%20d%E2%80%99e%CC%81cran%202018-01-25%20a%CC%80%2011.36.41.png" width="100%"/>
</td><td>En cas d'erreur ou d'imprécisions du Chatbot sur certaines intentions, vous pouvez ici en un clic supprimer une expression dans une valeur d'intention précise.</td></tr></table>

**Pour supprimer une expression :**
- Dirigez-vous vers la page d'entrainement d'une intention
- Dans la tableau du bas, cliquez sur l'icône X
- Validez votre choix
- Patientez le temps du chargement de la page

**Accéder directement à la console Wit.ai et la console Firebase de votre projet**

Depuis votre interface, vous pouvez accéder directement à vos consoles de vos projets Firebase et Wit.ai en cliquant sur le menu de gauche sur : <br />
-Les Apps > Aller sur Wit.ai<br />
ou bien <br />
-Les Apps > aller sur Firebase<br />


## Contacts
Pour tous renseignements ou demandes d'informations, veuillez contacter directement [mathieu.duboy@gmail.com]()
