# 1) Definição
- Em Python, métodos são funções características de um certo objeto e são utilizadas para realizar operações nesse objeto. No caso de listas, os métodos são usados para modificar, buscar, ordenar ou manipular os elementos dentro delas
- Os métodos de listas são chamados utilizando a sintaxe de ponto (.)

# 2) Manipulação de Listas
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
# Saída: ["P", "y", "t", "X", "h", "o", "n", 1, 2, 3, 4, 5, 6]
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

- extend(): Adiciona múltiplos elementos ao final da lista.
- insert(i, elemento): Insere um elemento na posição i.
- remove(valor): Remove a primeira ocorrência do valor na lista.
- pop(i): Remove e retorna o elemento na posição i (se omitido, remove o último).
