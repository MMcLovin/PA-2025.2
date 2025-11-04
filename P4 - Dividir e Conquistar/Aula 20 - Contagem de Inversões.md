# Contanto inversões

*  cara, foi o algoritmo que eu mais tive dificulade até agora

* ele mostrou 2 abordagens, uma era O(nlog²n) e a outra O(n log n)
* a abordagem O(n log n) é a do mergesort modificado
* a ideia que leva à O(nlogn) é que durante o merge a gente conta quantas inversões existem entre os dois arrays que estão sendo mesclados, então a gnt não faz uma coisa depois a outra, a gente faz tudo junto
* mas não entendi como isso é diferente de só fazer o mergesort e depois contar as inversões, pq no final das contas a gente ainda tá fazendo duas coisas
    * tipo, o nlog²n era assim:
        - passo nlogn
        - passo n
        - passo nlogn
        - passo n
        - total (não me pergunte como): nlog²n
    * já o nlogn é:
        - passo nlogn 
        - passo nlogn 
        - total: nlogn

# Exemplo

* vetor = {}