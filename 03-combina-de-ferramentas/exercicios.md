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

## 4. Como posso combinar vários comandos?
* **Conceito:** É possível encadear múltiplos comandos em sequência usando vários pipes (`cmd1 | cmd2 | cmd3`).

Exercício: Pegue a coluna 2 de `seasonal/summer.csv`, remova o cabeçalho "Tooth" e selecione apenas o primeiro nome de dente.

Comando:

```Bash
cut -d , -f 2 seasonal/summer.csv | grep -v Tooth | head -n 1
```

---

## 5. Como posso contar os registros em um arquivo?
* **Conceito:** O comando `wc (word count)` conta caracteres (`-c`), palavras (`-w`) e linhas (`-l`). A flag `-l` é ideal para contar registros em um arquivo de dados.

* **Exercício:** Conte quantos registros em `seasonal/spring.csv` contêm a data de julho de 2017 (2017-07).

Comando:

```Bash
grep 2017-07 seasonal/spring.csv | wc -l
```

---

## 6. Como posso especificar vários arquivos de uma vez? (Wildcards)
* **Conceito:** O caractere curinga * (asterisco) substitui zero ou mais caracteres em nomes de arquivos,
permitindo selecionar múltiplos arquivos de forma dinâmica.

* **Exercício:** Exiba as 3 primeiras linhas dos arquivos `spring.csv` e `summer.csv` no `diretório seasonal/` usando um curinga.

Comando:

```Bash
head -n 3 seasonal/s*.csv
```

---

## 7. Que outros curingas posso usar?

* **Conceito:**

- `?`: Corresponde a exatamente um caractere qualquer.

- `[...]`: Corresponde a qualquer um dos caracteres dentro dos colchetes.

- `{...}`: Expande alternativas separadas por vírgula.

* **Pergunta:* Qual expressão corresponde a `singh.pdf` e `johel.txt`, mas descarta `sandhu.pdf` e `sandhu.txt`?

* **Resposta Correta:** `{singh.pdf, j*.txt}`

* **Reflexão:**

`singh.pdf` busca o arquivo exato.

`j*.txt` pega qualquer arquivo que inicie com j e termine em .txt (como johel.txt).

As combinações`sandhu.*` são descartadas por não casar com nenhuma das opções.


