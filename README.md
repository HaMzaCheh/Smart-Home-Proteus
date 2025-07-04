# 🏠 Simulation d'une Maison Intelligente avec Proteus

Ce projet propose une **simulation complète d’un système de maison intelligente** réalisée avec **Proteus**.  
Il met en œuvre une architecture maître-esclave basée sur des microcontrôleurs AVR (ATmega32) permettant de gérer efficacement l’authentification, le contrôle des appareils domestiques, et la régulation de la température.

---

## ✨ Fonctionnalités principales

- 🔐 **Authentification sécurisée** avec deux profils utilisateurs :  
  - **Administrateur** : contrôle total  
  - **Invité** : accès limité  
- ⏳ **Gestion automatique des sessions** : déconnexion après période d’inactivité pour plus de sécurité  
- 💡 **Contrôle des lumières** dans quatre pièces distinctes  
- 📺 **Gestion de la télévision** : allumer/éteindre via menu  
- ❄️ **Contrôle intelligent de la climatisation** avec régulation automatique de la température grâce à un capteur intégré  
- 🖥️ **Interface utilisateur intuitive** via écran LCD 20x4 et clavier matriciel pour une navigation fluide  
- 🔄 **Communication SPI** fiable entre le contrôleur maître (interface) et le contrôleur esclave (exécution)  

---

## 📋 Prérequis techniques

Avant de lancer la simulation, assurez-vous de disposer de :

- **Proteus 8.9 ou version supérieure** (logiciel de simulation électronique)  
- **Compilateur AVR GCC** (pour compiler/modifier le code source en langage C)  
- Connaissances de base en microcontrôleurs AVR, notamment sur l’**ATmega32**  
- Compréhension des principes de la **communication SPI**  
- Familiarité avec les périphériques : écran LCD, clavier matriciel, EEPROM, ADC (convertisseur analogique-numérique)  

---

## 🛠️ Installation & configuration

1. **Installer Proteus** 8.9 ou version ultérieure sur votre machine.  
2. **Cloner ou télécharger** le dépôt GitHub :  
   `https://github.com/HaMzaCheh/Smart-Home-Proteus`  
3. Ouvrir le projet Proteus `Smart Home.pdsprj` dans Proteus.  
4. Charger les fichiers `.hex` fournis pour le **maître** et l’**esclave** dans leurs microcontrôleurs respectifs (via la propriété du microcontrôleur dans Proteus).  
5. Pour toute modification du code : compiler les fichiers `.c` avec AVR GCC (librairies incluses dans le dépôt).  

---

## 🚀 Utilisation détaillée

### 1. Connexion utilisateur

- Au premier démarrage, le système vérifie si les mots de passe **administrateur** et **invité** sont configurés. Sinon, il vous invite à les définir via le clavier.  
- L’écran affiche ensuite un menu de connexion :  
  - **`0` = Administrateur**  
  - **`1` = Invité**  
- Saisissez ensuite un mot de passe à 4 chiffres.  

> ❗️ Chaque profil a des droits différents, garantissant la sécurité et la gestion adaptée des appareils.

### 2. Navigation dans le menu principal

- Après authentification, un menu clair s’affiche : choix des pièces, contrôle des appareils.  
- **Administrateur** : accès à toutes les fonctions (TV, climatisation, lumières).  
- **Invité** : accès limité, par exemple uniquement aux lumières.  
- Utilisez le clavier pour naviguer facilement dans les options et activer/désactiver les appareils.

### 3. Déconnexion automatique

- En cas d’inactivité prolongée (pas d’appui sur une touche), la session est automatiquement fermée pour garantir la sécurité.

---

## 🧩 Architecture du code

### Code Maître

- **Interface utilisateur** : gestion de l’écran LCD, clavier, menus.  
- **Authentification** : stockage sécurisé des mots de passe dans l’EEPROM.  
- **Communication SPI** : envoi des commandes au contrôleur esclave.  
- **Gestion des sessions** avec minuteries et interruption.  

### Code Esclave

- **Réception des commandes SPI** et exécution des actions (allumage/extinction des LEDs symbolisant les appareils).  
- **Mesure de la température** via ADC pour contrôle automatique de la climatisation.  
- **Gestion des sorties** en fonction des commandes reçues.

---

## 🎮 Simulation dans Proteus

1. Ouvrez le fichier `Smart Home.pdsprj`.  
2. Vérifiez que les microcontrôleurs contiennent les bons fichiers `.hex`.  
3. Lancez la simulation.  
4. Interagissez avec le système via le clavier virtuel.  
5. Observez en temps réel :  
   - L’affichage sur l’écran LCD  
   - L’état des LEDs qui représentent les appareils dans la maison (lumières, TV, climatisation)

---

## 🤝 Contribution

Vous souhaitez améliorer ce projet ?  
- Forkez ce dépôt  
- Apportez vos modifications  
- Envoyez une Pull Request avec une description claire de vos changements  

Toute contribution est la bienvenue, qu’il s’agisse d’ajouts fonctionnels, corrections de bugs ou améliorations d’interface.

---

<p align="center">
  <em>Projet réalisé par <strong>Hamza CHEHAIBI</strong> — Ingénieur systèmes embarqués & télécoms</em>
</p>
