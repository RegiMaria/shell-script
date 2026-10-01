# Capítulo 1: Manipulação de Arquivos e Diretórios

Este arquivo contém os conceitos, enunciados e soluções de todos os exercícios do **Capítulo 1** do curso de **Introdução ao Shell**.

---

## 📑 Índice de Exercícios

1. [Como o shell se compara a uma interface de computador?](#1-como-o-shell-se-compara-a-uma-interface-de-computador)
2. [Onde estou?](#2-onde-estou)
3. [Como posso identificar arquivos e diretórios?](#3-como-posso-identificar-arquivos-e-diretórios)
4. [De que outra forma posso identificar arquivos e diretórios?](#4-de-que-outra-forma-posso-identificar-arquivos-e-diretórios)
5. [Como posso mudar para outro diretório?](#5-como-posso-mudar-para-outro-diretório)
6. [Como posso ir para um diretório acima?](#6-como-posso-ir-para-um-diretório-acima)
7. [Como posso copiar arquivos?](#7-como-posso-copiar-arquivos)
8. [Como posso mover um arquivo?](#8-como-posso-mover-um-arquivo)
9. [Como posso renomear arquivos?](#9-como-posso-renomear-arquivos)
10. [Como posso excluir arquivos?](#10-como-posso-excluir-arquivos)
11. [Como posso criar e excluir diretórios?](#11-como-posso-criar-e-excluir-diretórios)
12. [Concluindo](#12-concluindo)

---

### 1. Como o shell se compara a uma interface de computador?
* **Conceito:** A interface gráfica (GUI) utiliza ícones e cliques. O shell (CLI) opera por texto, facilitando automações e acesso a servidores remotos.

---

### 2. Onde estou?
* **Conceito:** O comando `pwd` (*Print Working Directory*) mostra o caminho completo da pasta atual.
* **Comando:**
  ```bash
  pwd
  ```

---

### 3. Como posso identificar arquivos e diretórios?
* **Conceito:** O comando `ls` lista os arquivos e subpastas no diretório de trabalho atual.
* **Comando:**
  ```bash
  ls
  ```

---

### 4. De que outra forma posso identificar arquivos e diretórios?
* **Conceito:** Diferença entre caminho absoluto (inicia com `/`) e caminho relativo (inicia a partir de onde você está).
* **Instruções e Soluções:**
  1. Liste o arquivo `/home/repl/course.txt` via caminho relativo estando em `/home/repl`:
     ```bash
     ls course.txt
     ```
  2. Liste `/home/repl/seasonal/summer.csv` via caminho relativo:
     ```bash
     ls seasonal/summer.csv
     ```
  3. Liste o conteúdo do diretório `/home/repl/people` via caminho relativo:
     ```bash
     ls people
     ```

---

### 5. Como posso mudar para outro diretório?
* **Conceito:** O comando `cd` (*Change Directory*) permite navegar entre pastas.
* **Instruções e Soluções:**
  1. Mudar para `/home/repl/seasonal` via caminho relativo:
     ```bash
     cd seasonal
     ```
  2. Verificar o diretório atual:
     ```bash
     pwd
     ```
  3. Listar o conteúdo do diretório atual:
     ```bash
     ls
     ```

---

### 6. Como posso ir para um diretório acima?
* **Conceito:** `..` indica o diretório pai (um nível acima), `.` indica o diretório atual e `~` indica o diretório pessoal (*home*).
* **Pergunta:** Estando em `/home/repl/seasonal`, para onde `cd ~/.../.` leva você?
* **Resposta Correta:** `/home/repl`

---

### 7. Como posso copiar arquivos?
* **Conceito:** O comando `cp` copia arquivos e diretórios.
* **Instruções e Soluções:**
  1. Copiar `seasonal/summer.csv` para `backup` chamando-o de `summer.bck`:
     ```bash
     cp seasonal/summer.csv backup/summer.bck
     ```
  2. Copiar `spring.csv` e `summer.csv` de `seasonal` para `backup`:
     ```bash
     cp seasonal/spring.csv seasonal/summer.csv backup
     ```

---

### 8. Como posso mover um arquivo?
* **Conceito:** O comando `mv` move arquivos entre diretórios.
* **Instrução e Solução:**
  1. Mover `spring.csv` e `summer.csv` de `seasonal` para `backup`:
     ```bash
     mv seasonal/spring.csv seasonal/summer.csv backup
     ```

---

### 9. Como posso renomear arquivos?
* **Conceito:** No Unix, o comando `mv` também é utilizado para renomear arquivos ao passar um novo nome de destino.
* **Exemplo de uso:**
  ```bash
  mv arquivo_antigo.txt arquivo_novo.txt
  ```

---

### 10. Como posso excluir arquivos?
* **Conceito:** O comando `rm` exclui arquivos permanentemente (não há lixeira no terminal).
* **Instruções e Soluções:**
  1. Entrar no diretório `seasonal`:
     ```bash
     cd seasonal
     ```
  2. Remover `autumn.csv`:
     ```bash
     rm autumn.csv
     ```
  3. Voltar para o diretório pessoal:
     ```bash
     cd ~
     ```
  4. Remover `seasonal/summer.csv` sem mudar de diretório:
     ```bash
     rm seasonal/summer.csv
     ```

---

### 11. Como posso criar e excluir diretórios?
* **Conceito:** `mkdir` cria diretórios e `rmdir` remove diretórios vazios.
* **Instruções e Soluções:**
  1. Excluir `agarwal.txt` em `people`:
     ```bash
     rm people/agarwal.txt
     ```
  2. Excluir o diretório `people`:
     ```bash
     rmdir people
     ```
  3. Criar diretório `yearly`:
     ```bash
     mkdir yearly
     ```
  4. Criar o diretório `2017` dentro de `yearly`:
     ```bash
     mkdir yearly/2017
     ```

---

### 12. Concluindo
* **Conceito:** O diretório `/tmp` armazena arquivos temporários do sistema.
* **Instruções e Soluções:**
  1. Entrar em `/tmp`:
     ```bash
     cd /tmp
     ```
  2. Listar o conteúdo de `/tmp`:
     ```bash
     ls
     ```
  3. Criar o diretório `scratch` dentro de `/tmp`:
     ```bash
     mkdir scratch
     ```
  4. Mover `~/people/agarwal.txt` para `scratch`:
     ```bash
     mv ~/people/agarwal.txt scratch
     ```