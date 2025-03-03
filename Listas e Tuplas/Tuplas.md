# Tuplas em Python

Tuplas são estruturas de dados imutáveis em Python, usadas para armazenar uma sequência ordenada de elementos. Diferente das listas, que podem ser modificadas (mutáveis), as tuplas são fixas após a sua criação, tornando-as mais eficientes e seguras para armazenar dados que não devem ser alterados
Tuplas são representadas com parênteses `minha_tupla(1,2,3,4,5)`


## Características das Tuplas
- **Imutabilidade:** Não podem ser modificadas após a criação (não permitem adição, remoção ou alteração de elementos)
- **Indexação e Fatiamento:** Assim como listas, suportam acesso por índice e slicing
- **Armazenam Tipos Diversos:** Podem conter diferentes tipos de dados, como inteiros, strings, listas, dicionários, etc.
- **Uso em Estruturas de Dados:** São utilizadas quando a integridade dos dados é essencial, como chaves em dicionários
- **Eficiência:** Mais eficientes que listas em termos de desempenho para leitura de dados

## Criando Tuplas
- Tuplas podem ser definidas de várias formas
```python
# Tupla vazia
minha_tupla = ()

# Tupla com elementos
tupla_numeros = (1, 2, 3, 4, 5)

# Tupla com diferentes tipos de dados
tupla_mista = (1, "Python", [10, 20], {'chave': 'valor'})

# Tupla sem parênteses (packing)
tupla_implícita = 10, 20, 30
```

## Acessando Elementos
- A indexação em tuplas segue o mesmo padrão das listas
```python
# Acesso por índice
print(tupla_numeros[0])  # Saída: 1

# Fatiamento
print(tupla_numeros[1:4])  # Saída: (2, 3, 4)

# Último elemento
print(tupla_numeros[-1])  # Saída: 5
```

## Métodos de Tuplas
Apesar de serem imutáveis, tuplas possuem alguns métodos úteis

### 1) `count(valor)`
Conta quantas vezes um elemento aparece na tupla
```python
tupla = (1, 2, 2, 3, 2, 4)
print(tupla.count(2))  # Saída: 3
```

### 2) `index(valor, inicio, fim)`
Retorna o índice da primeira ocorrência de um elemento. Pode opcionalmente receber um intervalo de busca
```python
tupla = (10, 20, 30, 40, 20)
print(tupla.index(20))  # Saída: 1
print(tupla.index(20, 2))  # Saída: 4 (procura a partir do índice 2)
```

## Desempacotamento de Tuplas
Podemos extrair os valores de uma tupla diretamente para variáveis
```python
tupla = ("Python", 3.9, 2023)
nome, versao, ano = tupla
print(nome)  # Saída: Python
print(versao)  # Saída: 3.9
print(ano)  # Saída: 2023
```

Se houver mais valores do que variáveis, podemos usar `*` para capturar múltiplos elementos
```python
tupla = (1, 2, 3, 4, 5)
a, *meio, b = tupla
print(a)  # Saída: 1
print(meio)  # Saída: [2, 3, 4]
print(b)  # Saída: 5
```

## Conversão entre Listas e Tuplas
Podemos converter listas em tuplas e vice-versa
```python
lista = [1, 2, 3]
tupla = tuple(lista)
print(tupla)  # Saída: (1, 2, 3)

nova_lista = list(tupla)
print(nova_lista)  # Saída: [1, 2, 3]
```

## Uso de Tuplas como Chaves de Dicionários
Por serem imutáveis, tuplas podem ser usadas como chaves em dicionários
```python
dicionario = {
    (1, 2): "Coordenada A",
    (3, 4): "Coordenada B"
}
print(dicionario[(1, 2)])  # Saída: Coordenada A
```
