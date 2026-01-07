# SIG Web Cadastral avec Django & GeoDjango

Projet de **SIG Web cadastral** développé avec **Django, GeoDjango, PostGIS et Leaflet**.  
Il permet la **visualisation des parcelles**, la **recherche**, le **filtrage** et la **gestion via l’admin Django**.

---

## Fonctionnalités
- Cartographie des parcelles (polygones)
- API GeoJSON avec Django REST Framework
- Recherche de parcelle (numéro / propriétaire)
- Filtrage par usage
- Interface cartographique Leaflet
- Interface d’administration Django
- Authentification (connexion)

---

## Prérequis

Avant de lancer le projet, assurez-vous d’avoir :

#1️⃣ Python
- Python **3.11 ou 3.12**
```bash
python --version

 #2️⃣ PostgreSQL + PostGIS

PostgreSQL 14+

Extension PostGIS activée

CREATE DATABASE sig_db;
\c django
CREATE EXTENSION postgis;

#3️⃣ Librairies SIG (obligatoire pour GeoDjango)

Sous Windows :

Installer OSGeo4W

##Cocher :
GDAL,GEOS,PROJ
## Installation du projet
Étape 1 — Cloner le dépôt
git clone https://github.com/geomatic-web/Sig-Django.git
cd Sig-Django
Étape 2 — Créer et activer l’environnement virtuel
python -m venv env
env\Scripts\activate | Vous devez voir :(env) en vert
Étape 3 — Installer les dépendances
pip install -r requirements.txt

## Configuration
Étape 4 — Fichier .env

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

🗄️ Base de données
Étape 6 — Migrations
python manage.py makemigrations
python manage.py migrate
Étape 7 — Créer un super utilisateur
python manage.py createsuperuser
Lancement du projet
python manage.py runserver
Accès :
🌐 Application :http://127.0.0.1:8000/
🔐 Admin Django :http://127.0.0.1:8000/admin
🔐 Admin Django :http://127.0.0.1:8000/api/parcelles/

Structure du projet
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
