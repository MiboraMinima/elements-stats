---
editor_options: 
  markdown: 
    wrap: 72
---

# (PART) Nettoyer et transformer ses données {-}

# Les opérations basiques

## Extraction des données, concaténation

Souvent on peut avoir à faire des extractions de la base de données initiale. Il existe deux fonctions de base très pratique, les fonctions `subset` et `agregate`. La première extrait des variables avec ou sans filtre, la deuxième permet d'extraire des variables tout en appliquant une fonction.


```r
# Extraire les individus dont lhabitants
head(iris)
```

```
##   Sepal.Length Sepal.Width Petal.Length Petal.Width Species
## 1          5.1         3.5          1.4         0.2  setosa
## 2          4.9         3.0          1.4         0.2  setosa
## 3          4.7         3.2          1.3         0.2  setosa
## 4          4.6         3.1          1.5         0.2  setosa
## 5          5.0         3.6          1.4         0.2  setosa
## 6          5.4         3.9          1.7         0.4  setosa
```

```r
subset(iris$Petal.Width, iris$Species=='setosa' & iris$Sepal.Length > 5)
```

```
##  [1] 0.2 0.4 0.2 0.2 0.4 0.4 0.3 0.3 0.3 0.2 0.4 0.5 0.2 0.2 0.4 0.1 0.2 0.2 0.2
## [20] 0.4 0.2 0.2
```

```r
# Calculer la moyenne des prix dans les communes
aggregate(iris$Petal.Width, na.rm = TRUE, by = list(iris$Species), FUN = mean)
```

```
##      Group.1     x
## 1     setosa 0.246
## 2 versicolor 1.326
## 3  virginica 2.026
```

## Changer la nature des variables

Il peut arriver que R n'interprète pas bien la nature des variables (\textit{cf. ???}). On peut modifier leur nature avec le code suivant :


```r
# définir comme facteur
var <- c(16,180,220,150,20) # vecteur numérique
var <- as.factor(var) # pour dire que la variable est un facteur

# définir en numérique
var <-as.character(c('16','180', '220', '150', '20')) # vecteur de caractères
var <- as.numeric(var) # pour dire que la variable est numérique.
                
# Facteur vers numérique
library(hablar)
```

```
## Warning: le package 'hablar' a été compilé avec la version R 4.2.2
```

```r
var <-  c(2,1,1,1,2)
as_reliable_num(var)
```

```
## [1] 2 1 1 1 2
```

## Résumé

Le package `dplyr`[^02-manipulations-1] permet de manipuler facilement les données. On trouve dans le tableau suivant les fonctions qui sont les plus utilisées pour manipuler les données.

[^02-manipulations-1]: Lien vers le un [*cheat sheet*](https://github.com/rstudio/cheatsheets/blob/main/data-transformation.pdf)

+-------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------+
| Description                                                                                                                                     | R code                                                |
+=================================================================================================================================================+=======================================================+
| Sélectionner des lignes en foncton de leur valeurs                                                                                              | `df %>% filter(var1 == value, var2 > value,…)`        |
+-------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------+
| Enlever les lignes dupliquée                                                                                                                    | `df %>% distinct()`                                   |
+-------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------+
| Arrange the rows based on specified column's values. Par défaut le `df` est réarrangé en fonction de la variable choisie dans l'ordre croissant | `df %>% arrange(var) : ordre croissant`               |
|                                                                                                                                                 |                                                       |
|                                                                                                                                                 | `df %>% arrange(desc(var)) : ordre décroissant`       |
+-------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------+
| Sélectionner des variables par leur nom                                                                                                         | `df %>% select(var_1, var_2, var_x)`                  |
+-------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------+
| Renommer des colonnes                                                                                                                           | `df %>% rename(new_var = old_var)`                    |
+-------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------+
| Renommer des lignes                                                                                                                             | `rownames(df)[rownames(df) == "label"] = "new_label"` |
+-------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------+
| Ajouter et créer de nouvelles variables                                                                                                         | `df %>% mutate(new_var = an operation)`               |
+-------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------+
| Mettre une colonne en ligne (`tibble`)                                                                                                          | `df <- column_to_rownames(df, var = "variable")`      |
+-------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------+
| Mettre une ligne en colonne (`tibble`)                                                                                                          | `df <- rownames_to_column(df)`                        |
+-------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------+
| Interchanger lignes et les colonnes                                                                                                             | `t(df)`                                               |
+-------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------+

# Chercher des données et les remplacer

Pour manipuler efficacement des *string*, on utilise *Regular Expression*.

Quand on a un tableau de données important et que les valeurs des variables à modifier sont en bordel il est commode de mettre au point un protocole de modification, et ce d'autant plus que le travail à réaliser est fastidieux.

On peut tester ses lignes de code sur [regex101](https://regex101.com). Il s'agit d'un IDE en ligne qui permet de visualiser dynamiquement son code.

## Références

<https://regex101.com>

<https://r4ds.had.co.nz/strings.html>

