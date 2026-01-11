
# COMMANDES GIT

# Toutes les étapes de A à Z pour un Nouveau projet :

  1/ **La toute première commande dès le lancement du projet**
         git init
    (Si on a ajouté node_modules par erreur on peut faire la commande : 
    git rm -r --cached node_modules)

  2/ **Créer un fichier .gitignore sous la racine du projet**
        Contenu par défaut : 
            node_modules/
            .env
            .env.local
            dist/
            build/
            *.log
            .DS_Store
        (Faut aussi ajouter tous les autres fichiers ou dossier de votre projet qui ne doivent pas être push sur le dépôt distant)

  3/ **Ajouter les le projet dans git poue le commiter**
         git add .

  4/ **si vous avez plusieurs comptes git, se positionner sur le bon compte où on veut push notre projet**
      # Voir quel compte est connecté dans l'IDE : 
         git config --global user.name ===> affiche le username du compte git actif
         git config --global user.email ===> affiche le useremail du compte git actif

      # Switch de compte Git avant de commit et push :
         git config user.name "Ton username du compte git souhaité"
         git config user.email "ton useremail du compte souhaité"

        (Sans --global pour que ça s'applique uniquement à ce projet)

  5/ **Créer une Repository ==> Aller dans Github et créér manuellement une repository vide**
  
  6/ **Connecter le projet local au dépôt distant créé précédemment**
         git remote add origin <url-de-votre-dépôt> 

         => url exemple : https://github.com/ton-username/ton-projet.git (le nom de la repo créée)

  7/ **Pour envoyer le projet vers le dépôt distant**
         git push -u origin master (ou main)

# Vérifier ta configuration pour voir tes dépôts distants configurés :
         git remote -v
    => Ça affichera quelque chose comme :
         origin  https://github.com/ton-username/mon-projet.git (fetch)
         origin  https://github.com/ton-username/mon-projet.git (push)


# Exemple : Pour ce projet j'ai fait ça : (mais j'ai déjà configuré des SSH Keys pour tous mes comptes GitHub pour s'auto pointer sur le bon compte pour chaque projet sans avoir à gérer le cache à chaque switch de compte)
    git init
    git add .
    git config user.name "le username de mon github de la formation"
    git config user.email "le useremail de mon github de la formation"
    git commit -m "initial commit"
    git branch -M main
    git remote add origin https://github.com/nbouzidi-stack/projet-react-01.git
    git push -u origin main
    Et pour les prochains push ce sera juste "git push"
