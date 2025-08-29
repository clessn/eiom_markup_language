# Outils de rédaction numériques en sciences sociales

Ce dépôt contient une présentation sur les langages de balisage et des exemples pratiques d'utilisation de Quarto pour la recherche en sciences sociales.

## 💾 Récupérer le projet en local

### Cloner le repository

Pour avoir tous les fichiers sur votre ordinateur :

```bash
git clone https://github.com/votre-username/eiom_markup_language.git
cd eiom_markup_language
```

### Ce que ça vous donne

En ayant le repository en local, vous pouvez :

- **Modifier les fichiers** directement sur votre machine
- **Tester et compiler** les présentations sans dépendre d'internet
- **Expérimenter** avec les exemples sans risquer de casser quoi que ce soit
- **Adapter** les templates à vos propres projets
- **Travailler hors ligne** une fois Quarto installé

### Prérequis

Avant de commencer, assurez-vous d'avoir :
- **Git** installé sur votre machine (pour cloner le repo)
- **Quarto** installé (voir section installation ci-dessous)
- Optionnel : **RStudio** pour une expérience plus simple

## 📋 Contenu du dépôt

- **`presentation.qmd`** : Présentation principale sur les langages de balisage
- **`templates_quarto/`** : Exemple d'article scientifique formaté avec Quarto
- **`custom.css`** : Styles personnalisés pour la présentation
- **`_quarto.yml`** : Configuration du projet Quarto

## 🚀 Installation de Quarto

### Si vous avez RStudio

Bonne nouvelle ! Si vous avez RStudio installé, vous pouvez installer Quarto très facilement :

1. **Ouvrez RStudio**
2. **Dans la console R**, tapez cette commande :
   ```r
   install.packages("quarto")
   ```
3. **Ou encore plus simple**, téléchargez directement Quarto : 
   - Allez sur https://quarto.org/docs/get-started/
   - Cliquez sur "Download" pour votre système (Windows/Mac/Linux)
   - Installez comme n'importe quel logiciel

### Vérifier que ça marche

Après l'installation, ouvrez le **Terminal** dans RStudio (onglet à côté de "Console") et tapez :
```bash
quarto --version
```

Si vous voyez un numéro de version, c'est bon !

## 📝 Comment compiler votre première présentation

### Méthode super simple (dans RStudio)

1. **Ouvrez le fichier `presentation.qmd`** dans RStudio
2. **Cliquez sur le bouton "Render"** (ou "Rendu") en haut du document
3. **Attendez quelques secondes** ⏳
4. **Votre présentation s'ouvre automatiquement** dans votre navigateur !

### Si le bouton "Render" ne marche pas

Pas de panique ! Utilisez le Terminal dans RStudio :

1. **Ouvrez le Terminal** (onglet en bas à côté de "Console")
2. **Tapez cette commande** :
   ```bash
   quarto render presentation.qmd
   ```
3. **Appuyez sur Entrée** et attendez
4. **Ouvrez le fichier `presentation.html`** qui a été créé

### Voir votre présentation en direct

Si vous voulez voir les changements en temps réel pendant que vous modifiez :

```bash
quarto preview presentation.qmd
```

Une page web s'ouvre et se met à jour automatiquement quand vous sauvegardez le fichier !

## 🎯 Votre premier document Quarto

### Structure de base

Un document Quarto (`.qmd`) a toujours cette structure :

```markdown
---
title: "Mon titre de présentation"
author: "Votre nom"
format: revealjs
---

# Ma première diapositive

Du texte normal ici

## Ma deuxième diapositive  

- Point 1
- Point 2
- Point 3

# Une nouvelle section

Plus de contenu...
```

### Les règles importantes

- **Les `---` au début** : C'est la configuration, ne les enlevez pas !
- **Un `#`** = nouvelle section
- **Deux `##`** = nouvelle diapositive dans la section
- **Sauvegardez souvent** et cliquez sur "Render" pour voir le résultat

## 🏗️ Comment Quarto fonctionne (simple)

Quarto prend votre fichier `.qmd` et le transforme automatiquement :

```
Votre fichier .qmd → Quarto fait sa magie → Présentation HTML
```

C'est comme un traducteur qui transforme votre texte simple en belle présentation web !

## 📊 L'exemple d'article scientifique

Dans le dossier `templates_quarto/`, il y a un exemple complet d'article avec :

- Bibliographie automatique
- Graphiques générés par du code R
- Format professionnel pour publication

### Pour le compiler :

1. **Ouvrez `templates_quarto.qmd`** dans RStudio
2. **Cliquez sur "Render"**
3. **Un PDF se génère automatiquement !**

## 🌐 Partager votre présentation

### Option 1 : Fichier local
- Le fichier `presentation.html` peut être envoyé par email
- Ça marche sur n'importe quel ordinateur avec un navigateur

### Option 2 : En ligne (plus avancé)
```bash
quarto publish gh-pages presentation.qmd
```

Votre présentation sera accessible sur internet !

## ❓ Problèmes fréquents et solutions

### "Le bouton Render ne fonctionne pas"
**Solution** : Utilisez le Terminal avec `quarto render presentation.qmd`

### "J'ai une erreur bizarre"
**Solutions** :
1. Vérifiez que les `---` au début sont bien présents
2. Sauvegardez le fichier avant de compiler
3. Redémarrez RStudio

### "Ma présentation est moche"
**Solution** : Modifiez le `custom.css` ou changez le thème dans l'en-tête :
```yaml
format:
  revealjs:
    theme: moon  # Essayez : dark, league, sky, beige, simple
```

### "Je veux ajouter du code R"
Utilisez des blocs comme ça :
````markdown
```{r}
plot(mtcars$mpg, mtcars$hp)
```
````

## 🎓 Pour aller plus loin

- **Documentation officielle** : https://quarto.org/docs/
- **Exemples de présentations** : https://quarto.org/docs/presentations/
- **Thèmes disponibles** : https://quarto.org/docs/presentations/revealjs/themes.html

N'hésitez pas à expérimenter ! Quarto est fait pour être facile à utiliser. 🚀