# Audit sécurité et conformité — Botium Toys

Ce dépôt présente un exercice d’audit sécurité réalisé autour de l’entreprise fictive **Botium Toys**.

L’idée était d’analyser les contrôles déjà en place, d’identifier les points faibles, puis de proposer des recommandations simples et prioritaires pour améliorer la posture de sécurité.

## Pourquoi j’ai fait ce projet

J’ai créé ce projet pour m’entraîner à lire une situation d’entreprise, repérer les contrôles manquants et structurer un rendu clair en français.

Ce travail m’a permis de pratiquer :

- l’analyse de risques,
- la lecture d’une checklist de contrôle,
- l’identification d’écarts de conformité,
- la rédaction d’un rapport simple et compréhensible.

## Ce qu’on retrouve dans le dépôt

```text
botium-toys-audit-fr-github-project/
├── README.md
└── docs/
    ├── rapport-audit-botium-toys.md
    └── checklist-controles-conformite.md
```

## Résumé rapide

L’audit montre que Botium Toys possède déjà quelques mesures de base, comme un **pare-feu**, un **antivirus**, des **serrures physiques**, la **vidéosurveillance** et un système de **détection/prévention incendie**.  

En revanche, plusieurs éléments importants manquent encore, notamment :

- le **moindre privilège**,
- la **séparation des tâches**,
- le **chiffrement**,
- les **sauvegardes**,
- un **plan de reprise après sinistre**,
- un **IDS**,
- une meilleure **gestion des mots de passe**,
- une gestion plus claire des **systèmes hérités**.

## Points de conformité étudiés

Ce projet aborde aussi les écarts liés à plusieurs référentiels et exigences :

- **PCI DSS**
- **RGPD**
- **SOC 1 / SOC 2**

Les principaux problèmes concernent surtout le contrôle d’accès, la protection des données sensibles et le manque de chiffrement.

## Ce que je retiens de cet exercice

Ce projet montre qu’une entreprise peut avoir quelques protections visibles, tout en restant exposée sur des points essentiels comme les accès, la continuité d’activité ou la confidentialité des données.

Il montre aussi qu’un audit ne consiste pas seulement à dire ce qui manque, mais à prioriser ce qu’il faut corriger en premier.

## Fichiers principaux

- `docs/rapport-audit-botium-toys.md` : synthèse de l’audit
- `docs/checklist-controles-conformite.md` : vue structurée des contrôles et des écarts de conformité

## Remarque

Le contexte utilisé ici est basé sur un cas pratique pédagogique. 
