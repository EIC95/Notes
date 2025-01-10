# Node.js Envoi d'Email

## Le module Nodemailer

Le module **Nodemailer** permet d'envoyer facilement des emails depuis ton ordinateur.

Tu peux installer ce module via npm :

```bash
C:\Users\Ton Nom>npm install nodemailer
```

Une fois installé, tu peux l'inclure dans ton application avec cette ligne de code :

```javascript
let nodemailer = require('nodemailer');
```

---

## Envoyer un Email

Maintenant, tu es prêt à envoyer des emails depuis ton serveur.

Utilise le nom d'utilisateur et le mot de passe de ton fournisseur de messagerie pour envoyer un email. Cet exemple montre comment utiliser un compte Gmail pour envoyer un email.

Voici un exemple complet :

```javascript
let nodemailer = require('nodemailer');

let transporter = nodemailer.createTransport({
  service: 'gmail',
  auth: {
    user: 'tonemail@gmail.com',
    pass: 'tonmotdepasse'
  }
});

let mailOptions = {
  from: 'tonemail@gmail.com',
  to: 'monami@yahoo.com',
  subject: 'Envoyer un Email avec Node.js',
  text: 'C\'était facile !'
};

transporter.sendMail(mailOptions, function(error, info){
  if (error) {
    console.log(error);
  } else {
    console.log('Email envoyé : ' + info.response);
  }
});
```

---

## Envoyer à Plusieurs Destinataires

Pour envoyer un email à plusieurs destinataires, il suffit d'ajouter leurs adresses dans la propriété **to** de l'objet `mailOptions`, séparées par des virgules.

Voici un exemple :

```javascript
let mailOptions = {
  from: 'tonemail@gmail.com',
  to: 'monami@yahoo.com, monautreami@yahoo.com',
  subject: 'Envoyer un Email avec Node.js',
  text: 'C\'était facile !'
};
```

---

## Envoyer du HTML

Si tu souhaites envoyer un email contenant du texte formaté en HTML, utilise la propriété **html** au lieu de **text**.

Voici un exemple d'email contenant du HTML :

```javascript
let mailOptions = {
  from: 'tonemail@gmail.com',
  to: 'monami@yahoo.com',
  subject: 'Envoyer un Email avec Node.js',
  html: '<h1>Bienvenue</h1><p>C\'était facile !</p>'
};
```
