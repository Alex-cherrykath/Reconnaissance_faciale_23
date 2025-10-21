# Reconnaissance_faciale_23
ceci est un programme qui fera la reconnaissance de tous mes camarades de promo.

📋 Description du projet
Le Face Recognition System est un logiciel de reconnaissance faciale développé en Python à l’aide de la bibliothèque OpenCV.
Il permet de détecter, analyser, apprendre et reconnaître des visages à partir d’images ou d’un flux vidéo en temps réel (caméra).
Le projet illustre comment combiner la vision par ordinateur et le machine learning pour créer un système capable d’identifier des personnes à partir d’un jeu de données d’images d’entraînement.

🚀 Fonctionnalités principales
-📸 Détection de visage en temps réel via webcam ou vidéo.
-🧍‍♂️ Apprentissage des visages à partir d’un dossier d’images (dataset).
-🧠 Reconnaissance automatique des visages connus.
-🔒 Authentification simple basée sur l’identité reconnue.
-💾 Sauvegarde et gestion du modèle entraîné pour éviter un réapprentissage à chaque lancement.

🧩 Architecture du projet:
face-recognition-system/
│
├── dataset/                 # Dossier contenant les images d'entraînement
│   ├── person1/
│   │   ├── img1.jpg
│   │   └── img2.jpg
│   └── person2/
│       ├── img1.jpg
│       └── img2.jpg
│
├── trainer/                 # Modèles d'entraînement sauvegardés
│   └── face_trainer.yml
│
├── haarcascades/            # Classificateurs pour la détection de visage
│   └── haarcascade_frontalface_default.xml
│
├── src/
│   ├── capture_faces.py     # Script pour capturer des visages à partir de la webcam
│   ├── train_model.py       # Script d'entraînement du modèle
│   ├── recognize_faces.py   # Script principal pour la reconnaissance
│   └── utils.py             # Fonctions utilitaires
│
├── requirements.txt         # Dépendances Python
├── README.md                # Ce fichier
└── main.py                  # Point d'entrée principal

🧠 Technologies utilisées
Technologie	Rôle
Python 3.x	Langage principal
OpenCV	Détection et reconnaissance des visages
NumPy	Traitement numérique et manipulation de matrices
Pillow	Gestion des images
Pickle / joblib	Sérialisation des modèles
Tkinter / PyQt (optionnel)	Interface graphique

⚙️ Installation et configuration
1️⃣ Cloner le dépôt
git clone https://github.com/<votre_nom>/Reconnaissance_faciale_23.git
cd Reconnaissance_faciale_23;

2️⃣ Créer un environnement virtuel (optionnel mais recommandé)
python -m venv venv
source venv/bin/activate   # Linux / macOS
venv\Scripts\activate      # Windows

3️⃣ Installer les dépendances
pip install -r requirements.txt


Contenu du fichier requirements.txt :
opencv-python
opencv-contrib-python
numpy
pillow

📸 Utilisation du logiciel
Étape 1 : Capturer les visages
Lancer la capture des visages d’un utilisateur :
python src/capture_faces.py --name "Alexandre"
👉 Ce script :
Active la webcam.
Détecte le visage à l’aide du classificateur Haar Cascade.
Enregistre plusieurs images (≈30) du visage dans dataset/Alexandre/.

Étape 2 : Entraîner le modèle
python src/train_model.py
👉 Ce script :
Parcourt tous les dossiers du dataset.
Convertit les images en niveaux de gris.
Utilise LBPH (Local Binary Patterns Histogram) pour entraîner le modèle.
Sauvegarde le modèle entraîné dans trainer/face_trainer.yml.


Étape 3 : Reconnaissance en temps réel
python src/recognize_faces.py
👉 Ce script :
Charge le modèle entraîné.
Ouvre la webcam.
Détecte et reconnaît les visages connus.
Affiche le nom de la personne sur la vidéo.
🧮 Algorithme de reconnaissance (LBPH)
Le LBPH (Local Binary Patterns Histograms) est un algorithme efficace pour la reconnaissance faciale.
Il fonctionne en quatre étapes :
-Conversion des images en niveaux de gris.
-Calcul d’un histogramme binaire local pour chaque région du visage.
-Comparaison des histogrammes entre le visage détecté et ceux du modèle.
-Attribution de l’étiquette (nom) la plus proche.

🧰 Améliorations possibles

✅ Ajout d’une interface graphique (GUI) avec Tkinter ou PyQt.

📊 Ajout d’un système de gestion de base de données (SQLite / MySQL) pour stocker les identités.

☁️ Intégration d’un stockage cloud (Google Drive / Firebase) pour synchroniser les datasets.

🤖 Passage à des modèles deep learning (avec dlib, face_recognition ou DeepFace) pour une précision accrue.

🔔 Ajout de notifications ou d’alertes en cas de détection inconnue.

🧑‍💻 Auteurs

Développeur principal : Alexandre Cherry Kath
📧 Contact : alexandrecherrykath@gmail.com
