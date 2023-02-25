# pythonanywhere

# Comment Deployer sur Python Anywhere

Voici le Lien du tutoriel sur youtube qui accompagne cette articles

Dans ce tutoriel je vais vous montrer comment deployer une application django sur pythonanywhere se deploiement se fera en deux parties:

 . La premiere partie sera deployer en utilisant le dommaine gratuite et par default que nous donne `pythonanywhere`.
 
 - La deuxiemme partie sera l'achat d'un dommaine et le connecter a notre application sur `pythonanywhere`
 
# PARTIE 1 DEPLOIEMENT AVEC DOMMAINE GRATUIT
  
  1- Creer un Compte sur pythonanywhere
  
  2- Mettre son projet sur github
  
  3- Aller dans le dashboard de pythonanywhere
  
  4- Clicker sur bash
  
  5- Cloner son project avec la commande: git clone ton_project
  
  6- Creer un environement vituel avec la commande: mkvirtualenv --python=/usr/bin/python.version_de_ton_python nom_de_ton_environement_virtuel
  
  7 Aller dans la partie web:
    Code:

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
       Virtualenv:
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
        
      Static files: 
         pour les fichier static: 
            Le URL sera	:
               /static/	
            Et le path:   
              /home/donald/ProjetDjango/static  

 

# PARTIE 2 ACHETER UN DOMMAINE ET POINTER SUR SON PROJET
    
