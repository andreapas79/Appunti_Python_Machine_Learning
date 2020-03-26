# Ciclo di vita di un algoritmo nel Datascience

[Fase 1 - Comprensione del problema](#Comprensione del problema)

[Fase 2 - Acquiring data](#Raccolta dei dati (Data mining))

[Fase 3 - Data cleaning](#Analisi di un dataframe (Data cleaning))

[Fase 4 - Data exploration](#Esplorazione dei dati (Data exploration))

[Fase 5 - Feature engineering](#Manipolazione del dataframe (Feature engineering))

[Fase 6 - Predictive modeling](#Realizzazione del modello predittivo)

[Fase 7 - Data Visualization](#Analisi dei risultati (Data visualization))



![](immagini/DataScience.png)

## Comprensione del problema



​																																					[Torna su](#Ciclo di vita di un algoritmo nel Datascience)

## Raccolta dei dati (Data mining)



​																																					[Torna su](#Ciclo di vita di un algoritmo nel Datascience)

## Analisi di un dataframe (Data cleaning)

Prima di implementare grafici, addestrare modelli o fare predizioni, c'è il dataframe. Questo ammasso, a volte immenso, di dati che ci capita tra le mani di cui necessita di alcune attenzioni prima di essere utilizzato. Così come il falegname deve osservare il legname con cui costruire un mobile prima di iniziare a tagliarlo, nella stessa maniera devono essere trattati i dati. Di seguito alcuni appunti sulle funzioni che utilizzo e sulle pratiche che adotto prima di iniziare a lavorare sui dati.

### Funzioni

* <u>df.info()</u>
* <u>df.describe()</u>
* df.dtypes
* df.count()
* df.shape

Le funzioni <u>info</u> e <u>describe</u> sono quelle che molto probabilmente racchiudono 

Trovare il numero di valori mancanti (Nan) è il primo passo per capire se una feature possa essere o meno utilizzata. Nell'esempio del Titanic sotto la voce 'deck' sono presenti solo 200 valori su 891, questo mi porta ad escluderla all'atto dell'analisi.

​																																					[Torna su](#Ciclo di vita di un algoritmo nel Datascience)

## Esplorazione dei dati (Data exploration)

​																																					[Torna su](#Ciclo di vita di un algoritmo nel Datascience)

## Manipolazione del dataframe (Feature engineering)

​																																					[Torna su](#Ciclo di vita di un algoritmo nel Datascience)

## Realizzazione del modello predittivo

Dalla fase precedente abbiamo estrapolato tre dataset:

* Training data
* Validation data
* Test data

Questi tre dataset saranno utilizzate per le tre fasi successive:

1.  Model training & building: la fase di addestramento, in cui il modello viene addestrato tramite i training data

2. Model testing: in cui traimite i validation data si recuperano i risultati ottenuti dal proprio modello

3. Error metrics: fase in cui si analizzano attraverso funzioni per modelli di classificazione o di regressione la bontà dei risultati ottenuti attraverso il model testing. A questo punto se i risultati non sono soddisfacenti si rinizia dal punto 1, cambiando alcuni parametri del modello, o cambiando proprio modello. Al contrario sei i risultati ottenuti sono buoni di procederà alla fase successiva: la rappresentazione dei dati ottenuti.

### Fase di addestramento

In base al tipo di dati che si hanno a disposizione e al tipo di risposta che si vuole ottenere viene definito il tipo di algoritmo o di famiglia di algoritmi che si possono utilizzare.

![](immagini/ModelliML.png)

### Test del modello

Con i modelli di tipo supervisionato verrà addestrato il modello con i training data e testato il modello con il validation data (o con il test data a seconda di quanto scelto nei punti precendenti).

Ciò che il modello predirrà con X_test data verrà confrontato con quanto compare nell' y_test data, tramite gli algoritmi opportuni a seconda si tratti di un modello di classificazione o di regressione. Per la fase successiva passeremo due set di dati:

* **y_test** data
* **predict** data

### Error metrics validation

Possiamo identificare funzioni che calcolano gli errori principalmente per modelli di classificazione e per modelli di regressione.

#### Classification Error Metrics

Solitamente ogni classificazione che il tuo modello può predire può essere di due tipi: corretta o incorretta, senza altra misura intermedia di errore, a prescidere che sia una classificazione binaria o multiclasse, il principio vale comunque.

É importante capire, che per quanto una risposta possa essere o giusta o sbagliata, non tutti gli errori hanno lo stesso peso. In statistica possono essere identificati due tipi di errore:

+ errori di primo tipo: conosciuti come falsi positivi

+ errori di secondi tipo: conosciuti come falsi negativi

Molte teorie statistiche si basano sulla riduzione di uno o di entrambi di questi errori.

![](immagini/Confusion-Matrix.png)

Per comprendere questo punto verranno introdotti i concetti dietro le metriche di classificazione dell'errore che possiamo ritrovare confrontate nella **Matrice di Confusione**:

* **Accuracy**: semplicemente misura la percentuale di predizioni corrette in rapporto al numero totale delle previsioni. 
  $$
  \frac {Σ True Pos + Σ True Neg}{
  Σ Total Cases}
  $$
  É il dato più "grezzo" che valuta la bontà di un modello in maniera diretta, per essere più precisi si possono trovare due definizioni di accuratezza: 

  - più comunemente, è una descrizione di errori sistematici , una misura della distorsione statistica ; la bassa precisione provoca una differenza tra un risultato e un valore "vero". ISO chiama questa verità .
  - In alternativa, ISO definisce l' accuratezza come la descrizione di una combinazione di entrambi i tipi di errore (casuale e sistematico), quindi un'elevata accuratezza richiede sia un'alta precisione che un'elevata verità.

  Questo valore è molto <u>utile quando abbiamo un dataset ben bilanciato</u>, in cui gli elementi sono presenti in maniera omogenea, mentre perde via via di valore quando al contrario abbiamo classi molto sbilanciate, in quanto l'errore non sarebbe proporzionale al numero di elementi, in questi casi assumono maggiore valenza i concetti di <u>recall</u> e <u>precision</u>;

* **Recall** (o Sensitivity): indica l'abilità di un modello di trovare TUTTI i casi rilevanti all'interno di un dataset, si calcola con:
  $$
  \frac{ΣTrue Pos} {ΣTrue Pos + ΣFalse Neg}
  $$
  la Recall è una misura di completezza o quantità (una misura del 100% indica che non ci sono falsi negativi).

* **Precision**:  (chiamata anche positive predictive value) è l'abilità di un modello di identificare SOLO i dati rilevanti. la precisione può essere vista come una misura che indica l'esattezza o la qualità di un modello predittivo, indicando l'assenza di falsi positivi.
  $$
  \frac{ΣTrue Pos} {ΣTrue Pos + ΣFalse Pos}
  $$
  

* **F1-score**:



​																																					[Torna su](#Ciclo di vita di un algoritmo nel Datascience)

## Analisi dei risultati (Data visualization)

​																																					[Torna su](#Ciclo di vita di un algoritmo nel Datascience)