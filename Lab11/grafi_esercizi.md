# Esercizi su grafi

1. Si consideri un grafo non orientato $G=(V, E)$ in cui a ciascun nodo $v \in V$ è associato un peso reale $w(v)$ (che può essere positivo o negativo). Un cammino $<v_1, v_2, \dots v_k>$ si dice monotono se $w(v_1) < w(v_2) < \dots < w(v_k)$. In altre parole in un cammino monotono i pesi dei nodi attraversati devono essere in ordine strettamente crescente. 
   1. Dimostrare che se $<v_1, v_2, \dots v_k>$ è un cammino monotono, allora è aciclico.
   2. Descrivere un algoritmo efficiente che, dato in input un grafo non orientato $G=(V, E)$ con nodi pesati, e due nodi $s, d\in V$, restituisce `true` se e solo se esiste un cammino monotono che inizia dalla sorgente $s$ e termina nella destinazione $d$. L'algoritmo deve anche stampare i nodi che compongono tale cammino (i nodi possono essere stampati nell'ordine $v_1, v_2, \dots v_k$ oppure nell'ordine inverso $<v_k, v_{k-1}, \dots v_1>$).
   3. Determinare il costo computazionale dell'algoritmo descritto al punto 2, motivando la risposta.


<br>
<br>


2. Considerare il seguente grafo non orientato: 
   
   ![Alt text](image.png)    


    1. Gli archi in grassetto possono rappresentare un albero di visita ottenuto mediante una visita in profondità del grafo? In caso affermativo specificare il nodo di inizio della visita, e rappresentare il grafo mediante liste di adiacenza in modo tale che l'ordine in cui compaiono gli elementi nelle liste consenta all'algoritmo DFS di produrre esattamente l'albero mostrato. 
    2. Gli archi in grassetto possono rappresentare un albero di visita ottenuto mediante una visita in ampiezza del grafo? In caso affermativo specificare il nodo di inizio della visita, e rappresentare il grafo mediante liste di adiacenza in modo tale che l'ordine in cui compaiono gli elementi nelle liste consenta all'algoritmo BFS di produrre esattamente l'albero mostrato.


3. Cosa succede se l'algoritmo di Dijkstra viene eseguito su un grafo in cui le lunghezze degli archi possono essere anche negative?
   * Nel caso di un grafo non orientato?
   * Nel caso di un grafo orientato? (Con archi negativi, ma senza cicli negativi)

4. Dato un grafo orientato con solo archi di peso positivo e due nodi $s$ e $r$, ci possono essere diversi cammini minimi da $s$ a $r$. Modificare l'algoritmo di Dijkstra in modo tale che restituisca il numero di cammini minimi da $s$ a $r$.





## Risorse

Per la visualizzazione di diversi algoritmi:
   - [Algorithm-visualizer](https://algorithm-visualizer.org)
   - [VisuAlgo](https://visualgo.net/en)



