# 🎯 Jour 9 / 10 — Analyse What-If : Scénarios & Valeur Cible

> **Série : 10 Days of Excel** · Jour 9/10  
> Concepts : Gestionnaire de scénarios · Valeur cible · Table de données · Seuil de rentabilité

---

## 📁 Fichiers du projet

```
Jour9-WhatIf/
│
├── compte_resultat.csv      ← Hypothèses et résultats du modèle de base
└── whatif_jour9.xlsx
    ├── MODÈLE                ← Compte de résultat avec hypothèses modifiables
    ├── SCÉNARIOS             ← 3 scénarios comparés (Pessimiste/Réaliste/Optimiste)
    └── VALEUR CIBLE          ← Guide complet : Valeur cible + Tables de données
```

---

## 🔑 Le modèle de base

4 hypothèses pilotent tout le compte de résultat :

| Hypothèse | Valeur |
|-----------|--------|
| Prix de vente unitaire | 45 € |
| Coût variable unitaire | 28 € |
| Charges fixes mensuelles | 12 000 € |
| Volume vendu | 900 unités |

**Formules calculées :**
```excel
Marge unitaire       = Prix - Coût variable
Marge totale          = Marge unitaire × Volume
Résultat net          = Marge totale - Charges fixes
Seuil de rentabilité  = Charges fixes / Marge unitaire
Marge de sécurité     = Volume - Seuil de rentabilité
```

---

## 🎯 1. Valeur Cible — Trouver une variable inconnue

**Question type :** *"Combien d'unités vendre pour un résultat net de 10 000€ ?"*

```
Données → Prévision → Analyse de scénarios → Valeur cible

Cellule à définir   : Résultat net (la formule)
Valeur              : 10000
Cellule à modifier  : Volume vendu (l'hypothèse)
```

Excel ajuste automatiquement le volume jusqu'à ce que le résultat net atteigne exactement 10 000€.

**Autre exemple :** trouver le prix minimum pour que le seuil de rentabilité = volume actuel.

---

## 📊 2. Table de données à 1 variable

Teste l'impact de **plusieurs valeurs** d'une hypothèse sur un résultat — en une seule opération.

```
1. Colonne de valeurs à tester : 500, 700, 900, 1100, 1300 (volumes)
2. Cellule formule juste au-dessus à droite : =Résultat_net
3. Sélectionner toute la plage (valeurs + formule)
4. Données → Analyse de scénarios → Table de données
5. Cellule d'entrée en colonne : Volume vendu
```

Résultat : Excel calcule le résultat net pour **chaque volume** automatiquement, sans copier la formule.

---

## 📐 3. Table de données à 2 variables

Croise **deux hypothèses** dans une grille (ex : Prix × Volume).

```
        40€    42€    45€    48€    50€
700    ...    ...    ...    ...    ...
800    ...    ...    ...    ...    ...
900    ...    ...    ...    ...    ...
1000   ...    ...    ...    ...    ...
```

```
1. Prix en ligne (en haut), Volume en colonne (à gauche)
2. Formule =Résultat_net dans le coin supérieur gauche
3. Sélectionner toute la grille
4. Table de données
   Cellule d'entrée ligne   : Prix de vente
   Cellule d'entrée colonne : Volume vendu
```

Résultat : une grille complète montrant le résultat net pour chaque combinaison prix/volume — parfait pour une heatmap.

---

## 🔮 4. Gestionnaire de scénarios

Sauvegarde plusieurs jeux d'hypothèses et bascule entre eux en un clic.

```
Données → Prévision → Analyse de scénarios → Gestionnaire de scénarios

Ajouter → Nom : "Pessimiste"
Cellules variables : Prix; Coût variable; Charges fixes; Volume
Saisir les valeurs → OK

Répéter pour "Réaliste" et "Optimiste"
```

- **Afficher** → bascule instantanément entre les scénarios
- **Synthèse** → génère un rapport comparatif sur une nouvelle feuille

---

## 📊 Les 3 scénarios comparés

| | Pessimiste | Réaliste | Optimiste |
|---|---|---|---|
| Prix unitaire | 40€ | 45€ | 50€ |
| Coût variable | 30€ | 28€ | 26€ |
| Charges fixes | 13 000€ | 12 000€ | 11 000€ |
| Volume | 700 | 900 | 1 100 |
| **Résultat net** | **-6 000€** | **3 300€** | **15 400€** |

---

## 💡 Quand utiliser quoi ?

| Outil | Cas d'usage |
|-------|-------------|
| **Valeur cible** | "Quelle valeur d'entrée donne ce résultat précis ?" |
| **Table à 1 variable** | "Comment le résultat évolue selon UNE hypothèse ?" |
| **Table à 2 variables** | "Comment le résultat évolue selon DEUX hypothèses croisées ?" |
| **Gestionnaire de scénarios** | "Comparer plusieurs jeux d'hypothèses complets nommés" |
