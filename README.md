markdown
# ListStore  

Ce projet est un site qui charge automatiquement les données d’un fichier JSON pour générer une liste de commerces, restaurants et lieux. Les filtres (catégories, ville, etc.) et les informations affichées proviennent directement de cette structure.  

---

## Structure des données  

Chaque entrée du JSON correspond à un établissement. Exemple :  

```json
[
  {
    "id": "Sandwicherie-Sobaut",
    "name": "Sandwicherie Sobaut",
    "address": "Rue Pont a la Faulx 75, Internal Postal Box A, 7600 Peruwelz",
    "city": "Peruwelz",
    "lat": 50.50819,
    "lng": 3.59373,
    "photo": "./images/sobaut.png",
    "website": "https://www.facebook.com/people/Sandwicherie-Sobaut-P%C3%A9ruwelz/61560876904982/",
    "mapsUrl": "https://www.google.com/maps/place/Sandwicherie+Sobaut/...",
    "categories": ["Food"],
    "advantage": {
      "label": "-10%",
      "conditions": "Sur présentation de la carte avantages Ecofrost."
    },
    "openingHours": "Lun–Sam 7:00–15:30"
  }
]
````

---

## Champs disponibles

* **id** : identifiant unique de l’établissement
* **name** : nom de l’établissement
* **address** : adresse complète
* **city** : ville
* **lat / lng** : coordonnées GPS
* **photo** : chemin vers l’image de l’établissement

  * Les images doivent obligatoirement être placées dans le dossier **`/images`**.
  * Exemple : `"photo": "./images/nom-fichier.png"`
* **website** : lien vers le site ou la page Facebook
* **mapsUrl** : lien direct vers Google Maps
* **categories** : tableau de catégories (ex: `["Food"]`, `["Shop"]`)
* **advantage** : objet contenant :

  * `label` : texte de l’avantage (ex: "-10%")
  * `conditions` : conditions d’application
* **openingHours** : horaires d’ouverture

---

## Fonctionnement du site

1. Le site charge le JSON.
2. Les données sont utilisées pour :

   * Afficher la liste des établissements
   * Générer automatiquement les filtres (catégories, villes)
   * Afficher les détails de chaque commerce

---

## Ajout d’un nouvel établissement

Pour ajouter un commerce :

1. Ajouter l’objet correspondant dans le JSON.
2. Placer la photo dans le dossier **`/images`**.

   * Nommer le fichier avec des tirets plutôt que des espaces (ex: `ma-boulangerie.png`).
   * Déclarer ce chemin dans le champ `"photo"`.

Exemple :

```json
{
  "id": "Ma-Boulangerie",
  "name": "Ma Boulangerie",
  "address": "Rue Exemple 12, 7500 Tournai",
  "city": "Tournai",
  "lat": 50.605,
  "lng": 3.388,
  "photo": "./images/ma-boulangerie.png",
  "website": "https://ma-boulangerie.be",
  "mapsUrl": "https://maps.google.com/?q=ma+boulangerie",
  "categories": ["Food", "Bakery"],
  "advantage": {
    "label": "1 café offert",
    "conditions": "À l’achat d’une baguette spéciale."
  },
  "openingHours": "Mar–Dim 6:30–18:00"
}
```

---

## Extensions possibles

* Ajouter un champ `phone` pour un contact direct.
* Support de plusieurs images par commerce.
* Mise en place d’un champ `tags` pour plus de flexibilité que `categories`.

---

Olivier Ecofrost

