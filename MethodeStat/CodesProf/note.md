## Vocabulaire

- Médiane : Valeur qui partage une série statistique en deux parties égales.
- Moyenne : Somme des valeurs divisée par le nombre de valeurs.
- Mode : Valeur la plus fréquente.
- Etendue : Différence entre la plus grande et la plus petite valeur. page 52
- Quartile : Valeurs qui partagent une série statistique en quatre parties égales.
- Variance : Somme des carrés des écarts à la moyenne divisée par le nombre de valeurs. page 52

## Propriétés

Voir ChatGPT [Conversation](https://chatgpt.com/c/6717d9e8-408c-8004-9fe6-4b0553fc8529)

# Statistiques déscriptive

## Formules

Bernoulli ou binomiale : 
- Probabilité : scipy.stats.binom.pmf(k, N, p)
- Moyenne : $N * p$
- Variance : $N * p * q = \sigma^2$  
- Ecart-type : $\sqrt{N*p*q} = \sigma$

Distribution géométrique :
- Probabilité : scipy.stats.geom.pmf(k, p) or $p * q^{N-1}$

Distribution normale ou gaussienne :
- Probabilité : scipy.stats.norm.pdf(x, $\mu$, $\sigma$)
- Moyenne : $\mu$
- Variance : $\sigma^2$
- Ecart-type : $\sigma$

## Mesures entre 2 variables quantitatives

### Covariance
- Covariance : $\frac{1}{n} \sum_{i=1}^{n} (x_i - \bar{x})(y_i - \bar{y})$

#### Propriétés

- cov(X, Y) > 0 $\Rightarrow$ X et Y varient dans le même sens.
- cov(X, Y) < 0 $\Rightarrow$ X et Y varient dans des sens opposés.
- cov(X, Y) = cov(Y, X)
- cov(X, X) = var(X)
- cov(x, ay + bz) = a cov(X, Y) + b cov(X, Z)

### Corrélation linéaire

- Coefficient de corrélation linéaire : $\rho = \frac{cov(X, Y)}{\sigma_X \sigma_Y}$

#### Propriétés

- -1 $\leq \rho \leq 1$
- $abs(\rho) = 1 \Rightarrow$ Corrélation parfaite
- $\rho = 0 \Rightarrow$ Pas de corrélation linéaire (indépendance)
- 0 < $abs(\rho)$ < 1 $\Rightarrow$ Corrélation positive

### Régression linéaire de y en x

- Droite de régression : $y = ax + b$
- Coefficient de régression : $a = \frac{cov(X, Y)}{var(X)}$
- Ordonnée à l'origine : $b = \bar{y} - a \bar{x}$

### Régression linéaire de x en y

- Coefficient de régression : $a' = \frac{cov(X, Y)}{var(Y)}$
- Ordonnée à l'origine : $b' = \bar{x} - a' \bar{y}$

### Lien entre corrélation et régression

- $\rho^2 = aa'$ or $\rho = a\frac{\sigma(x)}{\sigma(y)} = a'\frac{\sigma(y)}{\sigma(x)}$


## Ajustement à une fonction exponentielle

- $y = e^{x}$ exponentielle de base $e$
- $y = a^{x}$ exponentielle de base $a$
- $y = ba^x$ Forme générale

### Changement de variable

- $\ln(y) = \ln(b) + x \ln(a)$
- $Y = \ln(y)$, $X = x$, $A = \ln(a)$, $B = \ln(b)$
- $Y = AX + B$

## Ajustement à une fonction puissance

- Modèle puissance : $y = bx^a$

### Changement de variable

- $\ln(y) = \ln(b) + a \ln(x)$
- $Y = \ln(y)$, $X = x$, $A = a$, $B = \ln(b)$
- $Y = AX + B$

# Statistique Inférentielle

## Vocabulaire

- $\mu_{\overline{X}}$ : Moyenne de la distribution des moyennes
- $\sigma_{\overline{X}}$ : Ecart-type de la sitribution des moyennes

### Population

- $N$ : Population
- $\mu$ = Moyenne
- $\sigma$ = Ecart-type

### Echantillon

- $n$ : échantillons $n \in N$

#### Propriétés exhaustivité (`replace=False`)

- $\mu_{\overline{X}} = \mu$
- $\sigma_{\overline{X}} = \frac{\sigma}{\sqrt{n}}\sqrt{\frac{N-n}{N-1}}$

#### Propriétés non-exhaustivité (`replace=True`)

- $\mu_{\overline{X}} = \mu$
- $\sigma_{\overline{X}} = \frac{\sigma}{\sqrt{n}}$
