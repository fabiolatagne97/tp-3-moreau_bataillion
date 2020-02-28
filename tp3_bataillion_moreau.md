# TP 3 - Gestion des paquets

## Exercice 1. Commandes de base

Commencez par mettre à jour votre système avec les commandes vues dans le cours.

```
sudo apt update
sudo apt upgrade
```

**Donnez les commandes répondant aux questions suivantes :**

**1.Quels sont les 5 derniers paquets installés sur votre machine?**
```
ls -ltr /var/cache/apt/archives
```

**2.Utiliser dpkg et apt pour compter le nombre de paquets installés (ne pas hésiter à consulter le manuel!).Comment explique-t-on la (petite) différence de comptage?**
```
dpkg -l | wc -l
```
donne 559
```
sudo apt list --installed | wc -l
```
donne 555

La différence vient des fichiers de configuration de paquets désinstallés qui restent dans les dossiers et qui sont pris en compte par dpkg et pas par apt. Les paquets laissent des fichiers de configuration s'ils sont simplement remove et non purge.

**3.Combien de paquets sont disponibles en téléchargement?**
```
apt list --all-versions | wc -l
```
donne 124 907

**4.Créer un alias “maj” qui met à jour le système**

Dans ~/.bashrc rajouter
```
alias maj ='sudo apt update && sudo apt upgrade && sudo apt full-upgrade'
```
puis mettre à jour le fichier bashrc avec source .bashrc

**5.A quoi sert le paquet fortunes? Installez-le.**
 fortunes est un paquet qui permet d'afficher des citations sur une console.
 On l'installe avec : ```sudo apt install fortunes```

**6.Quels paquets proposent de jouer au sudoku?**

On installe le paquet gnome-sudoku

**7.Lister les derniers paquets installés explicitement avec la commande apt install**
