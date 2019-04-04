# Exercice #2

*Objectif:* Appliquer certains effets de perspective à l'aide des matrices de transformation.

**Modifiez ce fichier pour répondre aux questions**

## Généralité

Un composant `CustomMatrices` a été ajouté à la caméra *Exercice2/Camera* de la scène principale (*Scenes/Main*). Ce composant applique la matrice de projection configurée en paramètre à la caméra (de façon continue, donc possible de la modifier lors de l'exécution). Cette matrice est sauvegardée dans un object scriptable afin de pouvoir les conserver, et il suffit d'y glisser-déposer un objet scriptable du même type pour essayer diverses configurations.

## 2.1

Configurez la résolution du jeu pour être en ratio 16:9. Lancez le jeu à l'aide de la matrice *PerspectiveMatrix*. Modifiez le ratio pour une configuration 4:3. Que constatez-vous?
**L'image est déformée, les assets affichés à l'écran ont l'air moins large et la première valeur de la première colonne de la matrice est modifiée**
Remarquez les valeurs de la diagonale de la matrice. Dupliquez l'objet de matrice et paramétrez manuellement les valeurs pour obtenir un résultat satisfaisant. Quelle matrice avez-vous obtenu?
**[1,3	0,00000	0,00000	0,00000
0,00000	1,732051 0,00000	0,00000
0,00000	0,00000	-1,0006	-0,60018
0,00000	0,00000	-1,00000	0,00000]**


## 2.2

Faites le même exercice que précédemment, mais à l'aide de la matrice *OrthoMatrix*.

**Même constat**

*[0,08625 0 0 0 
0 0,1 0 0
0 0 -0,0020006 -1,0006
0 0 0 1]*

## 2.3

En conservant un ratio 16:9, dupliquez et modifiez la matrice *OrthoMatrix* en modifiant les deux valeurs supérieures de la dernière colonne (demeurez dans la plage ±1). Que constatez-vous? Qu'arrive-t-il si vous modifiez la troisième valeur de cette colonne? Qu'en est-il de la dernière valeur?

**En modifiant la premiere valeur de la dernière colonne on effectue une translation sur l'axe X et en modifiant la deuxieène colonne on effectue une translation sur l'axe Y. Si on modifie la troisième valeur, on modifie le champs de vision en profondeur. Si on modifie la dernière valeur, on effectue une translation sur l'axe Z **

## 2.4

Dupliquez et modifiez la matrice *OrthoMatrix*, appliquez les valeurs "-0.2" et "-0.8" aux deux valeurs supérieures de la dernière colonne, et ajoutez les valeurs "-0.1" et "-0.178" aux deux valeurs supérieures de la troisième colonne. Que constatez-vous?

**On s'aperçoit que l'angle de rotation de caméra est modifiée et qu'une translation à été effectuée, la caméra cible les voitures au lieu d'être centrée sur le personnage.**

## 2.5

Désactivez la caméra *Exercice2/Camera* et activez la caméra *Exercice2/Camera (1)*. Ajoutez un script au projet, à ajouter sur cette dernière caméra, où vous implémenterez un effet de [Travelling Contrarié](https://fr.wikipedia.org/wiki/Travelling_contrari%C3%A9) centré sur le personnage. Il existe plusieurs références sur le web pour des algorithmes (incluant la page anglaise de l'article ci-dessus), mais vous devriez être en mesure de déduire un algorithme à l'aide d'un peu d'algèbre linéaire en analysant l'effet.