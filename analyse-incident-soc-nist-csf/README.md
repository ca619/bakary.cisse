# Analyse d'incident SOC avec le NIST CSF

## Présentation

Ce projet présente une analyse d’incident de cybersécurité basée sur le **NIST Cybersecurity Framework (CSF)**.

Le scénario porte sur une entreprise victime d’une **attaque par déni de service (DoS/DDoS)** provoquée par une **inondation de paquets ICMP**, ayant perturbé les services du réseau interne. Cette étude de cas montre comment analyser l’incident à travers les cinq fonctions principales du NIST CSF :

- Identifier
- Protéger
- Détecter
- Réagir
- Rétablir

---

## Résumé du scénario

Une entreprise multimédia a subi une interruption de service réseau après qu’un acteur malveillant a saturé le réseau interne avec du **trafic ICMP**.

L’équipe de réponse à incident a limité l’impact en :

- bloquant le trafic ICMP entrant,
- arrêtant les services réseau non critiques,
- restaurant les services critiques.

Après investigation, l’équipe cybersécurité a identifié des faiblesses de configuration du pare-feu et a proposé plusieurs améliorations de sécurité, notamment :

- une nouvelle règle de pare-feu pour limiter le trafic ICMP entrant,
- la vérification de l’adresse IP source,
- la surveillance du réseau,
- un filtrage par IDS/IPS.

---

## Objectifs

Ce projet permet de démontrer ma capacité à :

- analyser un incident de sécurité réseau,
- appliquer le **NIST CSF** à un cas concret,
- documenter clairement des constats techniques,
- proposer des mesures d’amélioration après incident.

---

## Analyse selon le NIST CSF

### 1. Identifier
L’organisation a été touchée par une **attaque par inondation ICMP** ayant perturbé l’ensemble du réseau interne.  
Les services critiques et les ressources réseau ont été affectés et devaient être sécurisés puis restaurés.

### 2. Protéger
Pour réduire le risque de récurrence, l’entreprise a mis en place :

- une règle de pare-feu pour limiter le trafic ICMP entrant,
- une solution IDS/IPS pour filtrer les paquets ICMP suspects.

### 3. Détecter
Pour améliorer la visibilité et les capacités de détection, l’entreprise a ajouté :

- une vérification de l’adresse IP source sur le pare-feu,
- un logiciel de surveillance réseau pour repérer les schémas de trafic anormaux.

### 4. Réagir
En cas d’incident futur, l’équipe sécurité devra :

- isoler les systèmes affectés,
- analyser les journaux réseau,
- restaurer d’abord les services critiques,
- informer la direction et les parties concernées si nécessaire.

### 5. Rétablir
Les actions de rétablissement incluent :

- le retour à un fonctionnement normal du réseau,
- la remise en service prioritaire des systèmes critiques,
- la remise en ligne progressive des services non critiques,
- l’amélioration continue des procédures de reprise.

---

## Compétences mises en avant

- Analyse d’incident
- Fondamentaux de la sécurité réseau
- Compréhension d’une attaque DDoS / ICMP flood
- Concepts de pare-feu et IDS/IPS
- Application du NIST CSF
- Rédaction de documentation sécurité

---

## Outils / Concepts abordés

- NIST Cybersecurity Framework (CSF)
- Règles de pare-feu
- Vérification IP source
- Surveillance réseau
- IDS/IPS
- Réponse à incident

---

## Pourquoi ce projet est pertinent

Ce projet met en avant ma capacité à analyser un événement de sécurité de manière structurée et à relier les constats techniques à un cadre reconnu en cybersécurité.

Il reflète les compétences attendues d’un futur **analyste SOC junior** ou profil **Blue Team** : comprendre l’incident, identifier la cause, proposer des mesures défensives réalistes et documenter l’ensemble proprement.

---

## Auteur

**Bakary**  
Futur Analyste SOC | Blue Team | Apprenant en cybersécurité
