# 🧪 In Progress - ProfitCalculator

**Statut :** 🟠 In Progress  
**Version :** v0.1  
**Type :** Mod / Feature  
**Projet cible :** Schedule I  
**Objectif principal :**  
> Créer un Profit Calculator capable de lire les données utiles des produits et de les afficher dans une interface exploitable en jeu.

**Vision finale :**  
> Une interface propre, idéalement liée au téléphone ou à l’application produit, qui affiche les informations utiles sur les produits, leurs recettes, leurs ingrédients, leurs coûts et leur profit estimé.

---

## 🧱 Architecture

### Core
- Initialisation du mod via MelonLoader
- Chargement Harmony PatchAll
- Gestion de l’état global du mod
- Lancement des scans nécessaires

### UI
- Fenêtre de base affichable / masquable
- Affichage des informations récupérées
- Système de toggle clavier actuel en F6
- Interface encore brute

### Data
- Scan des produits
- Lecture de certaines informations utiles
- Début de récupération des recipes / ingrédients / prix
- Données encore incomplètes ou à confirmer

### Hooks / Intégration
- Utilisation du mod dans le contexte du jeu
- Volonté de lier le comportement à l’application produit / téléphone
- Input clavier actuellement trop global ou mal placé selon contexte

### Debug
- Logs de chargement du mod
- Vérification de l’initialisation
- Tests d’ouverture de fenêtre
- Tests de récupération des données produits

---

## ⚙️ Progression

### 🧩 Core
- [x] Mod chargé correctement
- [x] Message de chargement affiché
- [x] Harmony PatchAll actif
- [x] Base du projet créée
- [ ] Gestion plus fine des scènes / contextes


### 🧩 UI
- [x] Fenêtre visible en jeu
- [x] Base de DrawWindow en place
- [x] Affichage d’une première interface fonctionnelle
- [ ] Interface fermée par défaut uniquement quand il faut
- [ ] Ouverture dans le bon contexte uniquement
- [ ] Intégration propre à l’application produit / téléphone
- [ ] Mise en page améliorée
- [ ] Scroll propre si nécessaire
- [ ] Boutons / actions plus propres

### 🧩 Data
- [x] Début de scan des produits
- [x] Premier affichage d’informations de produits
- [x] Début de récupération de certaines valeurs utiles
- [ ] Confirmer la récupération correcte de toutes les recipes
- [ ] Confirmer la récupération correcte des ingrédients
- [ ] Confirmer la récupération correcte des prix
- [ ] Confirmer la récupération correcte de basePrice
- [ ] Structurer les données proprement
- [ ] Préparer le vrai calcul de profit

### 🧩 Input
- [x] Toggle F6 mis en place
- [ ] Déterminer si l’input doit rester clavier ou passer par un bouton in-game
- [ ] Restreindre l’ouverture à un contexte précis
- [ ] Éviter l’ouverture au mauvais moment

### 🧩 Intégration
- [ ] Identifier précisément la meilleure cible liée au téléphone / Product App
- [ ] Déterminer comment appeler les bonnes données au bon moment
- [ ] Relier l’interface au vrai flux du jeu
- [ ] Rendre l’expérience plus naturelle côté joueur

### 🧩 Debug
- [x] Logs de base présents
- [x] Vérification du chargement effectuée
- [x] Premiers tests d’affichage réalisés
- [ ] Ajouter logs plus précis sur l’input F6
- [ ] Ajouter logs sur le contexte de l’application produit
- [ ] Réduire les erreurs et faux tests
- [ ] Nettoyer les logs quand le comportement sera stable

---

## 🔍 Découvertes techniques

- Le mod se charge bien et Harmony fonctionne.
- Une interface de base peut déjà s’afficher en jeu.
- Le système de scan a commencé à récupérer des données utiles sur les produits.
- Le projet avance vers la lecture des recipes, ingrédients, prix et basePrice.
- Le comportement du toggle F6 semble poser problème dans le contexte de l’application produit.
- L’interface actuelle fonctionne comme base de test, mais pas encore comme intégration finale.

### Hypothèses
- L’application produit ou le téléphone modifie la manière dont l’input est capturé.
- Certaines données utiles existent déjà dans les objets produits mais doivent encore être correctement lues ou structurées.
- Le meilleur résultat final viendra probablement d’une intégration dans l’UI du téléphone plutôt qu’une simple fenêtre libre.

### Cibles importantes
- `Core.cs`
- `Scan.cs`
- `DrawWindow`
- Système de l’application produit / téléphone
- Système d’input en jeu

---

## 🧠 Problèmes rencontrés

### ❌ L’interface s’ouvre / existe encore comme outil global de test
- **Description :** la fenêtre actuelle sert de base technique mais n’est pas encore liée proprement au bon contexte.
- **Cause probable :** la logique d’ouverture est encore trop générale.
- **Impact :** l’expérience n’est pas encore naturelle ni finalisée.
- **Statut :** En cours

### ❌ Les données utiles ne sont pas encore complètement fiabilisées
- **Description :** les recipes, ingrédients, prix et basePrice ne sont pas encore tous validés proprement.
- **Cause probable :** la structure exacte des données n’est pas encore totalement confirmée.
- **Impact :** impossible pour l’instant de faire un Profit Calculator complet et fiable.
- **Statut :** En cours

---

## 🛠 Solutions testées

### ✔ Base du mod
- **Action :** création du projet MelonLoader + Core + PatchAll.
- **Résultat :** OK
- **Notes :** le mod charge correctement.

### ✔ Interface de base
- **Action :** mise en place d’une première fenêtre affichable en jeu.
- **Résultat :** OK
- **Notes :** bonne base de travail pour afficher les futures données.

### ✔ Scan initial
- **Action :** début du système de scan pour récupérer les produits.
- **Résultat :** OK
- **Notes :** les premières données remontent, mais la structure finale reste à fiabiliser.

### ✔ Toggle F6
- **Action :** ajout d’une touche pour afficher / masquer la fenêtre.
- **Résultat :** OK
- **Notes :** fonctionne comme base, mais pose problème dans l’application produit.

---

## 🛠 Choix techniques

- **Technologie principale :** C#
- **Framework / Loader :** MelonLoader
- **Patch system :** Harmony
- **Type d’interface :** UI simple de test en jeu
- **Projet ciblé :** Schedule I

### Choix validés
- Utiliser MelonLoader pour la base du mod
- Utiliser Harmony pour les patches
- Commencer par une UI simple pour valider les données avant une intégration plus poussée
- Construire d’abord le scan avant de raffiner le rendu

### Refusés / écartés
- Partir trop tôt sur une UI finale sans valider les données
- Complexifier le projet avant d’avoir un flux de données fiable

---

## 📊 État actuel

### ✅ Fonctionne
- Chargement du mod
- Initialisation Harmony
- Base du projet
- Première interface visible
- Début du scan des produits
- Premiers affichages d’informations
  
![Première lecture depuis téléphone](Pictures/ui_phone_first_read.png)

### ⚠️ Partiel
- Lecture complète des données produits
- Structure des données
- Lien entre l’interface et le bon contexte de jeu

### ❗ À faire
- Stabiliser la récupération recipes / ingrédients / prix / basePrice
- Transformer l’outil de test en vraie feature cohérente
- Préparer le calcul de profit réel
- Rendre l’interface plus propre et logique

---

## 🔮 Roadmap

### Phase 1 - Base
- [x] Créer le mod
- [x] Charger Harmony
- [x] Afficher une première fenêtre
- [x] Démarrer le scan des produits

### Phase 2 - Lecture des données
- [ ] Finaliser la récupération des produits
- [ ] Lire proprement les recipes
- [ ] Lire proprement les ingrédients
- [ ] Lire proprement les prix
- [ ] Lire proprement basePrice
- [ ] Structurer les données pour les calculs

### Phase 3 - Intégration
- [ ] Relier l’interface au bon contexte
- [ ] Intégrer l’outil à l’application produit / téléphone
- [ ] Éviter l’ouverture hors contexte

### Phase 4 - Profit Calculator réel
- [ ] Calculer coût / profit
- [ ] Afficher les résultats clairement
- [ ] Ajouter tri / lisibilité / confort
- [ ] Préparer une version plus propre

### Phase 5 - Finalisation
- [ ] Nettoyer le code
- [ ] Réduire les logs inutiles
- [ ] Tester plusieurs situations
- [ ] Préparer une version présentable

---

## 🧾 Dev Notes

### Session - Base du projet
- Création du mod ProfitCalculator
- Core en place
- Chargement MelonLoader validé
- Harmony PatchAll validé
- Base du système prête

### Session - Première UI
- Fenêtre de base créée
- Affichage en jeu fonctionnel
- Début des tests d’ouverture / fermeture
- L’outil existe désormais visuellement

### Session - Scan produits
- Début du travail sur le scan
- Recherche des bonnes données liées aux produits
- Premiers affichages d’informations
- Début de récupération de recipes / ingrédients / prix / basePrice

![Lecture téléphone](Pictures/ui_phone_first_read.png)

### Session - Blocage actuel
- Problème avec F6 dans l’application produit
- L’interface n’est pas encore intégrée au bon contexte final
- Il faut maintenant stabiliser l’input et les données

### 🔧 Amélioration Interface – Système de filtres avancés

**Objectif :**
Permettre un tri intelligent des recettes pour améliorer la prise de décision en jeu.

---

**Ajouts prévus :**

* Système de tri avec **jusqu’à 4 filtres actifs**
* Critères disponibles :

  * 💰 Prix
  * 📈 Profit (%)
  * 🧪 Nombre d’ingrédients
  * ✨ Effet (limité à 1)

---

**Choix de design :**

* Maximum 4 filtres pour éviter surcharge visuelle
* Limitation à 1 effet pour garder une UI claire (surtout sur téléphone)
* Priorité des filtres définie par l’ordre (Filtre 1 → Filtre 4)

---

**Utilisation prévue :**

* Trouver la recette la plus rentable
* Adapter la production selon les préférences client
* Optimiser le craft (coût / complexité)

---

**Statut :**
🟠 En réflexion (design validé, pas encore implémenté)

---

**Notes :**

* Fonctionnalité prévue après stabilisation du système actuel (scan + affichage)
* Possibilité d’évolution vers multi-effets plus tard

---

## 📤 Export

### DevLog
- Base du mod créée
- Première interface fonctionnelle
- Début du scan des produits
- Premières données visibles en jeu
- Début du travail vers recipes / ingrédients / prix / basePrice
- Transfert de l'interface vers application

### QA_Report
- Problème de toggle F6 dans l’application produit
- Intégration UI encore trop brute / globale
- Données encore incomplètes pour le calcul final

---

## 🧿 Notes libres

- Le mod a déjà dépassé le simple stade “idée”.
- La prochaine vraie marche importante est de stabiliser la lecture des données.
- Le second point critique est de décider comment l’utilisateur ouvre l’outil dans le vrai contexte.
- Une fois recipes + ingrédients + prix stabilisés, le cœur du Profit Calculator pourra vraiment commencer.
- Tester sur une grande partie pour voir si toutes les identités sont correctes.
