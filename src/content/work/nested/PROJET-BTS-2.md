---
title: Mise en place d'un laboratoire de virtualisation et configuration réseau NAT isolé
publishDate: 2026-02-17 00:00:00
img: /assets/LABO-2.png
img_alt: Schéma logique de la connexion réseau virtuelle entre les VM 
description: |
 Installation d'Oracle VirtualBox, déploiement automatisé de Windows 11 par clonage et configuration d'un réseau NAT isolé pour la communication inter-VM.
tags:
  - Projet 2
  - VLAN
  - Réseau NAT
  - DOC TECHNIQUE
---

Dans le cadre de ma formation en BTS SIO option SISR, j'ai réalisé un projet visant à relier virtuelement 2 VM entre elle a l'aide d'un reseau virtuel .

 Pour répondre à ce besoin, j'ai conçu et déployé 2 machine virtuel que j'ai ensuite relier grace a un reseau virtuel.


Compétences techniques mises en œuvre :

Infrastructure : Configuration de bridges Wi-Fi extérieurs et de switches Gigabit pour l'interconnexion de sites.

Réseau : Mise en place d'un plan d'adressage IP statique et gestion des baux DHCP.

Sécurité : Sécurisation des liaisons sans fil via le protocole WPA3 pour prévenir les intrusions.

Maintenance : Tests de connectivité et de bande passante pour garantir la stabilité de la solution.

Outils et matériels utilisés :

Matériel :Lenovo Ideapad 5 sous windows 11.

Systèmes : Windows 11 OS principal, VirtualBox.

Lien du projet 👇

<div class="button-container">
    <a href="/Documents/DOC-TECHNIQUE.pdf" target="_blank" class="btn-gradient">
        Doc technique (PDF)
    </a>
    <a href="/Documents/FICHE-projet-vb-vlan-2pcv.pdf" target="_blank" class="btn-gradient">
        Fiche Projet SIO 1 (PDF)
    </a>
</div>

<style>
    /* Le conteneur qui gère l'alignement et l'espacement */
    .button-container {
        display: flex; 
        justify-content: center; 
        align-items: center; 
        gap: 30px; /* L'espace entre les boutons */
        grid-column: 1 / -1; 
        margin-top: 50px; 
        margin-bottom: 50px;
        width: 100%;
    }

    /* Le style appliqué aux deux boutons */
    .btn-gradient {
        padding: 14px 32px;
        background: linear-gradient(90deg, #b35686 0%, #5d0f8f 100%);
        color: rgb(255, 255, 255);
        text-decoration: none;
        border-radius: 50px;
        font-family: sans-serif;
        font-weight: bold;
        box-shadow: 0px 4px 15px rgba(252, 252, 252, 0.4);
        transition: transform 0.2s ease;
    }

    /* Petit bonus Astro : on peut facilement ajouter un effet au survol de la souris */
    .btn-gradient:hover {
        transform: translateY(-3px);
    }
</style>