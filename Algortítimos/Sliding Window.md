## O que é o “Sliding Window”?

Em estruturas sequenciais (strings, listas, arrays, streams) um **sliding window** (“janela deslizante”) é um intervalo **contíguo** delimitado por dois índices — normalmente chamados **`left`** (início) e **`right`** (fim).
Enquanto percorremos a sequência, movemos um ou ambos os ponteiros para **expandir** ou **contrair** a janela, calculando estatísticas ou testando condições **em tempo O(1)** por passo, em vez de recomputar tudo do zero.

---

## 1. Anatomia da Técnica

| Etapa                    | Ação                                        | Objetivo                                                                                                       |
| ------------------------ | ------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| **Expansão** (`right++`) | Acrescenta o próximo elemento à janela.     | Garantir que a janela passe a conter a informação necessária (ex.: soma ≥ K, todos os caracteres de *t* etc.). |
| **Verificação**          | Testa se a janela cumpre uma condição‐alvo. | Saber se podemos tentar encolher para otimizar.                                                                |
| **Contração** (`left++`) | Remove o elemento da esquerda.              | Minimizar a janela (quando ela já é válida) ou baixar algum valor (quando excede um limite).                   |

> A **janela** é sempre `seq[left : right + 1]`.

---

## 2. Tipos Clássicos de Janela

1. **Tamanho fixo (Fixed Window)**

   * O intervalo tem comprimento constante `k`.
   * A cada passo: remove‐se `seq[left]` e insere‐se `seq[right+1]`.
   * Exemplos: média móvel, soma máxima de subarray de tamanho *k*.

2. **Tamanho variável (Dynamic/Adaptive Window)**

   * A janela cresce até satisfazer um critério, depois encolhe o máximo que puder sem perder a validade.
   * Exemplos: *Minimum Window Substring*, maior substring sem caracteres repetidos, menores subarrays com soma ≥ K.

---

## 3. Estruturas de Apoio

| Estrutura                                | Quando usar                                                            | Por quê?                                                                                         |
| ---------------------------------------- | ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| **`Counter` / dicionário de frequência** | Procurar requisitos de múltiplos tipos de item (caracteres, inteiros). | Permite saber rapidamente se a janela já possui a **quantidade mínima** necessária de cada item. |
| **Deque**                                | Precisamos do valor máximo/mínimo da janela fixa.                      | Mantém índices em ordem de valor, garantindo remoção/inserção O(1).                              |
| **Soma acumulada (prefix sum)**          | Janelas fixas com operações lineares (soma)                            | Evita recalcular soma inteira; apenas adiciona e remove uma extremidade.                         |
| **Bitset / Máscara**                     | Pequeno alfabeto (ex.: DNA ACGT)                                       | Opera via operações bit a bit extremamente rápidas.                                              |

---

## 4. Complexidade

* **Tempo:**
  Cada elemento entra e sai da janela **uma única vez** ⇒ O(*n*), onde *n* = |sequência|.
* **Espaço:**
  O(tamanho do alfabeto ou da janela auxiliar). Geralmente O(|Σ|) ou O(*k*).

---

## 5. Padrão de Implementação (dinâmica)

```python
def sliding_window(seq, valida, atualiza_entrada, atualiza_saida):
    left = 0
    estado = ...      # estrutura auxiliar (ex.: Counter, soma, deque...)
    for right, elem in enumerate(seq):
        atualiza_entrada(estado, elem)        # 1. expande

        while valida(estado):                 # 2. contração se possível
            # ← aqui já temos uma janela 'seq[left:right+1]' que serve
            processa_resposta(left, right)

            atualiza_saida(estado, seq[left]) # remove esquerda
            left += 1
```

* **`atualiza_entrada`**: insere `seq[right]` na estrutura auxiliar.
* **`valida`**: devolve `True` quando a condição alvo está satisfeita.
* **`atualiza_saida`**: retira `seq[left]` quando encolhemos.

---

## 6. Três Problemas Canônicos

| Problema                                      | Metodologia                     | Pontos‑chave                                                                |
| --------------------------------------------- | ------------------------------- | --------------------------------------------------------------------------- |
| **a) Soma máxima de subarray de tamanho *k*** | Janela fixa.                    | Atualizar soma: `soma += seq[r] - seq[l-1]`.                                |
| **b) Minimum Window Substring**               | Janela variável + `Counter`.    | `have / need` para saber quando a janela contém todos os caracteres de `t`. |
| **c) Maior substring sem repetir caracteres** | Janela variável + `set`/`dict`. | Enquanto há caractere duplicado, contraia a janela retirando da esquerda.   |

---

## 7. Armadilhas Comuns

1. **Off‑by‑one**: lembrar que o intervalo é inclusivo em `right` e exclusivo em `left` quando usamos slices.
2. **Atualizar a estrutura auxiliar na ordem errada**: primeiro insira o novo elemento, só depois teste a validade.
3. **Múltiplas aparições de um caractere**: sempre trabalhe com **contagens**, não apenas presença/ausência.
4. **Overflow de índices**: certifique‑se de mover `left` dentro do loop `while`, senão entra em loop infinito.

---

## 8. Extensões e Otimizações

* **Dois níveis de janela**: útil p/ problemas com duas condições diferentes (ex.: “contém X, tamanho ≤ Y”).
* **Janela 2‑D**: em matrizes, podemos fixar linhas e deslizar colunas (ou vice‑versa).
* **Slides lazy**: quando expandir custa caro (por ex. consultar disco), só processa se realmente precisar.
* **Janela sobre stream infinito**: manter estatísticas on‑the‑fly usando deque ou fila circular.

---

## 9. Visualização Rápida (Minimum Window)

```
s = A A A N E I C N A O R A V B A J J K A L B C N A
                ^               ^
              left            right
estado: {'A':5,'B':1,'C':1}  have=3 need=3 → válida
          └─ janela atual = “CNAORAVB” (tamanho 8)
```

1. **Expansão** chega a `right = 13` e torna a janela válida.
2. **Contração** move `left` de 0→7 para minimizar sem perder letras.
3. Salva resultado; volta a expandir até achar janela de tamanho 4 etc.

---

## 10. Resumo Final

* **Sliding window** explora a **contiguidade** para transformar problemas potencialmente O(*n²*) em O(*n*).
* Requer **duas operações simétricas** (inserir / remover extremidades) e uma forma rápida de testar a condição.
* Adapta‑se a inúmeras tarefas em algoritmos, processamento de sinais, análise de séries temporais e NLP.

Com estes princípios (e as variações de estrutura auxiliar) você pode resolver a maior parte dos problemas clássicos envolvendo subarrays ou substrings de forma eficiente.


Espaço O(|Σ|) — tamanho do alfabeto (tipicamente 128 ou 256).
