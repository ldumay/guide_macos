# Afficher ou masquer les fichiers cachés sur MacOS

[<== Retour](./)

## Afficher les fichiers cachés

Afficher tous les dossiers et fichiers cachés sous Mac
Pour afficher l’ensemble des répertoires et fichiers cachés sur un Mac, il faut passer par l’outil Terminal comme pour la première méthode décrite plus haut. La commande à saisir est toutefois différente.

Depuis les Utilitaires (Applications > Utilitaires), accédez à l’outil Terminal
Saisissez la commande suivante dans le Terminal puis validez :

```
defaults write com.apple.finder AppleShowAllFiles -bool true
```

Relancez ensuite Finder en saisissant la commande suivante dans le Terminal :

```
kill all Finder
```

et validez.

Le Finder dois se redémmarer.

Désormais, tous les fichiers et répertoires cachés s’afficheront quel que soit l’emplacement où ils se situent.

## Masquer les fichiers cachés

Pour les masquer à nouveau, il suffit de saisir la même commande indiquée plus haut en remplaçant la fin par false :

```
defaults write com.apple.finder AppleShowAllFiles -bool false.
```
