# Rapport d’évaluation des vulnérabilités

**Date :** 1er janvier 20XX

## Description du système

Le matériel du serveur se compose d’un processeur puissant et de 128 Go de mémoire. Il fonctionne avec la dernière version du système d’exploitation Linux et héberge un système de gestion de base de données MySQL. Il est configuré avec une connexion réseau stable utilisant des adresses IPv4 et interagit avec d’autres serveurs du réseau. Les mesures de sécurité comprennent des connexions chiffrées SSL/TLS.

## Portée

La portée de cette évaluation des vulnérabilités concerne les contrôles d’accès actuels du système. L’évaluation couvrira une période de trois mois, de juin 20XX à août 20XX. Le guide NIST SP 800-30 Rev. 1 est utilisé pour orienter l’analyse des risques du système d’information.

## Objectif

Le serveur de base de données est un système informatique centralisé qui stocke et gère de grandes quantités de données. Le serveur est utilisé pour stocker des données clients, de campagnes et d’analyse qui peuvent ensuite être analysées pour suivre les performances et personnaliser les efforts marketing. Il est essentiel de sécuriser ce système en raison de son utilisation régulière pour les opérations marketing.

## Évaluation des risques

| Source de menace | Événement de menace | Probabilité | Gravité | Risque |
|---|---|---:|---:|---:|
| Pirate informatique | Obtenir des informations sensibles par exfiltration | 3 | 3 | 9 |
| Employé | Perturber les opérations critiques | 2 | 3 | 6 |
| Client | Modifier/supprimer des informations critiques | 1 | 3 | 3 |

## Approche

Les risques mesurés ont pris en compte les procédures de stockage et de gestion des données de l’entreprise. Les sources et événements de menace potentiels ont été déterminés selon la probabilité d’un incident de sécurité, compte tenu des autorisations d’accès ouvertes du système d’information. La gravité des incidents potentiels a été évaluée par rapport à leur impact sur les besoins opérationnels quotidiens.

## Stratégie de remédiation

Mise en œuvre de mécanismes d’authentification, d’autorisation et d’audit afin de garantir que seuls les utilisateurs autorisés accèdent au serveur de base de données. Cela comprend l’utilisation de mots de passe robustes, de contrôles d’accès basés sur les rôles et de l’authentification multifacteur afin de limiter les privilèges des utilisateurs. Les données en transit doivent être chiffrées avec TLS plutôt qu’avec SSL. Une liste d’autorisation d’adresses IP limitée aux bureaux de l’entreprise doit être mise en place afin d’empêcher des utilisateurs aléatoires sur Internet de se connecter à la base de données.
