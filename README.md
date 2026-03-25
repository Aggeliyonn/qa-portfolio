# 🐉 Äggeliyonn  
## QA / Test & Debug – Jeux vidéo  

---

## 📊 Résumé

- 🔴 Critiques : 1  
- 🟠 Majeurs : 1  
- 🟡 Mineurs : 1  
- 🟢 Visuels : 0  

### 📌 Statut Global
- ✔ Corrigés : 2  
- 🔧 En cours : 1  
- ❗ Restants : 1  

---

## 🧠 À propos

Je travaille sur l’analyse, le test et la compréhension des systèmes de jeu.

Je développe et teste des mods en combinant QA, debug et logique technique afin d’identifier, reproduire et analyser les comportements complexes en jeu.

Je m’intéresse particulièrement aux interactions entre systèmes (états joueur, transitions, timing, caméra).

---

## ⭐ Highlight – Désynchronisation caméra & état joueur

Lors du développement du mod **PhoneOnSkate**, un bug complexe apparaît à la fermeture du téléphone.

Le joueur reste correctement sur le skate (état monde cohérent), mais la caméra se désynchronise et bascule incorrectement entre première et troisième personne.

👉 Ce bug implique plusieurs systèmes en interaction :
- état du joueur  
- objet skate  
- interface téléphone (UI)  
- gestion de la caméra  

📌 Analyse :  
Le problème semble provenir d’un conflit entre l’état du joueur maintenu sur le skate et la gestion de la caméra lors de la sortie de l’interface téléphone.

---

## 🔧 Projets

### 🎮 PhoneOnSkate — Schedule I

**Contexte :** Mod en cours de développement et de test  

**Type :** Mod MelonLoader  
**Objectif :** Utiliser le téléphone en skateboard  

**Travail réalisé :**
- Analyse des états joueur  
- Gestion des transitions (dismount / remount)  
- Identification de bugs système :
  - Clone d’objet (skate)  
  - Désynchronisation caméra  
  - Problèmes liés au timing (frames)  

👉 QA Report : [Voir le QA Report complet](PhoneOnSkate/QA_Report_.md)

---

## 🧪 Approche QA

- Identification des scénarios  
- Reproduction précise des bugs  
- Analyse des conditions et du timing  
- Documentation structurée (Dev Log + QA Report)  
- Priorisation des bugs (critique → visuel)

---

## 🛠️ Compétences

- Test manuel  
- Reproduction de bugs  
- Analyse comportementale  
- Analyse de systèmes multi-états  
- Lecture de logs (MelonLoader / Unity)  
- Modding (Harmony, IL2CPP)
