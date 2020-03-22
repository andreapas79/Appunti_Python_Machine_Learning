# Seaborn



## Boxplot

Per comprendere il Boxplot è necessario fare una premessa riguardante il concetto di quartile e il concetto di mediana.

In statistica, in particolare in statistica descrittiva, data una distribuzione di un carattere quantitativo oppure qualitativo ordinabile (ovvero le cui modalità possano essere ordinate in base a qualche criterio), i <u>**quartili** sono quei valori/modalità che ripartiscono la popolazione in quattro parti di uguale numerosità</u>.

I quartili sono indici di posizione e rientrano nell'insieme delle statistiche d'ordine.

<u>La differenza tra il terzo ed il primo quartile è un indice di dispersione ed è detto **scarto interquartile**.</u>

Il quartile zero, il primo, il secondo, il terzo e il quarto quartile corrispondono con le prime modalità la cui frequenza cumulata percentuale è almeno 0, 25, 50, 75 e 100 rispettivamente.  I quartili equivalgono ai quantili q0 (quartile zero), q1/4 (primo quartile), q2/4=q1/2 (secondo quartile), q3/4 (terzo quartile) e q1 (quarto quartile).

- **secondo quartile (q2/4)** = coincide con la mediana e divide la popolazione in due  parti di uguale numerosità.

- **primo e il terzo quartile (q1/4 e q3/4)** = coincidono con la mediana delle due parti delineante dal secondo quartile

- **quartile  zero (q0)** = coincide con il valore minimo della distribuzione
- **quarto quartile (q1)** = coincide con il valore massimo della distribuzione

I quartili vengono inoltre utilizzati per rappresentare un Box-plot.

![image-20200322190131570](C:\Users\Max\AppData\Roaming\Typora\typora-user-images\image-20200322190131570.png)

Simili al boxplot ci sono

>See also
>
>Violinplot
>A combination of boxplot and kernel density estimation.
>
>Stripplot
>A scatterplot where one variable is categorical. Can be used in conjunction with other plots to show each observation.
>
>Swarmplot
>A categorical scatterplot where the points do not overlap. Can be used with other plots to show each observation.
>
>Catplot
>Combine a categorical plot with a FacetGrid.



```
sns.barplot(x='sex', y='tip', hue='smoker', data=df, estimator=np.min)
```

Con l'attributo hue è possibile correlare due variabili categoriche

Con l'attributo estimator si imposta il metodo con cui raggruppare i valori delle variabili categoriche