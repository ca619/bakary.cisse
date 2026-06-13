# Triage d’une alerte SOC

## Présentation
Dans ce projet, je traite une alerte de sécurité liée à plusieurs tentatives de connexion SSH.

Le but est de montrer comment un analyste SOC junior peut lire une alerte, regarder les éléments disponibles, évaluer le risque et proposer une première décision.

## Contexte
Une alerte signale plusieurs échecs de connexion SSH depuis une même adresse IP externe.

Juste après, une connexion réussie apparaît sur le même serveur.  
À première vue, cela peut sembler inquiétant, mais il faut prendre le temps d’analyser les éléments avant de conclure à une compromission.

## Résumé de l’alerte
- **Type d’alerte :** activité SSH suspecte
- **Système concerné :** serveur Linux
- **Éléments déclencheurs :**
  - plusieurs échecs de connexion
  - plusieurs comptes ciblés
  - une connexion réussie observée ensuite

## Ce que j’observe

### 1. Une adresse IP externe revient plusieurs fois
L’adresse IP `185.243.115.84` apparaît à plusieurs reprises en très peu de temps.

Ce comportement peut faire penser à une tentative automatisée ou à une activité de brute force.

### 2. Les comptes visés sont classiques
Les tentatives concernent `admin`, `test` et `root`.

Ce sont des comptes souvent ciblés dans ce type d’activité, car ils sont fréquents ou sensibles.

### 3. Une connexion réussie apparaît ensuite
Une connexion réussie est visible après les échecs, mais elle concerne :
- l’utilisateur `analyste`
- l’adresse IP `192.168.1.20`

Cette adresse semble interne, ce qui change l’interprétation.

### 4. Rien ne prouve ici que l’IP externe a réussi à se connecter
À ce stade, les éléments disponibles montrent une activité suspecte, mais ils ne permettent pas de dire que l’adresse IP externe a réussi à ouvrir une session.

La connexion réussie observée semble venir d’un autre contexte.

## Analyse
L’alerte est intéressante, car elle signale une vraie activité anormale sur SSH.

En revanche, il faut rester prudent.  
Le bon réflexe n’est pas de conclure trop vite à une compromission, mais de distinguer :
- ce qui est réellement suspect
- ce qui est confirmé
- ce qui reste à vérifier

Ici, les tentatives depuis l’IP externe sont suspectes.  
La connexion réussie, elle, semble provenir d’une adresse interne et peut donc être légitime.

## Niveau de sévérité
**Sévérité estimée : moyenne**

Pourquoi :
- l’activité sur SSH est suspecte
- plusieurs comptes ont été testés
- aucune compromission n’est confirmée dans les éléments disponibles
- une vérification complémentaire reste nécessaire

## Décision de triage
**Décision : alerte à investiguer**

Cette alerte ne doit pas être ignorée, mais elle ne permet pas non plus de confirmer une intrusion réussie avec les seuls éléments observés.

## Actions recommandées
- vérifier si l’adresse IP `185.243.115.84` a ciblé d’autres systèmes
- consulter l’historique des connexions SSH
- confirmer que l’utilisateur `analyste` était bien autorisé à se connecter à ce moment-là
- renforcer la surveillance du service SSH
- mettre en place ou vérifier une protection comme Fail2ban
- limiter les accès distants aux comptes sensibles

## Conclusion
Cette alerte montre une activité suspecte cohérente avec une tentative de brute force SSH.

Cependant, la connexion réussie visible dans les événements ne suffit pas à confirmer une compromission, car elle semble provenir d’une autre adresse IP.

Le bon réflexe SOC ici est donc :
- reconnaître l’activité suspecte
- rester prudent
- poursuivre l’analyse avec méthode

## Compétences travaillées
- triage d’alerte SOC
- analyse d’événements de sécurité
- qualification du risque
- distinction entre activité suspecte et compromission confirmée
- rédaction d’un compte rendu simple
