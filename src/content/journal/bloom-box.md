---
title: WPA3 DragonBlood hack method 
publishDate: 2025-12-02 13:00:00
img: /assets/DRAGONBLOOD.png
img_alt: DRAGONBLOOD
description: |
  Dragonfly-DragonBlood
tags:
  - Connection
  - WPA3
  - Downgrade
  - DragonBlood
---

Les vulnérabilités Dragonblood sont une série de failles de sécurité découvertes dans le protocole WPA3, notamment dans son mécanisme d'authentification Dragonfly.  Elles ont été identifiées par les chercheurs Mathy Vanhoef et Eyal Ronen, les mêmes qui avaient découvert la faille KRACK sur WPA2. 

Nature des vulnérabilités
Dragonblood n'est pas une seule faille, mais cinq défauts de conception regroupés en deux catégories principales :


Attaques de rétrogradation : Permettent à un attaquant de forcer un appareil WPA3 à se connecter via WPA2, rendant possible une attaque par dictionnaire sur le handshake partiel. 

Attaques par canaux auxiliaires (side-channel) : Exploitent des fuites d'information via le temps d'exécution ou l'accès à la mémoire (cache), permettant de deviner progressivement le mot de passe. 

Impact
Un attaquant proche du réseau peut récupérer le mot de passe Wi-Fi. 
Les données sensibles (mots de passe, messages, informations bancaires) peuvent être compromises.

Ces vulnérabilités affectent aussi EAP-pwd, utilisé dans les réseaux WPA2 et WPA3 pour la rétrocompatibilité. 

Correctifs et mises à jour
La WiFi Alliance a publié des mises à jour de sécurité pour corriger ces failles. 
Les fabricants ont dû intégrer des correctifs via des mises à jour de firmware. 
Des correctifs sont disponibles pour des équipements comme FortiOS, Meru AP/Controller, et d'autres appareils.

Avertissements
Les vulnérabilités ont été confirmées sur des appareils récents, notamment le Samsung Galaxy S10. 

Le processus de développement fermé de la WiFi Alliance a été critiqué pour avoir empêché une vérification plus large par la communauté open-source. 
Important : Bien que les correctifs existent, les réseaux non mis à jour restent vulnérables.  Il est essentiel de vérifier que les routeurs et appareils sont équipés des derniers firmware.

Pour plus d'information:
https://www.zdnet.fr/actualites/dragonblood-de-nouvelles-vulnerabilites-trouvees-dans-le-standard-wifi-wpa3-39888783.htm


