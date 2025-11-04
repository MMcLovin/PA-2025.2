# MOM (Mediana das medianas)

* Curiosidade, o mesmo criador do Quicksort (Tony Hoare) inventou o QuickSelect, que é usado para encontrar o k-ésimo menor elemento em um conjunto não ordenado.
    * O cara é um britânico que nasceu no Siri Lanka e se formou em Moscow e tá vivo até hoje com 91 anos kkkkkk.

* Cara, e eu achando que o Inversão de Contagem era complicado kkkkk

* Esses três vídeos me ajudaram muito a entender o algoritmo:
  * [Median of Medians: The Smartest Algorithm No One Uses](https://www.youtube.com/watch?v=5JXpNOZWAHM&list=TLPQMjkxMDIwMjXhF6Sqp4wU3Q&index=2)
  * [Illustration of Linear Time Median of Medians Algorithm ](https://www.youtube.com/watch?v=_xp5FdAvIK8&list=TLPQMjkxMDIwMjXhF6Sqp4wU3Q&index=1&pp=gAQBiAQB)
  * [What is Median of Medians algorithm for Selection Problem? ](https://www.youtube.com/watch?v=BA222oONWco&list=TLPQMjkxMDIwMjXhF6Sqp4wU3Q&index=4)

* Jeito Noob/Naive de achar a mediana de um conjunto não ordenado:
  * Ordena o conjunto (O(n log n))
  * Retorna o elemento do meio (O(1))
  * Complexidade total: O(n log n)

* Parece bom, mas não é. O(n log n) é "muito" pior do que O(n).

* Será que dá pra meter um O(n)? => Sim

* Na real, o quickselect não é um algoritmo para a achar medianas, mas sim para achar o k-ésimo menor elemento de um conjunto não ordenado, só que *it just so happens that* a mediana é o k/2-ésimo menor elemento.

* MOM é o a estratégia que quando usada no quickselect, nos dá a garantia de O(n) no pior caso.

* MOM != QuickSelect

# ExotericSorting
* Considerando que temos um conjunto A não ordenado de k elementos
1. vamos confiar em um oráculo que nos dá uma aproximação boa o suficiente da mediana em O(n)
2. Agora nós dividimos o conjunto A em 3 partes:
    * **L (Less than):** elementos menores que a mediana aproximada
    * **M (Median):** elementos iguais à mediana aproximada
    * **B (Greater than):** elementos maiores que a mediana aproximada
    * **obs:** *o custo dessa operação é O(n), pois apenas varremos o conjunto original e vamos copiando os elementos para os novos conjuntos*
3. Como o oráculo é meia boca, vamos observar a quantidade de elementos em L e B:
    * Se |L| > k/2 => quantidade de elementos no conjunto de números menor que a mediana/pivô que o oráculo nos deu => a mediana está em L => chamamos o oráculo recursivamente em L
    * Se |B| > k/2 => quantidade de elementos no conjunto de números maior que a mediana/pivô que o oráculo nos deu => a mediana está em B => chamamos o oráculo recursivamente em B
        * Se |L| <= k/2 e |B| <= k/2 => a mediana está em M => retornamos a mediana aproximada => mas vamos ignorar esse caso por enquanto
    * porque a mediana estará sempre no conjunto de maior cardinalidade entre L e B?
        * Isso tem a ver com a escolha da mediana/pivô: nós sabemos que a mediana será o número que ocupa a posição ceiling(k/2) - divide por 2 e arredonda para o próximo número inteiro - quando o conjunto está ordenado. Então isso basicamente nos diz se a mediana obtida exotericamente está muito alta (|L| > k/2, taca-lhe recursão em L) ou muito baixa (|B| > k/2, taca-lhe recursão em B).

(tenho que terminar essa bucha, me fodi na prova pq não compreendi direito as condições de parada)