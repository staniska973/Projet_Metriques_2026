# Projet Métriques 2026

## Auteur
Karim STANISLAS-CONSTANTIN

## Présentation rapide
Dans ce projet, on construit une application web avec Flask pour apprendre à manipuler des API et à afficher des graphiques météo.
L'objectif est de rester simple, compréhensible et de voir un flux complet :
- on crée des routes Flask,
- on récupère des données JSON,
- on transforme ces données,
- on affiche le résultat dans des pages HTML.

---

## Démarrage (Codespace ou local Linux)

### 1) Installer les dépendances
```bash
make install
```

### 2) Lancer l'application
```bash
make run
```

### 3) Ouvrir l'application
- URL locale : `http://127.0.0.1:5000`
- en Codespace : on ouvre l'onglet Ports et on rend le port 5000 public.

---

## Ce qui a été fait (toutes les consignes du README)

## Séquence 3 - Modification HTML
Le fichier `templates/hello.html` a été modifié avec un nom/prénom et un petit texte d'accueil.

## Exercice 1 - Route `/contact`
Route créée dans Flask :
- `/contact`

Cette route affiche une page HTML de contact (formulaire visuel) avec :
- nom,
- prénom,
- message.

Important : c'est normal, le formulaire ne sauvegarde rien (pas de base de données dans l'atelier).

## Exercice 2 - API JSON filtrée `/paris`
Route créée dans Flask :
- `/paris`

Cette route appelle Open-Meteo (Paris) et renvoie un JSON propre avec :
- `datetime`
- `temperature_c`

On filtre uniquement les données utiles pour le graphique.

## Exercice 3 - Fichier HTML dans `templates` + route `/rapport`
Fichier créé :
- `templates/graphique.html`

Route créée :
- `/rapport`

La route retourne le template HTML, donc on voit bien la page depuis Flask.

## Exercice 4 - Graphique ligne Google Charts
Dans `graphique.html`, on récupère `/paris` avec `fetch`, puis on affiche un Line Chart.
On convertit les dates JSON en objets Date JavaScript pour que l'axe du temps fonctionne correctement.

## Exercice 5 - Histogramme `/histogramme`
Route créée :
- `/histogramme`

API ajoutée :
- `/paris-journalier` (températures max journalières)

Template créé :
- `templates/histogramme.html`

On affiche les températures de Paris en colonnes (histogramme) pour 7 jours.

## Exercice 6 - Contact un peu plus esthétique
Le `/contact` pointe vers une vraie page HTML plus propre visuellement.
On reste volontairement simple (niveau débutant), mais c'est cohérent et lisible.

## Atelier - Route `/atelier` (graphique différent)
Consigne respectée : pas de line chart et pas d'histogramme.

Route créée :
- `/atelier`

API atelier ajoutée :
- `/atelier-marseille`

Template créé :
- `templates/atelier.html`

Choix fait pour l'atelier : vitesse du vent max à Marseille sur 7 jours, affichée en Pie Chart (donut).

---

## Liste des routes disponibles
- `/` : page d'accueil
- `/contact` : page de contact HTML
- `/paris` : API JSON température horaire Paris
- `/rapport` : page graphique ligne (Google Charts)
- `/paris-journalier` : API JSON température max journalière Paris
- `/histogramme` : page histogramme (colonnes)
- `/atelier-marseille` : API JSON vent max Marseille
- `/atelier` : page atelier (pie chart)

---

## Structure des fichiers ajoutés/modifiés
- `app.py`
- `templates/hello.html`
- `templates/contact.html`
- `templates/graphique.html`
- `templates/histogramme.html`
- `templates/atelier.html`

---

## Vérification rapide
Après `make run`, on peut tester rapidement :
- `http://127.0.0.1:5000/`
- `http://127.0.0.1:5000/contact`
- `http://127.0.0.1:5000/paris`
- `http://127.0.0.1:5000/rapport`
- `http://127.0.0.1:5000/histogramme`
- `http://127.0.0.1:5000/atelier`

Si une page ne marche pas, on regarde les logs dans le terminal Flask (troubleshooting demandé dans l'énoncé).
