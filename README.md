# moncv
Outils utilisés
-----------------
- Visual Studio Code
- Node.js
- GitHub
- Bootstrap
--------------------------
|   VS CODE
----------------
Installation : https://code.visualstudio.com/

Afficher Terminal : Onglet "Terminal" -> "New Terminal"

--------------------------
|   NODE.JS + BOOTSTRAP   |
--------------------------
###    INSTALLATION
    
    (Ouvrir Invite de Commande)

####    ETAPE 1 - Download and Install:

        npm install -g @vue/cli

####    ETAPE 2 - Créer le projet:

        vue create moncv

###    COMMANDES (ce déplacer dans le dossier du Projet)

-    Installer les dépendances : npm install
-    Démarrer le serveur     : npm run serve
-    Arrêter le serveur      : ctrl + c
-    Ajouter une dépendance  : npm install NOM_DEPENDANCE --save     (Ex : npm install bootstrap --save)
-    Supprimer une dépendance: npm uninstall NOM_DEPENDANCE --save   (Ex : npm uninstall query --save)

###        Dépendances à ajouter :
- npm uninstall vue --save
- npm install jquery --save
- npm install popper.js --save
- npm install bootstrap --save

####    ETAPE 3 - gitAttributes :
    Créer le fichier .gitattributes

    Coller ce code :
        # Force all line endings to be \n
        * text eol=lf

        ############################################################
        # git can corrupt binary files if they're not set to binary.
        ############################################################

        # Apple office documents are actually folders, so treat them as binary.
        *.numbers binary
        *.pages binary
        *.keynote binary

        # Image files
        *.png binary
        *.jpg binary
        *.jpeg binary
        *.gif binary
        *.webp binary
        *.ico binary

        # Movie and audio files
        *.mov binary
        *.mp4 binary
        *.mp3 binary
        *.flv binary
        *.ogg binary

        # Compression formats
        *.gz binary
        *.bz2 binary
        *.7z binary
        *.zip binary

        # Web fonts
        *.ttf binary
        *.eot binary
        *.woff binary
        *.otf binary

        # Other
        *.fla binary
        *.swf binary
        *.pdf binary

        ############################################################
        # End binary settings
        ############################################################

####    ETAPE 4 - Bootstrap :
        Fichier src/main.js remplacer par :
        ***********************************
            import $ from "jquery";
            window.$ = $;
            import "bootstrap";
            import "bootstrap/dist/css/bootstrap.min.css";

            $(document).ready(() => {
            console.log("it works!");
            });
        ************************************
####    ETAPE 5 - Fichier de style custom :
        
        Créer le fichier main.css après src
        
        Ajouter après "/boostrap.min.css"

            import './main.css';
    
####    ETAPE 6 - Bootswatch :
        https://bootswatch.com/
    
        Ajouter après le main.css (dans main.js): 
            import "bootswatch/dist/darkly/bootstrap.min.css";

--------------------------
|   GITHUB   |
--------------------------
####    ETAPE 1 - Créer compte et installer Github :
        Créer un compte sur : github.com

        Installer Github Desktop : https://desktop.github.com/

####    ETAPE 2 - Git Master :
        Commit le code sur un répertoire git
        Commit et push le code sur Github
        
####    ETAPE 3 - version de production :
        nom run build
    (un dossier dist doit se créer)

####    ETAPE 4 - Deployer un site statique sur Github
        Créer une branche GH-PAGES dans le répertoire :
           npm install push-dir --save-dev

           Ajouter dans le fichier package.json
            ********************************
            {
                ...,
                "scripts": {
                    ...,
                    "deploy": "push-dir --dir=dist --branch=gh-pages --cleanup --verbose"
                },
                ...
            }   
            ********************************
            http://usernameABC.github.io/repositoryYXZ

####    ETAPE 5 - Essai de déploiement
        git add . --all
        git commit -m
        npm run deploy

####    ETAPE 6 - Fixer le chemin static dans assets
        
        fichier vue.config.js :
            module.exports = {
                baseUrl: process.env.NODE_ENV === "production" ? "/moncv-test/" : "/"
            };

        Rebuild et deployer le site pour tester
