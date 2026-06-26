# SenePay Embed Button v1.0.0

© 2026 Millennium Capital Invest LLC — Tous droits réservés.

## Bouton de paiement SenePay intégrable

Intégrez un bouton de paiement SenePay en une seule ligne de code HTML.

## Utilisation

```html
<!-- Charger le script SenePay -->
<script src="https://cdn.sene-pay.com/button.js"></script>

<!-- Bouton de paiement -->
<div class="senepay-button"
     data-amount="5000"
     data-currency="XOF"
     data-api-key="votre_cle_api"
     data-description="Facture Pro #1234"
     data-order-id="ORDER-1234"
     data-return-url="https://votre-domaine.com/confirmation"
     data-cancel-url="https://votre-domaine.com/annulation">
</div>
```

## Paramètres

| Paramètre | Type | Requis | Description |
|-----------|------|--------|-------------|
| `data-amount` | number | ✅ | Montant en FCFA |
| `data-currency` | string | ✅ | Code devise (XOF) |
| `data-api-key` | string | ✅ | Clé API SenePay |
| `data-description` | string | ✅ | Description |
| `data-order-id` | string | ✅ | ID unique de commande |
| `data-return-url` | string | Optionnel | URL après paiement réussi |
| `data-cancel-url` | string | Optionnel | URL en cas d'annulation |
| `data-theme` | string | Optionnel | `light` ou `dark` (défaut: light) |
| `data-lang` | string | Optionnel | `fr` ou `en` (défaut: fr) |

## Exemple complet

```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Paiement SenePay</title>
</head>
<body>
  <h1>Facture Pro #1234</h1>
  <p>Montant : 5 000 FCFA</p>

  <script src="https://cdn.sene-pay.com/button.js"></script>
  <div class="senepay-button"
       data-amount="5000"
       data-currency="XOF"
       data-api-key="sk_test_votre_cle"
       data-description="Facture Pro #1234"
       data-order-id="ORDER-1234"
       data-theme="dark">
  </div>
</body>
</html>
```

## Événements JavaScript

```javascript
document.addEventListener('senepay:success', function(e) {
  console.log('Paiement réussi:', e.detail.order_id);
  window.location.href = '/confirmation';
});

document.addEventListener('senepay:error', function(e) {
  console.log('Erreur:', e.detail.message);
});

document.addEventListener('senepay:cancel', function(e) {
  console.log('Paiement annulé');
});
```

## Sécurité

⚠️ En production, utilisez toujours un serveur pour générer les order_id et valider les callbacks via webhook.

## Support

- API: https://api.sene-pay.com
- Documentation: https://docs.sene-pay.com
- Support: contact.senepay@gmail.com

## Licence

Propriétaire — Millennium Capital Invest LLC.
