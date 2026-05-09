# Évaluation des vulnérabilités d’un serveur de base de données public

## Présentation du projet

Ce projet présente une évaluation des vulnérabilités réalisée dans le contexte d’une entreprise de commerce électronique.  
L’objectif est d’analyser les risques liés à un serveur de base de données distant accessible publiquement, puis de proposer une stratégie de remédiation adaptée.

Ce type de rapport permet de démontrer des compétences en analyse des risques, identification des menaces, priorisation des vulnérabilités et recommandation de contrôles de sécurité.

---

## Contexte du scénario

Une entreprise de commerce électronique stocke des informations importantes sur un serveur distant de base de données.  
De nombreux employés travaillent à distance dans le monde entier et interrogent régulièrement ce serveur pour rechercher des clients potentiels.

La base de données est ouverte au public depuis le lancement de l’entreprise, il y a trois ans.  
En tant qu’analyste en cybersécurité, cette exposition publique est identifiée comme une vulnérabilité importante, car elle augmente la surface d’attaque et peut permettre à des acteurs malveillants d’accéder au système.

---

## Description du système

Le système évalué est un serveur de base de données distant utilisé par l’entreprise pour stocker et gérer des informations liées aux clients, aux campagnes marketing et aux données analytiques.

Le serveur fonctionne sous Linux et héberge un système de gestion de base de données MySQL.  
Il dispose d’une connexion réseau stable, utilise des adresses IPv4 et communique avec d’autres serveurs de l’environnement informatique.  
Des connexions chiffrées SSL/TLS sont mentionnées comme mesures de sécurité existantes.

---

## Portée de l’évaluation

La portée de cette évaluation concerne principalement les contrôles d’accès actuels du serveur de base de données.  
L’analyse se concentre sur les risques liés à la confidentialité, à l’intégrité et à la disponibilité des données hébergées sur le serveur.

L’évaluation couvre une période de trois mois, de juin 20XX à août 20XX.  
Le référentiel NIST SP 800-30 Rev. 1 est utilisé comme guide pour identifier les sources de menaces, les événements de menaces, la probabilité, la gravité et le niveau de risque.

---

## Objectif

L’objectif de cette analyse est d’évaluer les risques associés à l’exposition publique du serveur de base de données.  
Ce serveur est essentiel pour l’entreprise, car il stocke des données clients, marketing et analytiques utilisées pour soutenir les opérations commerciales et personnaliser les campagnes.  
Sécuriser ces données est important afin d’éviter l’exfiltration d’informations sensibles, la modification non autorisée de données ou l’interruption des activités critiques.  
Si le serveur devenait indisponible ou compromis, l’entreprise pourrait subir des pertes opérationnelles, financières et réputationnelles importantes.

---

## Évaluation des risques

| Source de la menace | Événement de menace | Probabilité | Gravité | Risque |
|---|---|---:|---:|---:|
| Hacker externe | Obtenir des informations sensibles par exfiltration | 3 | 3 | 9 |
| Employé | Perturber des opérations critiques de l’entreprise | 2 | 3 | 6 |
| Client ou utilisateur externe | Modifier ou supprimer des informations critiques | 1 | 3 | 3 |

### Échelle utilisée

| Score | Niveau | Description |
|---:|---|---|
| 1 | Faible | L’événement est peu probable ou aurait un impact limité. |
| 2 | Modéré | L’événement est possible et pourrait perturber les opérations. |
| 3 | Élevé | L’événement est probable ou pourrait avoir un impact majeur. |

**Formule utilisée :**

```text
Risque = Probabilité × Gravité
```

---

## Approche

Les risques ont été sélectionnés en fonction de l’exposition publique du serveur, de la sensibilité des données stockées et de l’importance du système pour les opérations de l’entreprise.  
La probabilité a été évaluée selon la facilité avec laquelle une source de menace pourrait exploiter l’accès public au serveur.  
La gravité a été évaluée selon l’impact potentiel sur la confidentialité, l’intégrité et la disponibilité des données.  
Les limites de cette analyse sont liées au fait qu’elle repose sur le scénario fourni et ne comprend pas de test technique réel, comme un scan de vulnérabilités, une analyse de logs ou un test d’intrusion.

---

## Analyse des risques identifiés

### 1. Exfiltration d’informations sensibles

Le risque le plus élevé concerne l’exfiltration de données sensibles par un hacker externe.  
Comme le serveur est accessible publiquement, un attaquant pourrait tenter d’identifier des faiblesses dans les contrôles d’accès ou dans la configuration du service de base de données.  
Une exfiltration de données pourrait exposer des informations clients, nuire à la réputation de l’entreprise et entraîner des conséquences légales ou financières.

### 2. Perturbation des opérations critiques

Un employé, volontairement ou accidentellement, pourrait perturber des opérations critiques en accédant à des données ou fonctionnalités qui ne sont pas nécessaires à son rôle.  
Ce risque est modéré, car les employés ont probablement un accès légitime au système, mais cet accès peut devenir dangereux s’il n’est pas correctement limité.  
Une erreur de manipulation ou un abus de privilèges pourrait affecter les activités quotidiennes de l’entreprise.

### 3. Modification ou suppression de données critiques

Un client ou utilisateur externe pourrait tenter de modifier ou supprimer des informations critiques si les contrôles d’accès sont insuffisants.  
Même si la probabilité est plus faible, l’impact pourrait être important, car l’intégrité des données est essentielle pour les décisions commerciales.  
Des données altérées pourraient conduire à de mauvaises analyses, à des erreurs opérationnelles ou à une perte de confiance.

---

## Stratégie de remédiation

La première mesure recommandée consiste à retirer l’exposition publique directe du serveur de base de données.  
L’accès au serveur devrait être limité à des adresses IP autorisées, à un VPN d’entreprise ou à un réseau privé sécurisé.  
L’entreprise devrait mettre en place des contrôles d’authentification, d’autorisation et de journalisation afin de vérifier qui accède au serveur, avec quels privilèges et à quel moment.  
L’utilisation de mots de passe forts, de l’authentification multifacteur, du contrôle d’accès basé sur les rôles et du principe du moindre privilège permettrait de réduire les risques d’accès non autorisé.  
Enfin, les connexions devraient utiliser un chiffrement TLS moderne, et les journaux d’accès devraient être surveillés régulièrement à l’aide d’un outil de supervision ou d’un SIEM.

---

## Recommandations de sécurité

- Supprimer l’accès public direct au serveur de base de données.
- Mettre en place une liste d’autorisation d’adresses IP.
- Utiliser un VPN ou un réseau privé pour les connexions distantes.
- Appliquer le principe du moindre privilège.
- Mettre en place une authentification multifacteur pour les comptes sensibles.
- Utiliser le contrôle d’accès basé sur les rôles.
- Renforcer les mots de passe et désactiver les comptes inutilisés.
- Activer une journalisation complète des connexions et des requêtes sensibles.
- Surveiller les journaux avec un SIEM ou une solution de détection.
- Utiliser TLS pour protéger les données en transit.
- Mettre en place des sauvegardes régulières et tester leur restauration.
- Corriger régulièrement le système d’exploitation, MySQL et les composants associés.

---

## Compétences démontrées

Ce projet démontre les compétences suivantes :

- Compréhension d’un scénario de vulnérabilité.
- Identification des sources de menaces.
- Identification des événements de menaces.
- Évaluation de la probabilité et de la gravité.
- Calcul d’un niveau de risque.
- Utilisation d’une approche inspirée du NIST SP 800-30 Rev. 1.
- Rédaction d’un rapport d’évaluation des vulnérabilités.
- Proposition de mesures de remédiation réalistes.
- Communication des risques à des décideurs non techniques.

---

## Conclusion

Cette évaluation montre qu’un serveur de base de données exposé publiquement représente un risque important pour une entreprise de commerce électronique.  
Les risques les plus critiques concernent l’exfiltration de données sensibles, la perturbation des opérations et la modification ou suppression d’informations critiques.

La mise en place de contrôles d’accès stricts, d’une authentification renforcée, d’une segmentation réseau et d’une surveillance continue permettrait de réduire fortement la probabilité d’un incident.  
Ce projet illustre l’importance d’évaluer régulièrement les vulnérabilités afin de protéger les actifs critiques de l’entreprise.
