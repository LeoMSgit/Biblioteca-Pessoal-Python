# 1) Definição
- Em Python, métodos são funções características de um certo objeto e são utilizadas para realizar operações nesse objeto. No caso de listas, os métodos são usados para modificar, buscar, ordenar ou manipular os elementos dentro delas
- Os métodos de listas são chamados utilizando a sintaxe de ponto (.)

# 2) Adicionar Elementos
## 2.1) .append(elemento)
- Adiciona um `elemento` ao final da lista
  
```python
lista = ["P", "y", "t", "h", "o", "n", 1, 2, 3, 4, 5]
lista.append(6)  
print(lista)  
# Saída: ["P", "y", "t", "h", "o", "n", 1, 2, 3, 4, 5, 6]
```

## 2.2) .insert(index, elemento)
- Insere um elemento `elemento` em uma posição `index` específica e "empurra" os outros elementos para a próxima posição
  - Caso seja utilizado um `index` maior do que o tamanho da lista, o Python não gerará erro, em vez disso, o elemento será adicionado ao final da lista, como se tivéssemos usado `.append(elemento)`

```python
lista = ["P", "y", "t", "h", "o", "n", 1, 2, 3, 4, 5]
lista.insert(3, "X")  
print(lista)  
# Saída: ["P", "y", "t", "X", "h", "o", "n", 1, 2, 3, 4, 5]
```
Aqui o elemento `X` é insereido na poisção `3`, os outros elementos posteriores são movidos em uma posição


## 2.3) .extend(nova_lista)
- Concatena/Adiciona outra lista a sua lista original
  - Diferentemente do .set(), .extend **NÃO** remove as duplicatas, ele irá apenas juntar uma lista no final da outra
 
```python
lista = ["P", "y", "t", "h", "o", "n", 1, 2, 3, 4, 5]
nova_lista = [4, 5, 7, 8]
lista.extend(nova_lista)  
print(lista)  
# Saída: ["P", "y", "t", "h", "o", "n", 1, 2, 3, 4, 5, 4, 5, 7, 8]

```
Aqui a lista `nova_lista` é "colada" ao final da lista original, resultando em `[..., 4, 5, 4, 5, 7, 8]`

# 3) Remover Elementos 
## 3.1) .remove(elemento)
- Remove a primeira ocorrência do elemento na lista
  - Para remover **TODOS** os elementos desejados da lista, é necessário criar um loop utilizando `while`

```python
lista = ["P", "y", "t", "h", "o", "o", "o", "n", 1, 2, 3, 4, 5]
lista.remove("o")  
print(lista)  
# Saída: ["P", "y", "t", "h", "o", "o", "n", 1, 2, 3, 4, 5]
```
Aqui apenas a primeira ocorrência do elemento `"o"` foi removida
<br/>
<br/>
<br/>
```python
lista = [1, 2, 3, 4, 2, 5, 2, 6, 2, 7]
valor_remover = 2

while valor_remover in lista:
    lista.remove(valor_remover)

print(lista)
# Saída: [1, 3, 4, 5, 6, 7]
```
Aqui o loop `while` continuará a remover o elemento `2`, até que ele não seja mais encontrado na lista

## 3.2) .pop() ou .pop(index)
- Por padrão, remove o `último` elemento da lista. Porém pode utilizar um `index` para escolher uma posição para ser eliminada

```python
lista = ["P", "y", "t", "h", "o", "n", 1, 2, 3, 4, 5]
lista.pop()  
print(lista)  
# Saída: ["P", "y", "t", "h", "o", "n", 1, 2, 3, 4]
```
Aqui o elemento `5`, na última posição, foi removido da lista
<br/> <br/>

```python
lista = ["P", "y", "t", "h", "o", "n", 1, 2, 3, 4, 5]
lista.pop(2)  
print(lista)  
# Saída: ["P", "y", "h", "o", "n", 1, 2, 3, 4, 5]
```
Aqui o elemento `"t"`, na posição 2, foi removido da lista

## 3.3) .clear()
- Remove completamante **TODOS** os elementos da lista, deixando-a vazia,mas mantendo a referência à lista original
```python
lista = ["P", "y", "t", "h", "o", "n", 1, 2, 3, 4, 5]
lista.clear()
print(lista)
# Saída: []
```

# 4) Ordenação e Reversão
## 4.1) .sort(lista)
- 
