## 1) Definição

```python
lista = ["elemento1", "elemento2", "elemento3", ..., "elementoN"]
lista = list("Python")  # Cria uma lista onde cada letra da string se torna um elemento
print(lista)  # Saída: ['P', 'y', 't', 'h', 'o', 'n']
```

## 2) Seleção de Elementos por Posição

- O primeiro elemento tem índice **0** (Python usa indexação baseada em zero)
- Acessamos um elemento com o comando: `lista[N]`

```python
lista = ["P", "y", "t", "h", "o", "n"]
print(lista[2])  # Saída: 't'
```

## 2.1) Índices Negativos

- As listas em Python suportam índices negativos para contagem de posição, porém, a contagem começa em -1 na ÚLTIMA POSIÇÃO, diferentemente do 0-Based da contagem convencional

```python
print(lista[-1]) # Saída: ['n']
print(lista[-2]) # Saída: ['o']
```

## 2.2) Selecionando Múltiplos Elementos

- Para selecionar elementos individuais utilizamos comprehension, onde criamos uma lista nova utilizando como parâmetros os elementos nas posições selecionadas

```python
indices = [1, 3, 5]
selecionados = [lista[i] for i in indices]
print(selecionados)  # Saída: ['y', 'h', 'n']
```

## 2.3) Slicing/Fatiamento

- Podemos selecionar determinados segmentos da lista utilizando comandos como: 

- `[N:]` → Elementos a partir do índice `N`
- `[:N]` → Elementos do início até `N-1`
- `[N:X]` → Elementos entre `N` e `X-1`

```python
lista = ["P", "y", "t", "h", "o", "n"]
print(lista[:2])   # Saída: ['P', 'y']
print(lista[2:])   # Saída: ['t', 'h', 'o', 'n']
print(lista[1:3])  # Saída: ['y', 't']
```

## 2.4) Step/Passo

- Step permite alterar quantas possições serão percorridas por passagem na lista
   - Normalmente a contagem acontece de 1 em 1

- `lista[N:X:S]` → `S` define quantos elementos pular

```python
lista = ["P", "y", "t", "h", "o", "n"]
print(lista[0:6:2])  # Saída: ['P', 't', 'o']
```

## 2.5) Inversão de Lista

- Podemos inverter uma lista usando slicing e um step negativo, sem o list.reverse(lista)

```python
lista = ["P", "y", "t", "h", "o", "n"]
lista_invertida = lista[::-1]
print(lista_invertida)  # Saída: ['n', 'o', 'h', 't', 'y', 'P']
```

## 3) Listas Aninhadas

- Listas podem conter diversos tipos de dados, inclusive outras listas, desse modo é possível criar estruturas bidimensionais como matrizes

```python
Ex.: Matriz = [
[1, 2, 3],
["a", "b", "c"],
["△", "□", "◯"],
]
```

- A lista Matriz contém outras três listas Numeros = [1, 2, 3], Letras = ["a", "b", "c"], Simbolos = ["△", "□", "◯"]

## 3.1) Acessando Matrizes

- Para acessar um elemento de uma estrutura bidimensional utilizamos dois parâmetros:
  - A posição da sublista na lista mãe
  - A posição do elemento dentro de sua respectiva sublista

```python
Ex.: Matriz[0]  # Saída: [1, 2, 3]    OU SEJA a LISTA na POSIÇÃO 0
Matriz[0][0]  # Saída: [1]   OU SEJA a LISTA na POSIÇÃO 0 e o ELEMENTO na POSIÇÃO 0
Matriz[1][-1] # Saída: ['c']   OU SEJA a LISTA na POSIÇÃO 1 e o ELEMENTO na POSIÇÃO -1 (Última posição da Lista)
Matriz[-1][-2] # Saída: ['□']   OU SEJA a LISTA na POSIÇÃO -1 (Última lista) e o ELEMENTO na POSIÇÃO -2 (Penúltima posição da Lista)
```
