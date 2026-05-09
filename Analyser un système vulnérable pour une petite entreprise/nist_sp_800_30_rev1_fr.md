# NIST SP 800-30 Rev. 1

## Guide d’évaluation des risques

NIST SP 800-30 est une publication qui fournit des orientations pour réaliser des évaluations des risques. Elle présente des stratégies pour identifier, analyser et traiter les risques. Les organisations utilisent NIST SP 800-30 pour mieux comprendre la probabilité potentielle et la gravité des risques, ce qui les aide à prendre des décisions éclairées concernant l’allocation des ressources, la mise en œuvre de contrôles et la priorisation des actions de remédiation.

Ce document de quatre pages est adapté de NIST SP 800-30 Rev. 1. Le terme « Rev. 1 » signifie qu’il s’agit de la première version mise à jour de cette publication. Le NIST révise parfois ses documents afin d’intégrer de nouvelles informations, de refléter les évolutions technologiques et réglementaires ou de répondre aux retours reçus.

Remarque : le Computer Security Resource Center du NIST contient davantage d’informations sur SP 800-30 Rev. 1.

## Sources de menaces

NIST SP 800-30 définit et catégorise les sources de menaces comme des entités ou des circonstances susceptibles d’avoir un impact négatif sur les systèmes d’information d’une organisation. Ces informations sont utiles pour identifier et évaluer les risques potentiels. Lors de leur utilisation, il faut prendre en compte l’intention et les capacités des sources de menaces internes et externes.

Remarque : le tableau suivant présente quelques sources de menaces possibles pouvant compromettre un serveur de base de données accessible publiquement.

| Type | Exemples | Description |
|---|---|---|
| Humain | Utilisateur standard : employé, client. Utilisateur privilégié : administrateur système. Groupe : concurrent, fournisseur, partenaire commercial, État-nation. Acteur externe : pirate informatique, hacktiviste, menace persistante avancée (APT). | Menaces provenant d’individus ou de groupes susceptibles d’exploiter, volontairement ou accidentellement, des ressources cyber. Par exemple, ils pourraient modifier des données d’une manière qui a un impact négatif sur l’entreprise. Ils pourraient aussi voler intentionnellement des données et endommager des équipements professionnels. |
| Technologique | Matériel : stockage, traitement, communications. Logiciels : systèmes d’exploitation, réseau, logiciels malveillants. | Menaces provenant de facteurs non humains. Par exemple, des pannes d’équipement dues au vieillissement, à l’épuisement des ressources ou à d’autres circonstances. |
| Environnemental | Environnement opérationnel : contrôle de la température, contrôle de l’humidité, alimentations électriques défectueuses. Risques naturels : coupures de courant, événements météorologiques extrêmes. | Menaces provenant de facteurs accidentels non humains. Par exemple, des défaillances d’équipement causées par l’environnement opérationnel. |

## Événements de menace

NIST SP 800-30 définit et catégorise les événements de menace comme des situations concrètes dans lesquelles une source de menace exploite une vulnérabilité et cause des dommages ou un préjudice aux systèmes d’information d’une organisation. Ces informations sont utiles pour mieux comprendre les types de risques auxquels les actifs sont exposés. Des contrôles et contre-mesures plus efficaces peuvent être identifiés en comprenant les événements de menace possibles.

Remarque : le tableau suivant présente seulement quelques événements de menace possibles pouvant compromettre un serveur de base de données accessible publiquement.

| Exemples | Description |
|---|---|
| Effectuer une reconnaissance et une surveillance de l’organisation | La source de menace examine et évalue les vulnérabilités de l’entreprise au fil du temps à l’aide de divers moyens, par exemple le balayage, la collecte d’informations ou l’observation physique. |
| Obtenir des informations sensibles par exfiltration | La source de menace installe un logiciel malveillant sur les systèmes de l’organisation afin de localiser et d’acquérir des informations sensibles. |
| Modifier/supprimer des informations critiques | La source de menace modifie ou supprime des données essentielles aux opérations quotidiennes de l’entreprise. |
| Créer des certificats contrefaits | La source de menace compromet une autorité de certification afin de faire paraître ses connexions légitimes. |
| Installer des renifleurs réseau persistants et ciblés sur les systèmes d’information de l’organisation | La source de menace installe un logiciel conçu pour collecter, ou « sniffer », le trafic réseau sur une période prolongée. |
| Mener des attaques par déni de service (DoS) | La source de menace envoie des requêtes automatisées et excessives afin de submerger les capacités opérationnelles du système. |
| Perturber des opérations critiques | La source de menace compromet l’intégrité de l’information de façon à empêcher l’entreprise d’exécuter ses opérations critiques. |
| Masquer de futures attaques | La source de menace prend des mesures visant à réduire l’efficacité des systèmes de détection d’intrusion ou des capacités d’audit de l’entreprise. |
| Mener des attaques de type « homme du milieu » | La source de menace écoute les sessions entre les systèmes internes et externes. Elle relaie ensuite les messages entre les systèmes de l’organisation et des systèmes externes, de sorte que les parties croient communiquer directement sur une connexion privée. |

## Probabilité d’un événement de menace

En général, la probabilité d’un événement de menace doit être une note fondée sur une combinaison de facteurs, comme les preuves disponibles, l’expérience antérieure et le jugement d’expert.

Tenez compte de l’intention et des capacités d’une source de menace ainsi que des événements de menace potentiels lorsque vous attribuez une note de probabilité.

| Valeurs qualitatives | Valeurs quantitatives | Description |
|---|---:|---|
| Élevée | 3 | La source de menace est presque certaine de déclencher un événement de sécurité. Un événement pourrait avoir des effets multiples, graves ou catastrophiques sur les opérations et les actifs de l’entreprise. |
| Modérée | 2 | La source de menace est assez susceptible de déclencher un événement de sécurité. Un événement pourrait réduire de manière importante la fonctionnalité des opérations et des actifs de l’organisation. |
| Faible | 1 | La source de menace est très peu susceptible de déclencher un événement de sécurité. Un événement pourrait avoir des effets mineurs ou négligeables sur les opérations et les actifs de l’entreprise. |

## Gravité d’un événement de menace

En général, la gravité d’un événement de menace mesure son impact potentiel sur les opérations de l’entreprise. Par exemple, l’événement provoquerait-il l’arrêt complet d’une fonction métier ? Pourrait-il perturber temporairement un processus métier sans être immédiatement détecté ?

Tenez compte de l’impact métier des événements de menace lorsque vous attribuez une note de gravité.

| Valeurs qualitatives | Valeurs quantitatives | Description |
|---|---:|---|
| Élevée | 3 | Un événement pourrait avoir des effets multiples, graves ou catastrophiques sur les opérations et les actifs de l’entreprise. |
| Modérée | 2 | Un événement pourrait réduire de manière importante la fonctionnalité des opérations et des actifs de l’organisation. |
| Faible | 1 | Un événement pourrait avoir des effets mineurs ou négligeables sur les opérations et les actifs de l’entreprise. |
