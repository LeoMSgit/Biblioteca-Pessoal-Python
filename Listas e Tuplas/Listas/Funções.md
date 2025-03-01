# Manipulação de Listas em Python

## 1) Definição

```python
lista = ["elemento1", "elemento2", "elemento3", ..., "elementoN"]
lista = list("Python")  # Cria uma lista onde cada letra da string se torna um elemento
print(lista)  # Saída: ['P', 'y', 't', 'h', 'o', 'n']
```

## 2) Seleção de Elementos por Posição

- O primeiro elemento tem índice **0** (Python usa indexação baseada em zero).
- Acessamos um elemento com `lista[N]`.

```python
lista = ["P", "y", "t", "h", "o", "n"]
print(lista[2])  # Saída: 't'
```

## 2.1) Selecionando Múltiplos Elementos

- Para selecionar elementos individuais utilizamos comprehension, onde criamos uma lista nova utilizando como parâmetros os elementos nas posições selecionadas

```python
indices = [1, 3, 5]
selecionados = [lista[i] for i in indices]
print(selecionados)  # Saída: ['y', 'h', 'n']
```

## 2.2) Slicing

- `[N:]` → Elementos a partir do índice `N`.
- `[:N]` → Elementos do início até `N-1`.
- `[N:X]` → Elementos entre `N` e `X-1`.

```python
lista = ["P", "y", "t", "h", "o", "n"]
print(lista[:2])   # Saída: ['P', 'y']
print(lista[2:])   # Saída: ['t', 'h', 'o', 'n']
print(lista[1:3])  # Saída: ['y', 't']
```

## 2.3) Step (Passo)

- `lista[N:X:S]` → `S` define quantos elementos pular.

```python
lista = ["P", "y", "t", "h", "o", "n"]
print(lista[0:6:2])  # Saída: ['P', 't', 'o']
```

## 2.4) Inversão de Lista

- Podemos inverter uma lista usando slicing:

```python
lista = ["P", "y", "t", "h", "o", "n"]
lista_invertida = lista[::-1]
print(lista_invertida)  # Saída: ['n', 'o', 'h', 't', 'y', 'P']
