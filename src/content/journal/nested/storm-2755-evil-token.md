---
title: "STORM-2755 : L'Ère de l'Infiltration par Evil Token"
publishDate: 2026-03-15 00:00:00
img: /assets/storm-2755.jpg
img_alt: Clé de sécurité physique FIDO2 protégeant contre le détournement de jetons de session
description: |
  Étude de la campagne mondiale menée par le groupe d'attaque Storm-2755, exploitant l'ingénierie sociale assistée par IA et le détournement du protocole Device Code Flow pour contourner le MFA.
tags:
  - Cybersecurite
  - Phishing
  - Microsoft 365
  - SISR
---

## L'Infiltration par Ingressio Sociale Automatisée

> L'illusion parfaite : un e-mail mentionnant votre poste exact, un projet réel de votre entreprise, pointant vers le site officiel de Microsoft.

Depuis la mi-mars 2026, la menace **Storm-2755** s'est industrialisée à l'échelle planétaire en s'appuyant sur l'intelligence artificielle pour mener des campagnes d'OSINT (*Open Source Intelligence*) automatisées. Pendant 10 à 15 jours, l'IA de l'attaquant analyse et aspire les données LinkedIn des cibles (rôles, projets en cours, historique de l'entreprise) pour rédiger un e-mail d'hameçonnage unique, ultra-calibré, sans aucune faute de syntaxe ni élément suspect (faux appels d'offres pour les achats, fausses factures pour la comptabilité, invitations à des réunions de projet).

---

## Le Détournement du Device Code Flow

Le cœur technique de l'attaque repose sur l'exploitation malveillante du protocole **Device Code Flow** (conçu initialement par Microsoft pour connecter les terminaux sans claviers comme les Smart TV via l'URI `/devicelogin`) :

1. **Navigation légitime :** La victime clique sur le lien et navigue sur le *vrai* site officiel de Microsoft, éliminant toute méfiance visuelle liée à l'URL.
2. **Saisie du code :** L'utilisateur tape un code de validation à 9 caractères fourni dans l'e-mail de phishing.
3. **Bypass MFA (Double Authentification) :** En effectuant cette action volontairement sur le site officiel, c'est l'utilisateur lui-même qui génère, valide et autorise l'accès de session à l'attaquant. Les mécanismes MFA classiques approuvent la transaction puisqu'elle émane du terminal légitime de l'utilisateur.

### Industrialisation : Le Phishing-as-a-Service

Cette méthode d'attaque s'est démocratisée sous la forme de **Phishing-as-a-Service (PaaS)**. Des kits d'attaque clés en main sont commercialisés sous forme d'abonnements SaaS sur des canaux Telegram avec un support technique 24/7. L'infrastructure criminelle s'appuie sur plus de 1 000 noms de domaines malveillants gérés dynamiquement et couplés à des processus IA pour automatiser le traitement des comptes d'utilisateurs piratés.

### La Persistance Fatale : Le vol de Refresh Token

La dangerosité de Storm-2755 réside dans le fait que le pirate ne dérobe pas le mot de passe de la victime, mais intercepte son jeton de session, plus précisément le **Refresh Token**. 
Ce jeton garantit une persistance de **90 jours d'accès dissimulé**. Par conséquent, même si l'utilisateur modifie par la suite son mot de passe principal, le jeton reste valide et le pirate conserve ses accès sans interruption pendant 3 mois.

---

## L'Infiltration Invisible et Chronologie d'une Attaque

Une fois l'accès obtenu, l'attaquant configure des règles de boîte aux lettres Outlook de manière totalement invisible pour l'utilisateur. Il cible des mots-clés spécifiques tels que "banque", "virement", "salaire" ou "RIB". Tous les e-mails correspondants ou alertes de sécurité de Microsoft sont automatiquement déplacés vers des dossiers cachés ou supprimés instantanément. 

L'attaquant peut alors contacter sereinement le service des Ressources Humaines de l'entreprise en usurpant l'identité de l'employé pour demander un changement de compte bancaire pour le versement du salaire, menant à une exfiltration financière complète en fin de mois sans que la victime n'ait reçu la moindre notification.

---

## Diagnostic et Moyens de Protection (Bouclier FIDO2)

Pour auditer un système et vérifier l'absence de compromission, l'administrateur système ou l'utilisateur doit mener un diagnostic ciblé :
* **Audit des règles de messagerie :** Inspecter minutieusement dans Outlook (*Paramètres > Courrier > Règles*) toute règle suspecte n'ayant pas été créée explicitement par l'utilisateur, notamment celles comportant des actions de suppression ou de déplacement.
* **Vigilance face aux invitations de code :** Si Microsoft demande de valider un code à l'écran alors que l'utilisateur n'a pas initié de démarche de connexion : il s'agit d'une tentative d'attaque.

### La Remédiation : Le Standard FIDO2

Face à Storm-2755, la double authentification par code SMS ou via des applications de type Authenticator s'avère insuffisante. Le moyen de protection ultime consiste à déployer des clés physiques biométriques conformes au standard **FIDO2** (de type **Yubikey**). Seul un lien matériel et cryptographique direct entre le composant physique de sécurité et le domaine officiel de destination est capable de neutraliser l'interception et l'usage frauduleux de l'Evil Token.

---

## Ressources et Consultation

* [Consulter le diaporama de la présentation](https://docs.google.com/presentation/d/1cYntoiHW57iGDPqKY0sPYW8tcJzBTu6WtaIxrLc0AcI/edit?usp=sharing)

#### Sources analysées
- Document de référence : *Microsoft Threat Actor Naming & Threat Intelligence Reports (2026)*.
- Retours d'expérience et analyses d'incidents cyber sur le détournement du protocole *Device Code Flow*.
