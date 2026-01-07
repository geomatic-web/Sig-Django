# SIG Web Cadastral avec Django & GeoDjango (lien de la playliste youtube: https://youtube.com/playlist?list=PL2UHzWnHK66R6A8-i1IAMN6APx6YDgoTa&si=8JfnZcKlRDjUL3Kj)

Projet de **SIG Web cadastral** développé avec **Django, GeoDjango, PostGIS et Leaflet**.  
Il permet la **visualisation des parcelles**, la **recherche**, le **filtrage** et la **gestion via l’admin Django**.

---

## 1. Fonctionnalités

- Cartographie des parcelles (polygones)
- API GeoJSON avec Django REST Framework
- Recherche de parcelle (numéro / propriétaire)
- Filtrage par usage
- Interface cartographique Leaflet
- Interface d’administration Django
- Authentification (connexion)

---

## 2. Prérequis

### 2.1. Librairies SIG (obligatoire pour GeoDjango)

Sous Windows :

Télécharger Installer OSGeo4W depuis https://download.osgeo.org/osgeo4w/v2/osgeo4w-setup.exe

##Cocher :
GDAL,GEOS,PROJ
Avant de lancer le projet, assurez-vous d’avoir :

### 2.2. PostgreSQL + PostGIS

Installer postgresql ensuite postgis avec le stackbuilder

Activer l'Extension PostGIS

CREATE DATABASE sig_db;
\c django
CREATE EXTENSION *postgis;*

### 2.3. Python 

- Python **3.11 ou 3.12**

```bash
python --version;
```

## 3. Installation du projet

**Étape 1 — Cloner le dépôt depuis GITHUBE**

```
git clone [https://github.com/geomatic-web/Sig-Django.git](https://github.com/geomatic-web/sig-cadastral-geodjango-v1.git)
cd Sig-Django
```

**Étape 2 — Créer et activer l’environnement virtuel**

python -m venv env
env\Scripts\activate | Vous devez voir :(env) en vert

**Étape 3 — Installer les dépendances**
pip install -r requirements.txt

### 4. Configuration

**Étape 4 — Fichier settings.py**

```
Modifier cette partie du fichier settings.py pour correspondre à votre base de données :

DATABASES = {
    'default': {
        'ENGINE': 'django.contrib.gis.db.backends.postgis',
        'NAME': 'django',     # Exemple : 'sig_education'
        'USER': 'postgres',
        'PASSWORD': 'postgres',
        'HOST': 'localhost',          # ou l’adresse du serveur
        'PORT': '5432',               # port PostgreSQL par défaut
    }
}
```

### 5. Base de données

**Étape 6 — Migrations**

```
python manage.py makemigrations
python manage.py migrate

```

**Étape 7 — Créer un super utilisateur**
python manage.py createsuperuser

#   6. Lancement du projet

```
python manage.py runserver
Accès :
🌐 Application :http://127.0.0.1:8000/
🔐 Admin Django :http://127.0.0.1:8000/admin
🔐 Admin Django :http://127.0.0.1:8000/api/parcelles/
```

#  7. Structure du projet

```
Sig-Django/
│
├── cartographie/
├── config/
├── templates/
├── static/
├── manage.py
├── requirements.txt
├── README.md
├── .gitignore
```
