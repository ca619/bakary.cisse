# Checklist — Contrôles et conformité

## 1. Contrôles de sécurité

| Contrôle | Statut actuel | Commentaire |
|---|---|---|
| Moindre privilège | Non | Tous les employés ont accès aux données clients. |
| Plans de reprise après sinistre | Non | Aucun plan formalisé actuellement. |
| Politiques de mot de passe | Non / insuffisant | Exigences minimales trop faibles. |
| Séparation des tâches | Non | Risque de fraude et de concentration des responsabilités. |
| Pare-feu | Oui | Règles de sécurité définies et appliquées. |
| Système de détection d’intrusion (IDS) | Non | Contrôle manquant pour la détection d’intrusions. |
| Sauvegardes | Non | Absence de sauvegardes critiques. |
| Logiciel antivirus | Oui | Installé et surveillé régulièrement. |
| Surveillance / maintenance des systèmes hérités | Partiel | Activité réalisée mais sans calendrier clair ni procédures nettes. |
| Chiffrement | Non | Données sensibles non chiffrées. |
| Système de gestion des mots de passe | Non | Aucun outil centralisé actuellement. |
| Serrures physiques | Oui | Contrôle physique présent. |
| Vidéosurveillance (CCTV) | Oui | Présente et fonctionnelle. |
| Détection / prévention incendie | Oui | Système fonctionnel sur site. |

## 2. Conformité PCI DSS

| Bonne pratique | Conforme ? | Commentaire |
|---|---|---|
| Seuls les utilisateurs autorisés accèdent aux données de carte bancaire | Non | Tous les employés ont accès aux données internes. |
| Les données carte sont stockées, traitées et transmises dans un environnement sécurisé | Non | Pas de chiffrement et contrôle d’accès insuffisant. |
| Des procédures de chiffrement protègent les points de contact de paiement | Non | Le chiffrement n’est pas utilisé. |
| Des politiques de gestion des mots de passe sécurisées sont en place | Non | Politique faible et pas de gestionnaire dédié. |

## 3. Conformité RGPD

| Bonne pratique | Conforme ? | Commentaire |
|---|---|---|
| Les données des clients UE sont protégées | Non | Confidentialité insuffisante faute de chiffrement. |
| Notification sous 72 heures en cas de violation | Oui | Un plan est indiqué comme existant. |
| Les données sont classifiées et inventoriées | Partiel / Non | Les actifs sont inventoriés, mais pas classifiés. |
| Les politiques et procédures de confidentialité sont appliquées | Oui | Politiques et processus présents. |

## 4. Conformité SOC 1 / SOC 2

| Bonne pratique | Conforme ? | Commentaire |
|---|---|---|
| Les politiques d’accès utilisateur sont établies | Non | Le moindre privilège et la séparation des tâches ne sont pas en place. |
| Les données sensibles sont confidentielles / privées | Non | Le chiffrement n’est pas utilisé. |
| L’intégrité des données est assurée | Oui | L’intégrité est annoncée comme en place. |
| Les données sont disponibles pour les personnes autorisées | Non | Les accès ne sont pas correctement limités. |

## 5. Synthèse

### Contrôles à implémenter en priorité
- Moindre privilège
- Séparation des tâches
- Chiffrement
- Sauvegardes
- Plan de reprise après sinistre
- IDS
- Gestionnaire de mots de passe
- Gestion formalisée des systèmes hérités

### Bénéfices attendus
- Réduction du risque de violation de données
- Amélioration de la conformité réglementaire
- Renforcement de la résilience opérationnelle
- Meilleure gouvernance des accès et des actifs
