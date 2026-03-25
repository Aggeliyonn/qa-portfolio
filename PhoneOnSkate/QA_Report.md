# 🧪 QA Report – PhoneOnSkate v0.1

**Jeux :** Schedule 1 - PhoneOnSkate

---

## 📊 Résumé

- 🔴 Critiques : 1  
- 🟠 Majeurs : 1  
- 🟡 Mineurs : 1  
- 🟢 Visuels : 0  

### 📌 Statut global
- ✔ Corrigés : 2  
- 🔧 En cours : 1  
- ❗ Restants : 1  

---

## 🔧 Dev Log

Objectif :  
Pouvoir sortir le téléphone en étant sur le skate roulant et refermer le téléphone sans descendre et continuer sa route.

### Étape – Bloquer le dismount
- Empêcher le dismount à l’ouverture du téléphone  

### Étape – Ralentir le dismount
- Empêcher le dismount pendant 6 frames après l’ouverture du téléphone  

### Étape – Dismount Remount
- Remount automatique après dismount contrôlé  

---

## 🐞 QA Bug Report

---

### 🔴 Bug – Freeze écran

**Origine :** Étape Bloquer le dismount  

#### Conditions
- Être sur le skate et ouvrir le téléphone  

#### Étapes
1. Monter sur le skate  
2. Ouvrir le téléphone  

#### Résultat actuel
- Freeze complet du jeu  
- Apparition d’une zone noire à la place du texte  

#### 📷 Capture du bug
![Bug caméra](Pictures/bug-block-dismount.png)

#### Résultat attendu
- Rester sur le skate avec le téléphone ouvert  

#### Fréquence
- 10/10  

#### Reproductibilité
- Toujours → déclenchable à coup sûr  

#### Analyse
- Semble lié à la caméra, au joueur (entité), au skate (objet) et au téléphone (UI)  
- Se produit uniquement sur le skate  
- Probable conflit entre les objets téléphone, joueur et skate  
- Le problème semble provenir d’un conflit entre interface et caméra  

#### Statut
- ✔ Corrigé  

---

### 🟠 Bug – Remount impossible après délai

**Origine :** Étape Ralentir le dismount  

#### Conditions
- Être sur le skate  
- Ouvrir le téléphone  
- Attendre 6 frames  

#### Étapes
1. Monter sur le skate  
2. Ouvrir le téléphone  

#### Résultat actuel
- Le jeu continue normalement  
- Aucun remount effectué  

#### Résultat attendu
- Remonter sur le skate après les 6 frames  

#### Fréquence
- 10/10  

#### Reproductibilité
- Toujours → déclenchable à coup sûr  

#### Analyse
- Semble lié à l’interface téléphone et à l’objet skate  
- Le skate disparaît temporairement pendant les 6 frames  
- Le remount ne peut pas être appliqué  

#### Statut
- ✔ Corrigé  

---

### 🟡 Bug – Désynchronisation caméra

**Origine :** Étape Dismount Remount  

#### Conditions
- Ouvrir le téléphone en étant sur le skate  

#### Étapes
1. Monter sur le skate  
2. Ouvrir le téléphone  
3. Attendre  
4. Fermer le téléphone  

#### Résultat actuel
- Le remount fonctionne  
- Bug caméra à la fermeture  

#### Résultat attendu
- Continuer à rouler normalement après fermeture  

#### Fréquence
- 10/10  

#### Reproductibilité
- Toujours → déclenchable à coup sûr  

#### Analyse
- Le joueur reste correctement sur le skate  
- La caméra devient incohérente  
- Le jeu pense être en first person  
- Conflit entre état joueur et gestion caméra  
- La caméra ne sait pas si elle doit être en première ou troisième personne  

#### Statut
- 🔧 En cours  
