### Esercizio 4 - Longest Increasing Subsequence
Sia $X$ il nostro array di input.
Sia $l$ un array contenete in posizione $i$ la lunghezza della massima sottosequenza crescente $S_i=\{j:1 \leq j < i, X[j] < X[i] \}$ nella seguente maniera:
$$l[i] =  \begin{cases} 
        1 & \text{se } S_i = \empty  \\
        1 + \text{max}(S_i[1,\dots,j])  & \text{altrimenti}
        \end{cases} $$
Sia invece $prev$ un array in cui memorizzare gli indici dei predecessori degli elementi di $S_i$ come segue:
$$prev[i] =  \begin{cases} 
        0 & \text{se } S_i = \empty  \\
        k \text{ con } l[k] = \text{max}(S_i[1,\dots,j]) & \text{altrimenti}
        \end{cases}$$

Possiamo quindi scrivere il seguente pseudocodice:
```
LIS(X):
    n <- length(X)
    len <- 1
    end <- 1
    l[1] <- 1
    prev[1] <- 0
    for i <- 2 to n do
        l[i] <- 1
        prev[i] <- 0
        for j <- 1 to i-1 do
            if X[j] < X[i] then
                if l[i] < l[j] then
                    l[i] <- l[j]+1
                    prev[i] <- j
                endif
            endif
        endfor
        if len < l[i] then 
            len <- l[i]
            end <- i
        endif
    endfor
    return len, end, prev

PRINT_LIST(i, prev, X):
    if prev[i] != 0:
        PRINT_LIS[prev[i], prev, X]
    endif
    print(X[i])
```

La complessità sarà quadratica rispetto al numero di elementi presenti in $X$, $\Theta(n^2)$.


### Esercizio 5 - Maximum Subarray Sum
L'idea è quella di scorrere il nostro array di input $A$ e decidere se aggiungere o meno al subarray (che ricordo contiene elementi contigui di $A$) l'elemento successivo di A rispetto alla somma che ho fià ottenuto oppure ripartire dall'elemento successivo per creare il nostro subarray finale.
Pertanto:
```python
def max_subarray_sum(A):
    dp = [0] * len(A)
    dp[0] = A[0]
    max_sum = A[0]
    start = 0
    end = 0
    for i in range(1,len(A)):
        dp[i] = max(A[i]+dp[i-1], A[i])
        # Aggiorniamo gli indici per stampare il subarray finale
        if A[i] + dp[i-1] > A[i]:
            end += 1
        else:
            start = end = i
        # Aggiorniamo la massima lunghezza
        if dp[i] > max_sum:
            max_sum = dp[i]

    return A[start, end+1], max_sum
```

Per qualcosa di più sofisticato, guardate [Kadane's algorithm](https://medium.com/@rsinghal757/kadanes-algorithm-dynamic-programming-how-and-why-does-it-work-3fd8849ed73d).