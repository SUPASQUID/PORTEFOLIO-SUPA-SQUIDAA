---
title: "Actualité Cyber - PromptSpy : L'IA au cœur de l'espionnage mobile"
publishDate: 2026-03-01 00:00:00
img: /assets/promptspy.png
img_alt: Illustration de la menace PromptSpy et de l'exploitation de l'IA sur Android
description: |
  Analyse de PromptSpy, le premier cas documenté d'un malware Android exploitant un grand modèle de langage (LLM) de manière dynamique pour automatiser l'espionnage et le contournement des défenses.
tags:
  - Cybersecurite
  - Intelligence Artificielle
  - Android
  - SISR
---

## Pourquoi avoir choisi ce sujet ?

> L'IA transforme un malware passif en un agent actif et défensif.

L'actualité liée à cette menace est particulièrement brûlante suite à un rapport publié par ESET en **Février 2026**, marquant l'entrée dans une nouvelle ère de menaces "intelligentes" et adaptatives. 

Contrairement aux usages classiques de l'IA générative pour le phishing, PromptSpy représente une véritable innovation offensive : il délègue sa prise de décision dynamique à un LLM. Le malware "voit" l'écran de la victime et l'IA lui indique directement les actions à exécuter, rendant obsolètes les scripts d'attaque statiques traditionnels. Ce détournement d'outils légitimes (Google Gemini) pose un défi éthique et technique majeur.

---

## Qu'est-ce que PromptSpy et comment fonctionne-t-il ?

PromptSpy est un logiciel malveillant sophistiqué qui infecte les appareils Android via des campagnes de *Smishing* (SMS de phishing) ou de faux sites bancaires. L'IA fait office de cerveau selon un processus itératif précis :

1. **Extraction :** Le malware extrait l'arborescence XML de l'écran affiché sur le smartphone.
2. **Analyse :** Il envoie cette description textuelle à l'API Gemini de Google accompagnée d'un prompt spécifique.
3. **Décision :** Gemini renvoie les coordonnées précises (X, Y) de l'élément à cibler (par exemple, le bouton "Valider").
4. **Action :** Le malware exécute le clic de manière totalement automatisée.

### Faille et exploitation du système

La vulnérabilité exploitée n'est pas un bug logiciel classique, mais un abus de fonctionnalité systémique. PromptSpy détourne l'API **AccessibilityService**, initialement conçue par Android pour aider les utilisateurs en situation de handicap. En obtenant cette permission critique, le logiciel malveillant obtient le droit de lire tout le contenu de l'écran (y compris les mots de passe masqués) et d'agir sans aucune interaction de l'utilisateur.

### Persistance intelligente et capacités d'espionnage

Le couplage avec l'IA offre au malware une résilience inédite :
* **Contournement de la veille :** Android ferme régulièrement les applications inactives. PromptSpy demande à l'IA de vérifier si l'application est toujours dans la liste "récente" et la relance automatiquement si besoin.
* **Anti-désinstallation :** L'IA détecte si l'utilisateur tente d'accéder aux paramètres pour supprimer l'application et simule instantanément un clic sur le bouton "Retour" ou "Home".

Ses capacités d'espionnage avancé incluent le *keylogging* visuel (capture des saisies sur claviers virtuels aléatoires), le *screen recording* (enregistrement vidéo pour intercepter les codes de double authentification 2FA), le contrôle à distance via un pont VNC, et l'exfiltration de données ciblant principalement les portefeuilles de crypto-monnaies et les applications bancaires.

---

## Prévention, remédiation et impacts globaux

La lutte contre ce type de menace hybride nécessite des mesures à plusieurs niveaux :

* **Au niveau de l'OS (Android) :** Utilisation des *Restricted Settings* (depuis Android 14+) pour bloquer l'activation des services d'accessibilité pour les applications installées en dehors des stores officiels (*sideloadées*).
* **Au niveau logiciel :** Analyse heuristique via Google Play Protect pour détecter les comportements de type "screen reading" suspects.
* **Au niveau utilisateur :** Application d'une hygiène cyber stricte (interdiction d'installer des fichiers APK tiers).
* **Remédiation :** En cas d'infection, le démarrage en **Mode Sans Échec (Safe Mode)** est le seul moyen de neutraliser l'IA pour désinstaller manuellement le malware.

### Enjeux géopolitiques et économiques

L'apparition de ces outils réduit drastiquement le coût de développement des malwares complexes, permettant des attaques de masse auparavant réservées à des groupes étatiques. Des pays à forte adoption du système bancaire mobile comme la France ou l'Inde font face à des risques réels de déstabilisation. 

De plus, des traces de langue chinoise découvertes dans le code suggèrent une origine liée à des groupes d'espionnage d'Asie de l'Est, orientant l'usage de ce prototype vers de la surveillance ciblée de diplomates ou de dissidents. Cela soulves de lourdes questions politiques quant à la nécessité de brider ou réguler l'accès aux API publiques des IA.

---

## Ressources et consultation

* [Consulter le diaporama de la présentation](https://docs.google.com/presentation/d/1gcsnlfFyzSaWJJH8r29GDxZyy8122GBsW9ULkx_CNRk/edit?usp=sharing)

#### Sources analysées
- ESET Research : *“PromptSpy ushers in the era of Android threats”* (Février 2026)
- SecurityWeek : *“Malware abuses Gemini AI for persistence”*
- The Hacker News : *“PromptSpy Android Malware Analysis”*
