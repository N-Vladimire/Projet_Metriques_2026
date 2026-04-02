Atelier Métriques — Flask & API
Objectif du projet

Ce projet a pour objectif de construire une application web en Python avec Flask permettant de :

créer des API (routes)
consommer une API externe (Open-Meteo)
manipuler des données JSON
afficher des graphiques interactifs
structurer une application web simple

L’objectif final est de produire un dashboard de métriques fonctionnel.

Architecture du projet
  
**Architecture du projet :** Ci-dessous, voici l'architecture .   
  
![Screenshot Actions](Architecture_cible.png)  

## Installation et lancement (Codespace)

### Installer les dépendances

```bash
make install
```

### Lancer l’application

```bash
make run
```

### Accéder à l’application

* Ouvrir l’onglet PORTS
* Rendre le port 5000 public
* Ouvrir l’URL générée

---

## Méthode de travail (Codespace direct)

Lorsque le code est modifié :

```bash
Ctrl + S        # sauvegarder
Ctrl + C        # arrêter le serveur (si nécessaire)
make run        # relancer l’application
```

Puis tester dans le navigateur.

---

## Fonctionnalités développées

### 1. Page d’accueil

Route :

```
/
```

Affiche une page HTML simple (`hello.html`).

---

### 2. Page contact

Route :

```
/contact
```

Affiche une page HTML contenant un formulaire avec :

* nom
* prénom
* message

Objectif : améliorer l’aspect visuel et l’expérience utilisateur.

---

### 3. API météo Paris

Route :

```
/paris
```

Fonction :

* appelle l’API Open-Meteo
* extrait les dates (`time`)
* extrait les températures (`temperature_2m`)
* retourne un JSON simplifié

Exemple :

```json
[
  {
    "datetime": "2026-04-02T10:00",
    "temperature_c": 12.5
  }
]
```

---

### 4. Graphique des températures

Route :

```
/rapport
```

Fonction :

* appelle l’API `/paris`
* transforme les données JSON
* affiche un graphique de type LineChart

---

### 5. Histogramme

Route :

```
/histogramme
```

Fonction :

* réutilise les données de `/paris`
* affiche un graphique de type ColumnChart

---

### 6. Atelier personnalisé

Route :

```
/atelier
```

API associée :

```
/atelier-data
```

Fonction :

* récupération de la vitesse du vent à Marseille
* transformation des données
* affichage via un graphique de type AreaChart

Objectif : démontrer l’autonomie dans la création d’un indicateur.

---

## Technologies utilisées

### Backend

* Python
* Flask
* Requests

### Frontend

* HTML / CSS
* JavaScript (fetch API)

### Visualisation

* Google Charts

---

## Structure du projet

```text
.
├── app.py
├── templates/
│   ├── hello.html
│   ├── contact.html
│   ├── graphique.html
│   ├── histogramme.html
│   └── atelier.html
├── README.md
```

---

## Notions acquises

* création de routes Flask
* consommation d’API externes
* manipulation de données JSON
* interaction backend / frontend
* création de graphiques dynamiques
* organisation d’un projet web

---

## Améliorations réalisées

* ajout d’une barre de navigation (navbar)
* amélioration du design des pages
* structuration claire des routes
* réutilisation du code entre graphiques

---

## Gestion des erreurs

En cas de problème :

1. vérifier le terminal du Codespace
2. lire les logs Flask
3. vérifier :

   * les erreurs de syntaxe Python
   * les routes incorrectes
   * les fichiers HTML dans le bon dossier (`templates`)

---

## Checklist de validation

* /contact fonctionnel
* /paris retourne du JSON
* /rapport affiche un graphique
* /histogramme fonctionne
* /atelier fonctionne
* navigation fonctionnelle
* interface claire

---

## Conclusion

Ce projet illustre le fonctionnement complet d’une application web :

```text
Données → API → Backend → Frontend → Visualisation
```

Il constitue une base solide pour la création de dashboards de métriques.

---

## Améliorations possibles

* ajout de plusieurs villes
* ajout de filtres dynamiques
* intégration d’une base de données
* authentification utilisateur
* dashboard interactif avancé

---

## Auteur

Projet réalisé dans le cadre de l’atelier métriques.

---

## Remarque

Projet testé et fonctionnel via Codespace GitHub.
