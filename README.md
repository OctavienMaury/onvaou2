# On va où ? 🚄

**On va où ?** est une application web simple qui permet de choisir **au hasard une destination accessible en train**, à partir d’une gare de départ.  
L’objectif est d’encourager la découverte, le voyage spontané et la sérendipité.

---

## ✨ Principe

1. Vous choisissez une **gare de départ**
2. Vous sélectionnez éventuellement un **type de train** (TGV, TER, Intercités, ou tous)
3. L’application tire **une destination aléatoire**
4. Vous visualisez :
   - l’itinéraire sur une carte
   - quelques lieux culturels à proximité
   - des liens pour réserver votre billet

---

## 🎯 Fonctionnalités

- Sélection d’une gare de départ (données SNCF)
- Filtrage par type de train
- Tirage aléatoire d’une destination
- Carte interactive (OpenStreetMap)
- Points d’intérêt culturels à proximité (musées, théâtres, châteaux)
- Liens directs vers des plateformes de réservation

---

## 🧱 Architecture

Le projet est volontairement **léger** et **sans build**.

- Frontend statique (une seule page)
- Proxy API via **Cloudflare Workers** pour protéger la clé SNCF
- Déploiement via **GitHub Pages**

---

## 🚀 Installation

### 1. Déployer le proxy API (Cloudflare Worker)

Le Worker sert de proxy pour interroger l’API SNCF sans exposer la clé côté client.

1. Créer un compte sur Cloudflare
2. Aller dans **Workers & Pages** → **Create Worker**
3. Coller le contenu du fichier `worker.js`
4. Ajouter une variable d’environnement :
   - `SNCF_API_KEY` (clé API SNCF)
   - Activer l’option **Encrypt**
5. Déployer le Worker

Vous obtenez une URL du type :
