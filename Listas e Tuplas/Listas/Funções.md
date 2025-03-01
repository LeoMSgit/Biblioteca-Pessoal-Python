1) Definição
- lista = ["elemento1", "elemento2", "elemento3", ..., "elementoN"]
- lista = list("Python"), irá criar uma lista onde cada letra do parâmetro "Python" será um item na nova lista
   - lista_nova = ["P", "y", "t", "h", "o", "n"]

2) Seleção de Elementos por Posição
- Para selecionar um elemento da lista utilizamos "lista[N]", onde N é a posição do elemento a ser selecionado
   - Lembrando que Python é 0-Based, logo, o Primeiro elemento da Lista é o de numeração 0 e as contagens de N vão até N-1

Ex.: lista = ["P", "y", "t", "h", "o", "n"]
lista[2] = "t"


2.1) Múltiplos Elementos
- Para selecionar múltiplos elementos podemos pegá-los individualmente pelas suas posições

Ex.: lista = ["P", "y", "t", "h", "o", "n"]
lista[1, 3, 5] = "y", "h", "n"

- Outro método é determinar um segmento da lista utilizando [:]
   - [N:] seleciona todos os elementos à partir da Posição N+1 até a última posição da lista
   - [:N] seleciona todos os elementos até a Posição N-1 desde a primeira posição da lista
   - [N:X] seleciona todos os elementos à partir da Posição N até a posição X-1

Ex.: lista = ["P", "y", "t", "h", "o", "n"]
lista[:2] = "P", "y"
lista[2:] = "t", "h", "o", "n"
lista[1:3] = "y", "t"

2.2) Step
- O Step pode ser utilizado para pular uma quantidade de elementos na contagem da lista
   - lista[N:X:S] onde S é a quantidade a ser contada, ao invés de 1 a 1

Ex.: lista = ["P", "y", "t", "h", "o", "n"]
lista[0:5:2] = "P", "t", "o"

2.3) Inversão de Lista
- É possível inverter a lista sem o list.reverse, utilizando um step negativo e nenhum parâmetro

Ex.: lista = ["P", "y", "t", "h", "o", "n"]
lista[::-1] = "n", "o", "h", "t", "y", "P" 
