# Módulo 2: Manipulação de dados -  Exercícios

Este diretório contém as anotações teóricas e as
soluções práticas dos exercícios do segundo capítulo
do curso de **Introdução ao Shell** no DataCamp.

---

## 1. Como posso visualizar o conteúdo de um arquivo?
* **Conceito:** O comando `cat` (*concatenate*) imprime todo o conteúdo de um arquivo diretamente na tela do terminal.
* **Comando:**

```bash
  cat course.txt

```

## 2. Como posso visualizar o conteúdo de um arquivo, uma parte de cada vez?

**Conceito**: O comando less permite visualizar arquivos grandes de forma paginada.

`Barra de espaço:` avança uma página.

`:n:` avança para o próximo arquivo da lista.

`:p:` volta para o arquivo anterior.

`:q:` sai do visualizador.

**Comando:**

```Bash
less seasonal/spring.csv seasonal/summer.csv
```

## 3. Como posso digitar menos? (Autocompletar com Tab)
**Conceito:** A tecla Tab completa automaticamente
caminhos de arquivos e diretórios, evitando erros de digitação e economizando tempo.

**Comandos:**

```bash
# Digite 'head sea' + Tab -> completa para 'seasonal/'
# Digite 'a' + Tab -> completa para 'autumn.csv'
head seasonal/autumn.csv

# Repita para o arquivo spring.csv usando Tab
head seasonal/spring.csv
```
# 4. Como posso controlar o que os comandos fazem? (Flags)

**Conceito:** O sinalizador (flag) `-n` altera o comportamento
do comando head, permitindo especificar exatamente a quantidade
de linhas que serão exibidas.

**Comando:**

```Bash
head -n 5 seasonal/winter.csv
```

## 5. Como posso listar tudo abaixo de um diretório?
**Conceito:**

`-R` (recursivo): lista todos os arquivos e subdiretórios em todos os níveis.

`-F:` adiciona / ao final de diretórios e * ao final de arquivos executáveis.

**Comando:**

```Bash
ls -R -F /home/repl
```

## 6. Como posso obter ajuda para um comando?
**Conceito:** O comando man abre o manual do comando desejado.

No sinalizador `-n` do comando tail, usar o sinal `+N` faz o 
comando imprimir doN-ésimo item até o final.

**Comando:**
```Bash
# Passo 1: Abrir e ler o manual (navegue com espaço, saia com q)
man tail

# Passo 2: Exibir a partir da 7ª linha (ignorando as 6 primeiras)
tail -n +7 seasonal/spring.csv

```

**7. Como posso selecionar as colunas de um arquivo?**

**Conceito:** O comando cut é utilizado para extrair colunas
de arquivos de texto. Ele utiliza `-f` (fields) para as colunas
e `-d` (delimiter) para o caractere separador.

Pergunta do Exercício: Que comando seleciona a primeira coluna do arquivo spring.csv?

Resposta Correta: Qualquer uma das opções acima.

Explicação: Tanto `cut -d` , `-f 1 seasonal/spring.csv` quanto `cut -d, -f1 seasonal/spring.csv` funcionam identicamente.

**8. O que o cut não pode fazer?**

**Conceito:** O cut não reconhece aspas em arquivos CSV/texto. Se uma coluna contiver vírgulas entre aspas, o cut interpretará essa vírgula como um novo separador.

Pergunta do Exercício: Qual é a saída de `cut -d : -f 2-4` na linha first:second:third:?

Resposta Correta: second:third:

Explicação:

Campo 1: first

Campo 2: second

Campo 3: third

Campo 4: `` (vazio)

O intervalo `-f 2-4` une do campo 2 ao 4 com o delimitador `:`, gerando `second:third:`.

**9. Como posso repetir comandos?**

**Conceito:** O comando history exibe o histórico de comandos executados.
É possível reutilizar comandos com as setas para cima/baixo do teclado ou
com o operador !.

Comando:
```Bash
# Digite o comando (o exercício espera que ele falhe pois o arquivo está em seasonal/)
head summer.csv
```

**10. Como posso selecionar as linhas que contêm determinados valores?**

**Conceito:** O comando grep busca por palavras ou padrões de texto 
dentro de arquivos e imprime as linhas correspondentes.

Comando:
```Bash
grep molar seasonal/autumn.csv
```
## 11. Por que não é sempre seguro tratar dados como texto?

**Conceito:** O comando paste une arquivos linha por linha, 
sem entender o significado dos dados ou estruturas como cabeçalhos.

Pergunta do Exercício: O que há de errado ao unir os dois arquivos com paste?

Resposta Correta: Os cabeçalhos das colunas são repetidos.

Explicação: Ele junta a primeira linha de cada arquivo, 
fazendo com que a linha de títulos de winter.csv apareça no
meio das colunas resultantes.