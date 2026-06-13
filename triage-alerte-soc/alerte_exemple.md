# Exemple d’alerte SOC

## Nom de l’alerte
Plusieurs échecs de connexion SSH suivis d’une connexion réussie

## Source
SIEM / journaux Linux

## Horodatage
12 juin 2026 entre 02:11 et 02:12

## Description
Une alerte a été déclenchée après plusieurs tentatives de connexion SSH échouées depuis une même adresse IP externe.

Quelques secondes plus tard, une connexion réussie apparaît sur le même serveur.

## Éléments observés
- plusieurs échecs de connexion SSH depuis `185.243.115.84`
- comptes visés : `admin`, `test`, `root`
- une connexion réussie pour l’utilisateur `analyste`
- adresse IP de cette connexion : `192.168.1.20`

## Première impression
Cette alerte fait penser à une tentative de brute force sur le service SSH.

La connexion réussie qui suit doit être vérifiée, car il faut déterminer si elle est liée à l’activité suspecte précédente ou si elle correspond à une connexion légitime.
