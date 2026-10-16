# Módulo 3: Combinação de Ferramentas 

Este diretório contém as anotações teóricas, explicações,
reflexões e soluções práticas dos exercícios do terceiro
capítulo do curso **Introdução ao Shell** da DataCamp.

---

## 1. Como posso armazenar a saída de um comando em um arquivo?
* **Conceito:** O operador `>` (redirecionador) salva a saída padrão (*stdout*) de um comando em um arquivo. Se o arquivo não existir, ele será criado; se já existir, seu conteúdo será sobrescrito.
* **Exercício:** Salve as últimas 5 linhas de `seasonal/winter.csv` em `last.csv`.
* **Comando:**
  ```bash
  tail -n 5 seasonal/winter.csv > last.csv
  ```
  
---

## 2. Como posso usar a saída de um comando como entrada?
* **Conceito:** É possível usar arquivos intermediários para encadear a saída de um comando como entrada para o próximo.
* **Exercício:**
1. Salve as duas últimas linhas de `seasonal/winter.csv` em `bottom.csv`.
2. Pegue a primeira linha de `bottom.csv` (obtendo a penúltima linha do arquivo original).

Comandos:

```Bash

# Passo 1
tail -n 2 seasonal/winter.csv > bottom.csv

# Passo 2
head -n 1 bottom.csv
```

---

## 3. Qual é a melhor maneira de combinar comandos? (Pipes)
* **Conceito:** O operador `|` (pipe) conecta a saída de um comando
diretamente como entrada para o próximo na memória, sem a necessidade
de criar arquivos temporários intermediários.

* **Exercício:** Extraia a coluna 2 de `seasonal/summer.csv` e remova o cabeçalho "Tooth".

Comando:

```Bash
cut -d , -f 2 seasonal/summer.csv | grep -v Tooth
```

---






