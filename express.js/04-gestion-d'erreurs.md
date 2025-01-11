# Gestion des erreurs dans Express.js

## 1. Capturer et gérer les erreurs
Dans Express, il est possible de capturer les erreurs générées lors de l'exécution des routes ou des middlewares. Lorsqu'une erreur se produit, vous pouvez utiliser la fonction `next()` pour transmettre l'erreur à un middleware de gestion des erreurs.

### Exemple :
```js
app.get('/some-route', (req, res, next) => {
  try {
    // Simuler une erreur
    throw new Error('Une erreur est survenue !');
  } catch (error) {
    next(error);  // Passe l'erreur au middleware de gestion des erreurs
  }
});
```
Ici, si une erreur se produit, elle est envoyée à la fonction `next()` et sera capturée par un middleware de gestion des erreurs.

## 2. Créer un middleware de gestion des erreurs
Un middleware de gestion des erreurs prend 4 arguments : `(err, req, res, next)`. C'est une particularité des middlewares utilisés pour gérer les erreurs.

### Exemple de middleware de gestion des erreurs :
```js
app.use((err, req, res, next) => {
  console.error(err.stack);  // Affiche l'erreur dans la console
  res.status(500).send('Quelque chose a mal tourné !');  // Réponse générique
});
```
Ce middleware capte toutes les erreurs non gérées dans l'application et renvoie une réponse générique avec le code d'état HTTP 500.

## 3. Réponses d'erreur personnalisées
Il est possible de personnaliser les réponses d'erreur en fonction de l'environnement (développement ou production). Par exemple, en développement, vous pouvez afficher des détails sur l'erreur, tandis qu'en production, vous pouvez masquer ces détails pour des raisons de sécurité.

### Exemple de gestion des erreurs personnalisées :
```js
app.use((err, req, res, next) => {
  if (process.env.NODE_ENV === 'development') {
    // En développement, on peut afficher des détails sur l'erreur
    res.status(500).json({
      message: err.message,
      stack: err.stack
    });
  } else {
    // En production, on ne montre que le message d'erreur
    res.status(500).json({ message: 'Erreur interne du serveur' });
  }
});
```