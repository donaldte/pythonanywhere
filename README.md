# pythonanywhere

# Comment Deployer sur Python Anywhere Une Application django

Voici le Lien du tutoriel sur youtube qui accompagne cette articles

Dans ce tutoriel je vais vous montrer comment deployer une application django sur pythonanywhere se deploiement se fera en deux parties:

 - La premiere partie sera deployer en utilisant le dommaine gratuite et par default que nous donne `pythonanywhere`.
 
 - La deuxiemme partie sera l'achat d'un dommaine et le connecter a notre application sur `pythonanywhere`
 
# PARTIE 1 DEPLOIEMENT AVEC DOMMAINE GRATUIT
  
  1- Creer un Compte sur pythonanywhere
  
  2- Mettre son projet sur github
  
  3- Aller dans le dashboard de pythonanywhere
  
  4- Clicker sur bash
  
  5- Cloner son project avec la commande: git clone ton_project
  
  6- Creer un environement vituel avec la commande: mkvirtualenv --python=/usr/bin/python.version_de_ton_python nom_de_ton_environement_virtuel
  
  7 Aller dans la partie web
    Code

      .Source code:
      /home/ton_non_utilisateur_ici/non_de_ton_projet_ici

      .Working directory:
      /home/ton_non_utilisateur_ici/

      .Click sur ce lien suivant
        WSGI configuration file:/var/www/donald_pythonanywhere_com_wsgi.py
       apres avoir clicke, le fichier wsgi.py souvre copy le code suivant et colle:
       
       ```
       
            import os
            import sys

            # add your project directory to the sys.path
            project_home = '/home/ton_nom_utilisateur/nom_de_ton_project'
            if project_home not in sys.path:
                sys.path.insert(0, project_home)

            os.chdir(project_home)
            # set environment variable to tell django where your settings.py is
            os.environ.setdefault('DJANGO_SETTINGS_MODULE', 'non_du_dossier_ou_se_trouver_ton_fichier_settins.settings')

            import django
            django.setup()

            # serve django via WSGI
            from django.core.wsgi import get_wsgi_application
            application = get_wsgi_application()
       
       ```
       Virtualenv
        Dans ce block 
        entre le nom de ton environement virtuel cree plus tot
        
      Dans le terminale:
        1- execute la commande suivante pour collecter les fichiers static:  pythonversion_de_ton_python manage.py collectstatic
        2  dans le fichier setting rassure toi que tu as le code suivant:
          ```
          STATIC_ROOT = os.path.join(BASE_DIR, "static")
          ```
          Pour les fichiers media rassure toi que que a le MEDIA_ROOT et MEDIA_URL dans le fichier settings
          Rassure toi aussi de mettre DEBUG=Fasle
        
      Static files
         pour les fichier static: 
            Le URL sera	:
               /static/	
            Et le path:   
              /home/donald/ProjetDjango/static  
              
      
      BRAVO ICI RECHAREGE TON APPLICATION DANS PYTHONANYWHERE ET TON APPLICATION SERA DISPONIBLE AU DOMAINE SUIVANT: non_utilisateur.pythonanwhere.com

 

# PARTIE 2 ACHETER UN DOMMAINE ET POINTER SUR SON PROJET

 1 Acheter le domain sur Godady
 2 Souscrire a un plan sur python anywhere pour pouvoir changer le domaine de l'application
 3 Renomer son application sur python anywhere : www.non_du_domaine.com
 4 Copier le CNAME du DNS sur python anywhere
 5 Aller sur Godady clicker sur `le domaine` pour clicker sur `manage DNS`
   - clicker sur `add/ajouter`
   - choisir CNAME puis pour le HOST mettre `www` pour le pointe/point to mettre `le CNAME que vous avez copier dans pythonanywhere` 
   - enregistrer
 6 Actualiser l'application sur python anywhere et le domaine sur Godady.
 
 Nb: Il est important de noter que la connection domaine peux prendre jusqu'a 24h pour propager le DNS a ton application, Donc sois sans crainte et patiente
 
 
     BRAVO TON APPLICATION EST DISPONIBLE SUR UN DOMAINE PERSONNALISE
     
  # Contact pour tous problemes   
  
    - Email: donaldtedom0@gmail.com
    - whatsapp: 00237691435485
  
    
 
 
    
