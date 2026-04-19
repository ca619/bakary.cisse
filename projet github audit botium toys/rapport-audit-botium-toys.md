# Rapport d’audit — Botium Toys

## 1. Contexte

Cet audit porte sur les contrôles de sécurité et les bonnes pratiques de conformité de **Botium Toys**.  
L’objectif est d’identifier les lacunes de sécurité, les risques principaux et les mesures à mettre en œuvre pour améliorer la posture globale de l’entreprise.

## 2. Portée

L’audit couvre l’ensemble du programme de sécurité de l’organisation, notamment :

- les équipements sur site,
- les équipements des employés,
- les produits du magasin et de l’entrepôt,
- les systèmes et services gérés par l’IT,
- l’accès Internet,
- le réseau interne,
- la rétention et le stockage des données,
- la maintenance des systèmes hérités.

## 3. Niveau de risque

Le niveau de risque est considéré comme **élevé**, avec un score de **8/10**.

### Raisons principales

- gestion insuffisante des actifs,
- contrôles incomplets ou absents,
- conformité partielle aux standards et réglementations,
- accès trop larges aux données internes,
- absence de chiffrement pour des données sensibles.

## 4. Contrôles en place

Les contrôles suivants sont déjà présents :

- **Pare-feu**
- **Antivirus**
- **Serrures** sur les sites physiques
- **Vidéosurveillance (CCTV)**
- **Détection / prévention incendie**

Ces mesures apportent une base de protection, mais elles restent insuffisantes pour répondre au niveau de risque global.

## 5. Contrôles absents ou insuffisants

### Gouvernance et accès
- Moindre privilège : **absent**
- Séparation des tâches : **absente**
- Politique de mots de passe : **insuffisante**
- Système de gestion des mots de passe : **absent**

### Résilience et continuité
- Sauvegardes : **absentes**
- Plan de reprise après sinistre : **absent**

### Détection et surveillance
- IDS : **absent**
- Gestion des systèmes hérités : **présente mais non formalisée**

### Protection des données
- Chiffrement : **absent**

## 6. Analyse conformité

### PCI DSS
Écarts identifiés :

- accès non restreint aux données de carte bancaire,
- absence de chiffrement,
- environnement interne insuffisamment sécurisé,
- gestion des mots de passe non conforme aux bonnes pratiques.

### RGPD
Points partiellement conformes :

- plan de notification sous 72 heures : **présent**
- politiques de confidentialité : **présentes**

Écarts :

- données non suffisamment protégées,
- actifs non classifiés,
- confidentialité insuffisante faute de chiffrement.

### SOC 1 / SOC 2
Points positifs :

- intégrité des données annoncée comme assurée.

Écarts :

- politiques d’accès insuffisantes,
- confidentialité des données sensibles insuffisante,
- accès trop larges aux données.

## 7. Recommandations prioritaires

### Priorité 1 — Réduction immédiate du risque
- Mettre en œuvre le **moindre privilège**
- Déployer le **chiffrement**
- Limiter l’accès aux données de cartes et aux données sensibles
- Mettre en place la **séparation des tâches**

### Priorité 2 — Résilience opérationnelle
- Déployer des **sauvegardes régulières**
- Rédiger et tester un **plan de reprise après sinistre**

### Priorité 3 — Détection et durcissement
- Déployer un **IDS**
- Formaliser la supervision et la maintenance des **systèmes hérités**
- Renforcer la politique de mot de passe
- Déployer un **gestionnaire de mots de passe**

### Priorité 4 — Gouvernance et conformité
- Classifier les actifs
- Mettre à jour l’inventaire
- Aligner les contrôles avec PCI DSS, RGPD et SOC 1/SOC 2

## 8. Conclusion

Botium Toys dispose de quelques contrôles de base, mais l’organisation présente encore plusieurs lacunes critiques en matière d’accès, de protection des données, de résilience et de conformité.

La mise en œuvre des contrôles recommandés permettrait de réduire fortement le risque de compromission, d’améliorer la continuité d’activité et de renforcer la conformité réglementaire.
