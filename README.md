# ⬡ GMAO Parc & Atelier

> **Système de Gestion de Maintenance Assistée par Ordinateur**  
> Application web standalone de coordination entre le Chef de Parc et le Chef d'Atelier.

![Version](https://img.shields.io/badge/version-2.0-f59e0b?style=flat-square)
![HTML](https://img.shields.io/badge/stack-HTML%20%2F%20CSS%20%2F%20JS-3b82f6?style=flat-square)
![Licence](https://img.shields.io/badge/licence-MIT-10b981?style=flat-square)
![Offline](https://img.shields.io/badge/offline-compatible-10b981?style=flat-square)
![Lang](https://img.shields.io/badge/langue-Français-ef4444?style=flat-square)

---

## 📌 Présentation

Application de gestion industrielle dédiée aux structures gérant un **parc d'engins** et un **atelier de maintenance**. Elle centralise les échanges entre les équipes, suit l'état des engins, gère le stock de pièces, le carburant et les ordres de travail — le tout dans un **fichier HTML unique**, sans installation ni serveur.

---

## 🚀 Démarrage rapide

```bash
# Cloner le repo
git clone https://github.com/votre-username/gmao-parc-atelier.git

# Ouvrir directement dans le navigateur
open index.html
````

> ✅ Aucune dépendance. Aucun serveur requis. Fonctionne hors ligne.

---

## 📑 INDEX COMPLET

### 0. ACCÈS & AUTHENTIFICATION

* 0.1 Sélecteur de rôle (sidebar footer)
* 0.2 Rôles disponibles
  * 0.2.1 Master Admin — accès total
  * 0.2.2 Chef d'Atelier — OT, stock, sections
  * 0.2.3 Chef de Parc — engins, chantiers, réceptions
  * 0.2.4 Coordinateur (Amine) — rôle transversal
* 0.3 Avatar et badge de rôle actif

---

### 1. DASHBOARD GÉNÉRAL

* 1.1 KPIs principaux
  * 1.1.1 Engins actifs (sur total flotte)
  * 1.1.2 Engins en panne
  * 1.1.3 Interventions en cours
  * 1.1.4 Taux de disponibilité parc (%)
* 1.2 Alertes système
  * 1.2.1 Alerte stock critique / rupture
  * 1.2.2 Alerte dépassement heures de service
* 1.3 Tableau engins en panne (résumé)
* 1.4 Jauges capacité atelier par section
* 1.5 Timeline activité récente

---

### 2. MODULE PARC

#### 2.1 Engins & Fiches

* 2.1.1 Grille visuelle des engins (cards)
* 2.1.2 Filtrage par statut (Disponible / En panne / Maintenance)
* 2.1.3 Badge statut coloré par engin
* 2.1.4 Fiche technique engin
  * N° Interne
  * Type / Modèle
  * N° Châssis
  * N° Série
  * Année de mise en service
  * KM / Heures actuels
  * Localisation / Chantier affecté
  * Statut opérationnel
  * Observations techniques
* 2.1.5 Formulaire ajout nouvel engin

#### 2.2 Chantiers

* 2.2.1 Liste des chantiers actifs
* 2.2.2 Informations chantier
  * Référence interne
  * Désignation
  * Localisation (ville / région)
  * Engins affectés
  * Responsable de chantier
  * Statut (Actif / Pause / Clôturé)
* 2.2.3 Formulaire nouveau chantier
* 2.2.4 Vue détail par chantier

#### 2.3 Réceptions

* 2.3.1 Historique des réceptions
* 2.3.2 Informations réception
  * Date de réception
  * Engin réceptionné
  * Chantier d'origine
  * KM / Heures à la réception
  * État constaté à l'arrivée
  * Agent récepteur
  * Observations / Suite donnée
* 2.3.3 Formulaire nouvelle réception
* 2.3.4 Orientation automatique (atelier / VT / base)

---

### 3. MODULE ATELIER

#### 3.1 Interventions — Ordres de Travail

* 3.1.1 Filtrage par section atelier
  * Mécanique
  * Soudage
  * Sablage
  * Peinture
  * Tour-Fraisage
  * Pneumatique
* 3.1.2 Tableau des OT
  * N° OT (auto-incrémenté)
  * Engin concerné
  * Description de la panne
  * Section atelier assignée
  * Technicien responsable
  * Date d'ouverture
  * Priorité (Urgent / Normal / Faible)
  * Statut (En cours / Bloquée / Terminée)
* 3.1.3 Formulaire nouvel ordre de travail
* 3.1.4 Fiche intervention détaillée
  * Informations engin & technicien
  * Description complète de la panne
  * Liste des pièces utilisées + statut sortie stock
  * Mise à jour du statut en temps réel
  * Export PDF de la fiche

#### 3.2 Stock & Pièces

* 3.2.1 KPIs stock
  * Nombre de références actives
  * Ruptures actives
  * Références en seuil critique
  * Valeur totale du stock (MAD)
* 3.2.2 Alertes rupture et seuil critique
* 3.2.3 Tableau de stock
  * Référence pièce
  * Désignation
  * Catégorie (Filtration / Joints / Lubrifiants / Hydraulique…)
  * Quantité disponible
  * Seuil minimum
  * Unité (Pcs / Litres / Kg / Mètres / Jeux)
  * Prix unitaire (MAD)
  * Fournisseur
  * Statut (OK / Bas / Critique / Rupture)
* 3.2.4 Recherche texte en temps réel
* 3.2.5 Formulaire entrée stock
  * Référence, désignation, catégorie
  * Quantité & unité
  * Prix unitaire, seuil minimum
  * Fournisseur, N° bon de commande, date réception
* 3.2.6 Formulaire sortie stock
  * Pièce, quantité
  * Lien vers intervention (OT)
  * Valideur (Coordinateur / Chef Atelier / Admin)
  * Motif de sortie

#### 3.3 Carburant & Lubrifiants

* 3.3.1 KPIs carburant
  * Volume gasoil disponible (litres)
  * Consommation hebdomadaire (litres)
  * Volume huile moteur (litres)
  * Coût mensuel (MAD)
* 3.3.2 Bons de carburant
  * Date, engin, chauffeur
  * Litres consommés
  * KM / Heures relevés
  * Statut de validation
* 3.3.3 Formulaire nouveau bon carburant
* 3.3.4 Jauges niveaux lubrifiants
  * Huile moteur 15W40
  * Huile hydraulique
  * Graisse multi-usage
  * Liquide de refroidissement

---

### 4. MODULE COORDINATION

#### 4.1 Dashboard Coordinateur

* 4.1.1 KPIs de coordination
  * Besoins urgents (engins en attente d'intervention)
  * Transferts de pièces à valider
  * OT ouverts
  * OT clôturés dans la semaine
* 4.1.2 Tableau transferts à valider
  * Pièce, quantité, OT concerné
  * Demandeur
  * Validation directe par le Coordinateur
* 4.1.3 Messagerie interne Parc ↔ Atelier ↔ Coordinateur
  * Timeline chronologique des échanges
  * Formulaire nouveau message
    * Expéditeur / Destinataire
    * Priorité (Normale / Urgente)
    * Objet (Intervention / Stock / Engin / Chantier / Autre)
* 4.1.4 Tableau de bord hebdomadaire
  * Disponibilité par chantier (%)
  * MTTR moyen (heures)
  * Consommation gasoil de la semaine
  * Top pannes récurrentes

---

### 5. RAPPORTS & EXPORTS

#### 5.1 Générateur de rapports

* 5.1.1 Types de rapports disponibles
  * Disponibilité du Parc (hebdomadaire)
  * Interventions par période
  * Consommations Carburant & Lubrifiants
  * État des stocks
  * Historique par engin
  * Rapport par chantier
* 5.1.2 Paramètres de génération
  * Période (semaine / mois / personnalisée)
  * Dates début et fin
  * Filtre par engin (optionnel)
  * Format d'export choisi

#### 5.2 Exports

* 5.2.1 **CSV** — données brutes du parc (téléchargement réel)
* 5.2.2 **PDF** — fiche propre avec KPIs + tableaux (impression directe)
* 5.2.3 Bouton export disponible dans toutes les sections (topbar)

#### 5.3 Aperçu rapport

* 5.3.1 KPIs résumés (opérationnels / en panne / taux dispo)
* 5.3.2 Tableau disponibilité par engin (jours, MTTR, %)

---

### 6. SYSTÈME D'ALERTES & NOTIFICATIONS

* 6.1 Cloche de notifications (topbar)
  * Badge rouge si alertes actives
  * Panneau déroulant avec liste horodatée
* 6.2 Types d'alertes gérées
  * 6.2.1 Rupture de stock
  * 6.2.2 Seuil de stock critique
  * 6.2.3 Dépassement heures de service (VT obligatoire)
  * 6.2.4 Panne engin signalée sur chantier
  * 6.2.5 Intervention clôturée (confirmation)
* 6.3 Bandeaux d'alerte contextuels (rouge / orange) dans chaque page
* 6.4 Toasts de confirmation après chaque action (enregistrement, validation, export)

---

### 7. INTERFACE & EXPÉRIENCE UTILISATEUR

* 7.1 Thème sombre industriel avec grille de fond
* 7.2 Sidebar navigable avec badges de comptage par section
* 7.3 Topbar avec titre dynamique, fil d'ariane, boutons export globaux
* 7.4 9 modals de formulaire (Engin, Intervention, Fiche OT, Pièce, Sortie Stock, Carburant, Chantier, Réception, Message)
* 7.5 Tableaux avec hover, badges colorés, colonnes mono-espace
* 7.6 Jauges de capacité avec barres de progression colorées
* 7.7 Timeline d'activité chronologique
* 7.8 Cards engins avec code couleur statut (vert / orange / rouge)
* 7.9 Fichier HTML standalone — aucune dépendance, utilisable hors ligne

---

## 🗂 Structure du Projet

```
gmao-parc-atelier/
├── index.html          # Application complète (standalone)
└── README.md           # Documentation & index
```

---

## 🛠 Stack Technique

| Composant | Technologie |
|-----------|-------------|
| Frontend | HTML5 / CSS3 / JavaScript Vanilla |
| Fonts | Rajdhani, IBM Plex Mono, IBM Plex Sans (Google Fonts) |
| Export CSV | Blob API natif |
| Export PDF | window\.print() natif |
| Stockage | localStorage (extensible) |
| Dépendances | **Aucune** |

---

## 📋 Modules & Pages

| # | Page | Module | Accès |
|---|------|--------|-------|
| 1 | Dashboard | Général | Tous |
| 2 | Engins & Fiches | Parc | Chef Parc, Admin, Coord. |
| 3 | Chantiers | Parc | Chef Parc, Admin, Coord. |
| 4 | Réceptions | Parc | Chef Parc, Admin, Coord. |
| 5 | Interventions | Atelier | Chef Atelier, Admin, Coord. |
| 6 | Stock & Pièces | Atelier | Chef Atelier, Admin, Coord. |
| 7 | Carburant & Lubrifiants | Atelier | Chef Atelier, Admin, Coord. |
| 8 | Coordinateur | Coordination | Coordinateur, Admin |
| 9 | Rapports | Global | Tous |

---

## 🔐 Rôles & Permissions

| Fonctionnalité | Master Admin | Chef Atelier | Chef Parc | Coordinateur |
|----------------|:---:|:---:|:---:|:---:|
| Dashboard global | ✅ | ✅ | ✅ | ✅ |
| Gestion engins | ✅ | — | ✅ | ✅ |
| Ordres de travail | ✅ | ✅ | — | ✅ |
| Sorties stock | ✅ | ✅ | — | ✅ |
| Validation transferts | ✅ | — | — | ✅ |
| Bons carburant | ✅ | ✅ | ✅ | ✅ |
| Rapports & exports | ✅ | ✅ | ✅ | ✅ |

---

## 🗺 Roadmap

* [ ] Backend Node.js + base de données SQLite / PostgreSQL
* [ ] Authentification JWT avec sessions sécurisées
* [ ] PWA (Progressive Web App) avec mode hors ligne complet
* [ ] Notifications push temps réel (WebSocket)
* [ ] API REST pour intégration ERP externe
* [ ] Historique complet par engin (graphiques)
* [ ] Application mobile (React Native)

---

## 👤 Auteur

**Mohamed Amine Rami**  
Fleet Manager & Logistics Coordinator  
Soualem, Maroc

---

## 📄 Licence

Ce projet est sous licence **MIT** — libre d'utilisation, de modification et de distribution.

---

> *GMAO Parc & Atelier — Système de Gestion Industrielle — Precision Logistics*
