# Analyse d’un email de phishing

## Présentation
Dans ce projet, j’analyse un email suspect qui imite Microsoft 365.  
L’objectif est d’identifier les éléments qui montrent qu’il s’agit probablement d’une tentative de phishing.

## Contexte
Un utilisateur reçoit un email indiquant qu’une activité inhabituelle a été détectée sur son compte Microsoft 365.  
Le message demande de cliquer rapidement sur un lien pour vérifier son identité.

## Éléments analysés
- **Objet :** Action requise : activité inhabituelle détectée sur votre compte Microsoft 365
- **Expéditeur :** security-alert@micr0soft-verif.com
- **Lien :** http://microsoft-login-verification-secure.com/verify

## Indicateurs suspects

### 1. L’adresse email paraît fausse
L’expéditeur n’utilise pas un domaine officiel Microsoft.  
Le domaine `micr0soft-verif.com` cherche à imiter Microsoft en remplaçant le **o** par un **0**.

### 2. Le message crée un sentiment d’urgence
L’utilisateur doit agir dans les **30 minutes**.  
C’est une méthode classique utilisée dans les emails de phishing pour pousser la victime à cliquer rapidement.

### 3. Le lien n’est pas légitime
Le lien affiché ne renvoie pas vers un domaine officiel comme `microsoft.com` ou `office.com`.  
Cela laisse penser qu’il peut rediriger vers une fausse page de connexion.

### 4. Le message fait peur à l’utilisateur
L’email menace de suspendre l’accès à Outlook et OneDrive.  
L’objectif est de provoquer une réaction immédiate.

### 5. Le but probable est de voler des identifiants
Même si le mot de passe n’est pas demandé directement dans l’email, le lien peut conduire à une page frauduleuse conçue pour récupérer les identifiants Microsoft 365.

## Conclusion
Cet email présente plusieurs signes typiques d’un phishing :
- imitation d’une marque connue
- adresse expéditeur suspecte
- lien douteux
- sentiment d’urgence
- menace de suspension du compte

Il s’agit très probablement d’un **email malveillant** destiné à voler les identifiants de l’utilisateur.

## Recommandations
- Ne pas cliquer sur le lien
- Ne pas saisir d’identifiants
- Signaler l’email à l’équipe sécurité ou au support IT
- Vérifier si d’autres utilisateurs ont reçu le même message
- Sensibiliser les utilisateurs à ce type de tentative

## Compétences travaillées
- Analyse d’email suspect
- Détection d’indices de phishing
- Triage initial
- Rédaction d’un compte rendu simple
