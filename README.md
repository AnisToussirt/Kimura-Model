# Modèle de Kimura : Impacts de la dominance dans le modèle de fixation des mutations

## Introduction

Ce projet explore l'impact de la dominance sur la probabilité de fixation d'un gène mutant dans une population, en utilisant le modèle de Kimura. Le modèle de Kimura est un modèle classique en génétique des populations qui décrit la probabilité de fixation d'une nouvelle mutation dans une population en fonction de sa fréquence initiale, de son avantage sélectif et du coefficient de dominance.

## Modèle

Le modèle étudié dans ce projet est le suivant où :

*   u(p) est la probabilité de fixation d'un gène mutant avec une fréquence initiale p.
*   G(x) = exp(-intégrale de (2M_delta_x / V_delta_x) dx)
*   M_delta_x est le changement moyen de la fréquence du gène dans un intervalle de temps court delta.
*   V_delta_x est la variance du changement de la fréquence du gène dans un intervalle de temps court delta.


## Code

Le code fourni implémente le modèle de Kimura en Python et génère des simulations pour étudier l'impact de la dominance sur la probabilité de fixation. Le code comprend les fonctions suivantes :

*   `log_G(x, N, s, h)` : Calcule le logarithme de la fonction `G(x)`.
*   `log_sum_exp(log_vals)` : Calcule le log-sum-exp des valeurs logarithmiques pour éviter les underflows/explosions.
*   `u_log(p, N, s, h, num_points=1000)` : Calcule `u(p)` en utilisant l'échelle logarithmique.

Le code génère également des tracés 3D et des cartes thermiques pour visualiser la probabilité de fixation en fonction du coefficient de dominance (`h`) et de l'avantage sélectif (`s`).

## Rapport

Le rapport fourni explore les résultats des simulations et discute de l'impact de la dominance sur la probabilité de fixation. Le rapport comprend les sections suivantes :

1. **Introduction** : Présente le concept de dominance en génétique et son rôle dans la diffusion d'un caractère au sein d'une population.
2. **Modèle de Kimura : Probabilité de fixation d'un gène mutant dans une population** : Présente le modèle de Kimura et explique sa dérivation.
3. **Application à un cas général de sélection** : Discute de la probabilité de fixation dans le cas d'une dominance intermédiaire et des cas de sur/sous-dominance.
4. **Conclusion** : Résume les résultats et discute des implications de l'étude.
5. **Discussion** : Suggère des orientations de recherche futures et discute des limitations de l'étude.


# Guide d'Utilisation : Modification des Paramètres

## Modification des paramètres

Pour exécuter le code, vous aurez besoin des packages Python suivants :

*   NumPy
*   SciPy
*   Matplotlib

Vous pouvez modifier les paramètres du modèle directement dans le fichier `kimura_model.py`. Les paramètres modifiables sont les suivants :

- **`N`** : Taille effective de la population (par défaut : `1000`)
- **`p`** : Fréquence initiale de la mutation (par défaut : `1 / (2 * N)`)
- **`h_values`** : Liste des valeurs du coefficient de dominance à simuler (par défaut : `np.linspace(-3, 3, 50)`)
- **`s_values`** : Liste des valeurs de l'avantage sélectif à simuler (par défaut : `np.linspace(-1, 1, 50)`)

### Exemple de modification

Pour simuler le modèle avec une taille de population de `5000`, une fréquence initiale de `0.01` et une plage de valeurs de dominance de `-2` à `2`, modifiez les lignes suivantes dans le script :

```python
N = 5000  # Taille effective de la population
p = 0.01  # Fréquence initiale de la mutation

# Grille de valeurs pour h et s
h_values = np.linspace(-2, 2, 50)  # Coefficient de dominance
s_values = np.linspace(-1, 1, 50)  # Avantage sélectif

Après avoir modifié les paramètres, enregistrez le fichier et exécutez le script pour générer les tracés avec les nouvelles valeurs.
