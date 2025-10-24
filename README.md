# 💻 Antoine Le Provost — Développeur Mainframe

## 👋 À propos de moi

Je suis **Antoine Le Provost**, développeur en formation spécialisé dans les environnements **mainframe IBM**.  
Sociable, curieux et passionné par la technologie, j’aime particulièrement le **travail collaboratif** et la **résolution de problèmes complexes**.  
Ma motivation : concevoir des programmes qui améliorent l’expérience des utilisateurs et optimisent les processus métiers.

📧 **Mail :** [antoine.leprovost@gmail.com](mailto:antoine.leprovost@gmail.com)  
📞 **Téléphone :** 06 52 70 48 40  
🌍 **Langues :** Anglais B1, Espagnol A2  
🔗 [Mon profil LinkedIn](https://www.linkedin.com/in/antoine-le-provost/) 

---

## 🎓 Formation

- **2025 – POEC Développeur Grands Systèmes**  
  *Apprentissage des environnements mainframe :* COBOL, PACBASE, ECLIPSE RDZ, ISPF, DB2, SQL, CICS.

- **2021–2024 – BUT Informatique, Parcours A**  
  *IUT de Lannion* — Formation axée sur la programmation, la conception logicielle et la gestion de projet.

- **2020–2021 – Prépa Intégrée EPITA**, Villejuif  
- **2019–2020 – Baccalauréat STI2D, option ITEC**, Lycée Pierre et Marie Curie (Saint-Lô)

---

## 💼 Expériences professionnelles

### 🔹 Alternance – ENEDIS (2023–2024)
Développement d’un **programme d’automatisation des commandes de vêtements**.  
Participation à l’analyse fonctionnelle, la conception et la mise en production.  
Utilisation de méthodes **Agile**.

### 🔹 Stage – ENEDIS (2023)
Création d’une **application web "PICUP"** permettant de répertorier tous les sites français d’ENEDIS.  
Travail sur la conception de la base de données, l’interface utilisateur et la mise en ligne.

---

## 🧠 Compétences techniques

- **Langages :** COBOL, SQL, Java, PACBASE  
- **Environnements :** CICS, DB2, ISPF, Eclipse RDz  
- **Concepts :** BMS, pseudo-conversationnel, gestion de transactions, optimisation système  
- **Méthodes :** Agile / Scrum  
- **Soft Skills :** Adaptabilité, travail en équipe, sens du service, rigueur, autonomie  

---

## 🏦 Projet COBOL — Système de Gestion Bancaire

### 📋 Description

Ce projet académique met en œuvre un **système de gestion bancaire complet** développé en **COBOL CICS** avec une base de données **DB2**.  
Il permet à un client de réaliser les opérations suivantes :  
- Dépôt  
- Retrait  
- Virement entre comptes  
- Consultation paginée de l’historique des opérations  

L’application s’appuie sur l’architecture **3270 BMS** pour les écrans et utilise le modèle **pseudo-conversationnel CICS** pour optimiser l’utilisation des ressources.

---

### 🎯 Fonctionnalités principales

#### 📊 Menu Principal (SN01)
- Navigation vers les modules de Retrait, Dépôt, Virement, Historique  
- Identification du client par son ID  

#### 💰 Retrait (SN02)
- Vérification du solde disponible  
- Débit du compte et enregistrement en base  

#### 💵 Dépôt (SN03)
- Crédit du compte  
- Mise à jour du solde avec précision décimale  

#### 🔄 Virement (SN04)
- Virement inter-comptes avec validation des montants et conversion automatique  
- Double enregistrement (débit + crédit)  

#### 📜 Liste des opérations (SN05)
- Affichage paginé (10 opérations/page)  
- Tri décroissant (plus récentes en premier)  
- Navigation par **F7/F8**, retour menu avec **F3**

---

### 🗄️ Base de données DB2

Trois tables structurent le système :  

#### Table CLIENT
    CREATE TABLE API3.CLIENT (
        ID_CLIENT       INTEGER NOT NULL PRIMARY KEY,
        NOM_CLIENT      VARCHAR(50),
        PRENOM_CLIENT   VARCHAR(50),
        ADRESSE         VARCHAR(100),
        TELEPHONE       VARCHAR(15)
    );

#### Table COMPTE
    CREATE TABLE API3.COMPTE (
        ID_COMPTE       INTEGER NOT NULL PRIMARY KEY,
        ID_CLIENT       INTEGER NOT NULL,
        SOLDE           DECIMAL(10,2),
        DATE_OUVERTURE  DATE,
        FOREIGN KEY (ID_CLIENT) REFERENCES API8.CLIENT(ID_CLIENT)
    );

#### Table OPERATION
    CREATE TABLE API3.OPERATION (
        ID_OPERATION    INTEGER NOT NULL PRIMARY KEY,
        ID_COMPTE       INTEGER NOT NULL,
        MONTANT_OP      DECIMAL(10,2),
        TYPE_OP         CHAR(1),  -- 'D' = Dépôt, 'R' = Retrait, 'V' = Virement
        DATE_OP         DATE,
        FOREIGN KEY (ID_COMPTE) REFERENCES API8.COMPTE(ID_COMPTE)
    );

---

    Projet-cobol/
    │
    ├── BMS/               # Écrans 3270 (BMS)
    ├── PROGRAMME/         # Programmes COBOL
    ├── CPY/               # Copybooks DB2
    ├── JCL/               # Jobs de compilation
    ├── SQL/               # Scripts de création et d’initialisation DB2
    └── README.md

---

## 📚 Concepts COBOL/CICS utilisés

- CICS Transaction Server  
- BMS (Basic Mapping Support)  
- DB2 Embedded SQL  
- COMMAREA pour le passage de paramètres  
- Curseurs SQL (DECLARE / FETCH)  
- XCTL & RETURN TRANSID  
- EIBAID pour la gestion des touches de fonction  
- COMP-3 pour le stockage optimisé des montants  

---

## 🧩 Autres projets

### 📖 Livre numérique interactif (2023–2024)

Création d’un jeu narratif où l’histoire évolue selon les choix de l’utilisateur.  
Technologies : Java, JSON, JavaFX.

---

## 🏁 Centres d’intérêt

Voyages ✈️ | Jeux vidéo (FPS 🎮) | Formule 1 🏎️
