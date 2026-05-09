# Gestion des autorisations de fichiers sous Linux

## Présentation du projet

Ce projet présente une activité de durcissement des permissions de fichiers sous Linux dans un contexte professionnel. Le scénario se déroule au sein d’une grande organisation où l’équipe de recherche utilise un répertoire `projects` pour stocker des fichiers de travail. En tant que professionnel de la sécurité, l’objectif est de vérifier les autorisations existantes, d’identifier les accès excessifs et de modifier les permissions afin de supprimer les accès non autorisés.

Le projet démontre l’utilisation de commandes Linux pour examiner les permissions, interpréter les chaînes d’autorisation, modifier les droits d’accès avec `chmod` et appliquer le principe du moindre privilège.

---

## Objectifs

- Vérifier les permissions des fichiers et répertoires sous Linux.
- Comprendre la chaîne de permissions Linux sur 10 caractères.
- Identifier les fichiers avec des permissions excessives.
- Modifier les droits d’accès avec la commande `chmod`.
- Sécuriser un fichier caché et un répertoire sensible.
- Documenter les actions réalisées dans un format professionnel adapté à un portfolio cybersécurité.

---

## Contexte du scénario

L’équipe de recherche de l’organisation utilise le répertoire suivant :

```bash
/home/researcher2/projects
```

Certains fichiers et répertoires possèdent des autorisations qui ne correspondent pas au niveau d’accès attendu. Il est nécessaire de vérifier les permissions actuelles, puis de les corriger afin que seuls les utilisateurs autorisés puissent lire, modifier ou exécuter les fichiers concernés.

---

## 1. Vérification des détails des fichiers et répertoires

Pour afficher les fichiers, les répertoires, les fichiers cachés et leurs permissions, j’ai utilisé la commande suivante :

```bash
ls -la /home/researcher2/projects
```

L’option `-l` permet d’afficher les détails des fichiers, notamment les permissions, le propriétaire, le groupe, la taille et la date de modification. L’option `-a` permet d’afficher tous les fichiers, y compris les fichiers cachés qui commencent par un point, comme `.project_x.txt`.

Exemple de permissions observées :

```text
-rw-rw-rw-  project_k.txt
-rw-r-----  project_m.txt
-rw-rw-r--  project_r.txt
-rw-rw-r--  project_t.txt
-rw--w----  .project_x.txt
drwx--x---  drafts
```

Cette sortie permet d’identifier les fichiers ayant des permissions trop permissives, notamment `project_k.txt`, qui autorise les autres utilisateurs à écrire dans le fichier.

---

## 2. Description de la chaîne de permissions

Sous Linux, les permissions sont représentées par une chaîne de 10 caractères. Cette chaîne permet de comprendre rapidement le type de ressource et les droits accordés à chaque catégorie d’utilisateur.

Exemple :

```text
-rw-rw-r--
```

La chaîne se lit de la manière suivante :

| Position | Signification |
|---|---|
| 1er caractère | Type de ressource : `-` pour un fichier, `d` pour un répertoire |
| 2e à 4e caractères | Permissions de l’utilisateur propriétaire |
| 5e à 7e caractères | Permissions du groupe |
| 8e à 10e caractères | Permissions des autres utilisateurs |

Les permissions possibles sont :

| Lettre | Signification |
|---|---|
| `r` | Lecture |
| `w` | Écriture |
| `x` | Exécution |
| `-` | Permission non accordée |

Pour l’exemple `-rw-rw-r--`, il s’agit d’un fichier classique. L’utilisateur propriétaire peut lire et modifier le fichier, le groupe peut également lire et modifier le fichier, tandis que les autres utilisateurs peuvent seulement le lire.

---

## 3. Modification des permissions d’un fichier

L’organisation ne souhaite pas que les autres utilisateurs disposent d’un accès en écriture sur les fichiers du répertoire `projects`. Après vérification, le fichier `project_k.txt` possède les permissions suivantes :

```text
-rw-rw-rw-
```

Cette configuration indique que l’utilisateur, le groupe et les autres utilisateurs peuvent lire et modifier le fichier. Le droit d’écriture accordé aux autres utilisateurs représente un risque, car une personne non autorisée pourrait modifier le contenu du fichier.

Pour supprimer le droit d’écriture des autres utilisateurs, j’ai utilisé la commande suivante :

```bash
chmod o-w /home/researcher2/projects/project_k.txt
```

Vérification après modification :

```bash
ls -la /home/researcher2/projects/project_k.txt
```

Résultat attendu :

```text
-rw-rw-r--  project_k.txt
```

Le fichier est maintenant plus sécurisé, car les autres utilisateurs peuvent uniquement le lire et ne peuvent plus le modifier.

---

## 4. Modification des permissions d’un fichier caché

Le fichier `.project_x.txt` est un fichier caché, car son nom commence par un point. Ce fichier a été archivé par l’équipe de recherche. Il ne doit donc plus être modifiable par qui que ce soit, mais l’utilisateur propriétaire et le groupe doivent encore pouvoir le lire.

Permissions initiales observées :

```text
-rw--w----  .project_x.txt
```

Cette configuration indique que l’utilisateur propriétaire peut lire et écrire, tandis que le groupe peut écrire sans avoir le droit de lecture. Cette configuration n’est pas adaptée pour un fichier archivé.

Pour retirer les droits d’écriture et accorder la lecture au groupe, j’ai utilisé la commande suivante :

```bash
chmod u-w,g-w,g+r /home/researcher2/projects/.project_x.txt
```

Une autre commande équivalente serait :

```bash
chmod 440 /home/researcher2/projects/.project_x.txt
```

Vérification après modification :

```bash
ls -la /home/researcher2/projects/.project_x.txt
```

Résultat attendu :

```text
-r--r-----  .project_x.txt
```

Le fichier caché est maintenant en lecture seule pour l’utilisateur propriétaire et le groupe. Les autres utilisateurs n’ont aucun accès.

---

## 5. Modification des permissions d’un répertoire

Le répertoire `drafts` contient des fichiers de travail qui ne doivent être accessibles qu’à l’utilisateur `researcher2`. Les autres utilisateurs et le groupe ne doivent pas avoir de droit d’exécution sur ce répertoire, car le droit `x` sur un répertoire permet d’y accéder.

Permissions initiales observées :

```text
drwx--x---  drafts
```

Cette configuration indique que l’utilisateur propriétaire possède les droits de lecture, écriture et exécution, mais que le groupe possède également le droit d’exécution. Il faut donc retirer ce droit au groupe.

Commande utilisée :

```bash
chmod g-x /home/researcher2/projects/drafts
```

Une autre commande équivalente serait :

```bash
chmod 700 /home/researcher2/projects/drafts
```

Vérification après modification :

```bash
ls -la /home/researcher2/projects
```

Résultat attendu :

```text
drwx------  drafts
```

Le répertoire `drafts` est maintenant accessible uniquement par l’utilisateur propriétaire `researcher2`.

---

## Synthèse des changements effectués

| Élément | Permission initiale | Problème identifié | Commande utilisée | Permission finale attendue |
|---|---:|---|---|---:|
| `project_k.txt` | `-rw-rw-rw-` | Les autres utilisateurs avaient un accès en écriture | `chmod o-w project_k.txt` | `-rw-rw-r--` |
| `.project_x.txt` | `-rw--w----` | Fichier archivé encore modifiable | `chmod u-w,g-w,g+r .project_x.txt` | `-r--r-----` |
| `drafts` | `drwx--x---` | Le groupe pouvait accéder au répertoire | `chmod g-x drafts` | `drwx------` |

---

## Compétences démontrées

- Utilisation de la commande `ls -la` pour auditer les permissions Linux.
- Interprétation des chaînes de permissions Linux.
- Identification de droits excessifs sur des fichiers et répertoires.
- Utilisation de `chmod` pour modifier les permissions.
- Application du principe du moindre privilège.
- Sécurisation d’un fichier caché.
- Sécurisation d’un répertoire contenant des données sensibles.
- Documentation claire des actions techniques réalisées.

---

## Résumé

Dans ce projet, j’ai vérifié les autorisations des fichiers et répertoires situés dans `/home/researcher2/projects`. J’ai utilisé `ls -la` pour afficher les permissions existantes, y compris celles des fichiers cachés, puis j’ai interprété les chaînes de permissions afin d’identifier les accès non conformes.

J’ai ensuite utilisé la commande `chmod` pour supprimer les droits d’écriture inutiles, sécuriser un fichier caché archivé et limiter l’accès au répertoire `drafts` uniquement à l’utilisateur autorisé. Ces actions permettent de réduire les risques de modification non autorisée et d’améliorer la sécurité du système Linux.
