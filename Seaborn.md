# Seaborn

Seaborn è una libreria per il plotting statistico, basata su matplotlib, rimanendo più "user friendly". Ha stili di default predefiniti molto belli ed è strutturata per lavorare molto bene con i dataframe di pandas.



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

![](immagini/Seaborn-boxplot.png)

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

Di seguito un breve grafico di riepilogo dei grafici precendenti:

![](immagini/Seaborn-riepilogo.png)

Questo è invece il codice compatto per la visualizzazione del precedente grafico

```
plt.figure(figsize=(10,10))
i=1
titles=['Boxplot', 'Violinplot', 'Stripplot', 'Swarmplot']
grafici=(sns.boxplot, sns.violinplot, sns.stripplot,sns.swarmplot)

for fun, title in zip (grafici, titles):
    plt.subplot(2,2,i)
    plt.title(title)
    fun(x='sex',y='tip', data=df)
    plt.tight_layout()
    i+=1
```

Qui si può notare come i titoli sono stati inseriti all'interno di un ciclo for, stessa cosa vale per le funzioni, questo esprime per me la potenza e la versatilità di Python per semplificare il codice e renderlo molto elegante e leggibile.

Di seguito il grafico catplot che si distingue dai precedenti in quanto

<img src="immagini/Seaborn-catplot.png" style="zoom:150%;" />

il codice del grafico:

```
sns.catplot(x="sex", y="total_bill",
                hue="smoker", col="time",
                data=df, kind="boxen",
                height=4, aspect=.7);
```



```
sns.barplot(x='sex', y='tip', hue='smoker', data=df, estimator=np.min)
```

Con l'attributo hue è possibile correlare due variabili categoriche

Con l'attributo estimator si imposta il metodo con cui raggruppare i valori delle variabili categoriche