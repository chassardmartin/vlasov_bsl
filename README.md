# TP : Résolution de Vlasov-Poisson par une méthode semi-lagrangienne avec interpolations en séries de Fourier. 

Ce projet est dédié à la réalisation d'un TP numérique à destination des élèves du nouveau cours de [V. Ehrlacher](https://team.inria.fr/matherials/team-members/virginie-ehrlacher-galland/) en première année à l'Ecole des Ponts ParisTech. 

L'objectif est d'implémenter une méthode semi-lagrangienne pour la résolution du systéme de Vlasov-Poisson non-collisionnel décrivant l'évolution de la distribution électronique dans l'espace des phases $f : \Omega \times [0, T] \rightarrow \mathbb{R}$, en dimension $1\times 1$: $\,\Omega \subset \mathbb{R}\times\mathbb{R}$ selon

$$
    \begin{cases}
        \partial_t f(x,v,t) - E(x,t) \, \partial_v f(x,v,t) + v \, \partial_x f(x,v,t) = 0, \\
        \partial_x E(x,t)  = 1 - \int_{v} f(x,v,t) \, dt,
    \end{cases}
$$

et de tester cette implémentation sur le cas d'étude de l'instabilité double faisceau (doublestream instability). Le code ```VP_cubic_splines.ipynb``` propose une interpolation en splines, tandis que le script ```VP_bsl.ipynb``` présente une interpolation en séries de Fourier. Le script ```poisson_fem.ipynb ``` permet de comparer notre solveur poisson à une méthode précise de référence en éléments finis.

Les codes développés se situent dans le répertoire code/ et les graphes et .gif dans le répertoire graphs/ 