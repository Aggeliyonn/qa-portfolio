*QA Report - PhoneOnSkate v0.1

Jeux : Schedule 1 - PhoneOnSkate
**Résumé:
🔴 Critiques : 1
🟠 Majeurs : 1
🟡 Mineurs : 1
🟢 Visuels : 0
📌 Statut global
✔ Corrigés : 2
🔧 En cours : 1
❗ Restants : 1

**Dev Log:
Pouvoir sortir le téléphone en étant sur le skate roulant et refermer le téléphone sans descendre et continuer sa route.


Étape Bloquer le dismount
Empêcher le dismount a l’ouverture du téléphone

Étape Ralentir le dismount
Empêcher le dismount pendants 6 frame après l’ouverture du téléphone

Étape Dismount Remount
Remount automatiquement après dismount contrôlé

**Qa Bug Report

***Origine: Étape Bloquer le dismount

Conditions:
Être sur le skate et ouvrir le téléphone

Étapes:
Montez sur le skate
Ouvrir le téléphone

Résultat actuel:
Freeze complet du jeu
Apparitions d’une zone noire dans l’interface au zone de texte




Capture du Bug:


Résultat attendu:
Restez sur le skate avec le téléphone ouvert

Fréquence: 10/10

Reproductibilité:
Toujours -> Je peux le déclencher à coup sûr

Analyse:
Semble lié à la caméra, aux joueur(entité), au skate(objet), au téléphone(UI)
Se produit uniquement si sur le skate
Probable conflit entre l’objet du téléphone, le joueur, et l’objet du skate
Le problème semble provenir d’un conflit complet d’Interface mélanger à la caméra

Statut:
Corrigé


***Origine : Étape Ralentir le dismount

Conditions:
être sur le skate et ouvrir le téléphone
attendre 6 frames et tenter de remount

Étapes:
Monter sur le skate
Ouvrir le téléphone

Résultat actuel:
Le jeux tourne normalement, comme si on avais rien toucher

Résultat attendu:
Remontez sur le skate après les 6 frames qui précèdent l'ouverture du téléphone.

Fréquence: 10/10

Reproductibilité:
Toujours -> Je peux le déclencher à coup sûr

Analyse:
Semble lié à l’interface du téléphone, l'objet du skate dans le monde
Le skate semble disparaître durant ces 6 frames ducoup l’appel du personnage sur le skate n'est pas possible.

Statut:
Corrigé


***Origine : Étape Dismount Remount

Conditions:
Ouvrir le téléphone en étant sur le skate

Étapes:
Monter sur le skate
Ouvrir le téléphone
Patienter
Fermer le téléphone

Résultat actuel:
Le remount fonctionne très bien, ca bug a la fermeture du téléphone.

Résultat attendu:
Monter sur le skate, ouvrir le téléphone, continuer à rouler, fermer le téléphone, continuer à rouler.

Fréquence: 10/10

Reproductibilité:
Toujours -> Je peux le déclencher à coup sûr

Analyse:
Le dismount remount fonctionne très bien, le joueur peut continuer à rouler en ayant le téléphone en mains.
À la fermeture du téléphone, la caméra bug.
À la fermeture, le jeu pense que nous devons être en first personne.
Le remount fais en sorte que le joueur (entité dans le monde) soit toujours sur le skate
La caméra c’est pas si elle doit être première ou troisième personne.

Statut:
En cours
