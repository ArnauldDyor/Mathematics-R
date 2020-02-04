# EXERCICE 1

Cet exercice étudie le niveau de bruit émis par des véhicules dans une rue de Montréal

### Question 1

```
Decibel <- c(54.8,55.4,57.7,59.6,60.1,61.2,62,63.1,63.5,64.2,65.2,65.4,65.9,66,67.6,68.1,69.5,70.6,71.5,73.4)
```

`Moyenne`
```R
moyenne <- mean(Decibel)

output: 64.24
```
`Médiane`
```R
median(Decibel)

output: 64.7
```
`Variance`
```
var(Decibel)

output: 26.51832
```
`Ecart-type`
```
ecart <- sd(Decibel)

output: 5.1495937499451
```
`Coefficients de variation`
```
coefV <- ecart/moyenne

output: 0.0801617956093572
```
`Quartiles empiriques`
```
quantile(Decibel)

output:
   0%    25%    50%    75%   100% 
54.800 60.925 64.700 67.725 73.400 
```

### Question 2

- histogramme à classes de même largeur
```
hist(Decibel, col = "skyblue", right = FALSE )
```
![histogramme même largeur] (../Screenshots/hist1.png)

- histogramme à classes de même effectif
```
breaks <- c(54.8, quantile(Decibel,seq(1,19)/20),73.4) 
hist(Decibel, breaks, col = "red")
```
![histogramme même effectif] (../Screenshots/hist2.png)

### Question 3
On suppose que l'échantillon Decibel est issu d'une loi normale
- Estimation de la moyenne et de la variance d'un tel échantillon

*Pour ce faire, il faut dans un premier temps normaliser le vecteur
```
normaliseDecibel <- scale(Decibel)

estimation_moyenne <- mean(normaliseDecibel)

output: 1.09915332044408e-15
```

```
estimation_variance <- var(normaliseDecibel)

output: 1
```