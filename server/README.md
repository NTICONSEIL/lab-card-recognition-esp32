# L5 — Serveur d'inférence (v1)

API FastAPI conteneurisée qui reçoit une image JPEG et renvoie la carte reconnue.

## Contrat d'interface

`POST /predict` — corps : image JPEG (`Content-Type: image/jpeg`), en-tête `Authorization: Bearer <jeton de l'objet>`

Réponse :

```json
{ "carte": "dame_coeur", "libelle": "Dame de cœur", "confiance": 0.97 }
```

Sous le seuil de confiance (à fixer par L3) : `"carte": "inconnue"`.

`GET /health` — état du service et version du modèle chargé.

## À produire

- [ ] `app/main.py` avec les deux routes
- [ ] Chargement du modèle publié en release
- [ ] `Dockerfile` et service ajouté à `platform/docker-compose.yml`
- [ ] Publication de chaque résultat sur MQTT pour l'historique
