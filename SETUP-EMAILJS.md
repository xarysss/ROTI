# Configuration EmailJS pour Tiro Network

## 🚀 Guide d'installation EmailJS

### 1. Créer un compte EmailJS

1. Allez sur [https://www.emailjs.com/](https://www.emailjs.com/)
2. Créez un compte gratuit
3. Vérifiez votre email

### 2. Configurer le service email

1. Dans le dashboard EmailJS, allez dans **Email Services**
2. Cliquez sur **Add New Service**
3. Choisissez **Gmail** (recommandé)
4. Connectez votre compte Gmail `titouanmouysset@gmail.com`
5. Notez l'**Service ID** (ex: `service_xxxxx`)

### 3. Créer un template d'email

1. Allez dans **Email Templates**
2. Cliquez sur **Create New Template**
3. Utilisez ce template :

**Sujet :**
```
Nouveau message de contact - Tiro Network
```

**Contenu :**
```
Bonjour,

Vous avez reçu un nouveau message de contact depuis votre site web Tiro Network :

👤 Nom: {{from_name}}
📧 Email: {{from_email}}
🎯 Objectif: {{objective}}
🏢 Activité: {{activity}}

💬 Message:
{{message}}

---
Ce message a été envoyé depuis le formulaire de contact de votre site web.
```

4. Notez l'**Template ID** (ex: `template_xxxxx`)

### 4. Récupérer votre clé publique

1. Allez dans **Account** > **API Keys**
2. Copiez votre **Public Key** (ex: `xxxxxxxxxxxxxxxx`)

### 5. Configurer le fichier email-config.js

Ouvrez le fichier `email-config.js` et remplacez :

```javascript
const EMAIL_CONFIG = {
    PUBLIC_KEY: 'VOTRE_PUBLIC_KEY_ICI',
    SERVICE_ID: 'VOTRE_SERVICE_ID_ICI',
    TEMPLATE_ID: 'VOTRE_TEMPLATE_ID_ICI',
    TO_EMAIL: 'titouanmouysset@gmail.com'
};
```

### 6. Variables du template

Les variables suivantes sont automatiquement envoyées :
- `{{from_name}}` : Prénom + Nom du client
- `{{from_email}}` : Email du client
- `{{objective}}` : Objectif sélectionné
- `{{activity}}` : Activité sélectionnée
- `{{message}}` : Message du client
- `{{to_email}}` : Votre email de destination

### 7. Test

1. Ouvrez votre site web
2. Allez sur la page de contact
3. Remplissez le formulaire
4. Vérifiez que l'email arrive bien dans `titouanmouysset@gmail.com`

### 🎉 C'est terminé !

Votre formulaire de contact enverra maintenant directement les emails à votre adresse Gmail.

## Limites du plan gratuit

- 200 emails/mois
- 2 services email
- Templates illimités

## Support

Si vous avez des problèmes :
1. Vérifiez la console du navigateur (F12)
2. Assurez-vous que toutes les clés sont correctes
3. Vérifiez que le service Gmail est bien activé dans EmailJS
