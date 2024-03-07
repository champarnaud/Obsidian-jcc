---
tags:
  - developpement/python/Django
---

# Installation de [Python]([https://www.python.org](https://www.python.org/)) Sur MAC OS

```
brew install python
```

Pour en faire la version par défaut, ajouter au fichier `.zprofile` pour **ZSH** `~/.bash_profile` pour **BASH**
```
export PATH=/opt/homebrew/opt/python@3.12/libexec/bin:$PATH
```

Test
```
❯ python --version
Python x.xx.x
```
# pip le gestionnaire de paquet Python

Vérifier que `pip`est installé
```
pip --version
```
Answer
> pip 24.0 from /Users/jcc/Developpement/charlotte/charlotte_site/lib/python3.12/site-packages/pip (python 3.12)


> [!info] pour éviter les conflits de différentes versions de package installés, ‘pip’ à évoluer. Il faut désormais créer des environnements virtuels séparés


# Installation de [Django]([https://www.djangoproject.com](https://www.djangoproject.com/))


## création de l'environnement virtuel

```

```

## Démarrer et arrêter  un environnement virtuel

**Démarrer**
```
source mon_venv/bin/activate
```

**Arrêter**
```
deactivate
```
## Installation de Django

Maintenant `pip`est disponible
```
pip install Django
> Collecting Django
  Downloading Django-5.0.2-py3-none-any.whl.metadata (4.1 kB)
Collecti...
```

Pour vérifier, entrer sur la console Python
```
python
Python 3.12.2 (main, Feb  6 2024, 20:19:44) [Clang 15.0.0 (clang-1500.1.0.2.5)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>>
>>> import django
>>> django.VERSION
(5, 0, 2, 'final', 0)
```

## Info sur le framework Django

> [!info] Django créé un projet dans le quel on peut créer plusieurs App

Dans le répertoire `monprojet`
```
mon_projet
|--- manage.py           # Script de management du projet
|--- mon_projet          # répertoire qui contient les outils pour mon projet
|    |--- __init__.py
|    |--- settings.py
|    |--- urls.py
|    |--- wsgi.py
|--- mon_app             # Répertoire de mon application
|    |--- __init__.py
|    |--- models.py
|    |--- views.py
|    |--- tests.py
```

## Création du projet grâce à Django

Django est livré avec un utilitaire : `django-admin`
```
django-admin startproject mon_projet
```

Cette commande va créer un répertoire avec un sous répertoire `mon_projet` contenant les fichiers :
- `settings.py` contient la configuration globale du projet, par exemple les identifiants de connexion BDD, les chemins des différentes ressources, etc.
- `urls.py` est le contrôleur frontal du projet : c'est le chef de gare qui éguillera toutes les requêtes vers les bons contrôleurs.
- `wsgi.py` est un fichier de configuration relatif au serveur qui exécutera le projet, suivant l'interface WSGI (Web Server Gateway Interface). Nous n'avons pas à nous en occuper.

  Et Le script `manage.py` qui est un outil qui nous permettra d'**exécuter des commandes utiles au sein du projet**, par exemple pour créer les tables de base de données ou [lancer le serveur de développement](https://www.formation-django.fr/framework-django/premier-projet/creation-projet-django.html#lancer-serveur-developpement).

### Pour lancer le serveur de Django

Dans le répertoire contenant le fichier `manage.py` :
```
python manage.py runserver
```

## Création de l'application grâce à Django

Avec l'utilitaire `django-admin`
```
django-admin.py startapp mon_app
```