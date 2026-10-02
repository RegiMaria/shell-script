<div align="center">
  <img src="https://github.com/user-attachments/assets/dec0a118-b89c-4ea7-889a-5fb99af35ddc" />
</div>


# Introdução ao Shell 💻

Este repositório contém anotações, explicações e soluções de exercícios do curso [**Introdução ao Shell** da DataCamp](https://app.datacamp.com/learn/courses).

---

## 📌 Sobre o Curso

* **Nível:** Básico
* **Duração estimada:** 4 horas
* **Quantidade de exercícios:** 55 exercícios

### 📖 Descrição
A linha de comando do Unix permite executar tarefas complexas com apenas alguns toques no teclado.
Conhecido como a "cola universal da programação", o shell ajuda a combinar programas, automatizar tarefas 
repetitivas e executar scripts em servidores locais ou na nuvem. Este curso apresenta os principais
elementos do shell e ensina como utilizá-los com eficiência.

---

## 🗂️ Estrutura do Curso

1. **[Módulo 1: Manipulação de arquivos e diretórios](https://github.com/RegiMaria/shell-script/tree/main/01-manipulacao-arquivos-diretorios)**
2. **[Módulo 2: Manipulação de dados](https://github.com/RegiMaria/shell-script/tree/main/02-manipulacao-dados)**
3. **Módulo 3: Combinação de ferramentas**
4. **Módulo 4: Processamento em lote**
5. **Módulo 5: Criação de novas ferramentas**

---

## 🚀 Módulo 1: Manipulação de Arquivos e Diretórios

Este módulo aborda os conceitos essenciais do sistema de arquivos Unix, como navegar entre pastas, entender caminhos absolutos e relativos e gerenciar arquivos e diretórios.

### 📌 Resumo de Comandos

| Comando | Descrição | Exemplo de Uso |
| :--- | :--- | :--- |
| `pwd` | Exibe o caminho do diretório atual (*Print Working Directory*). | `pwd` |
| `ls` | Lista arquivos e diretórios na pasta atual. | `ls` |
| `ls -F` | Lista arquivos e indica diretórios com uma barra `/`. | `ls -F` |
| `ls -a` | Lista todos os arquivos, incluindo ocultos (iniciados com `.`). | `ls -a` |
| `cd` | Altera o diretório de trabalho (*Change Directory*). | `cd seasonal` |
| `cp` | Copia arquivos de uma origem para um destino. | `cp dados.csv backup/` |
| `mv` | Move ou renomeia arquivos e diretórios. | `mv antigo.txt novo.txt` |
| `rm` | Remove/exclui arquivos permanentemente. | `rm arquivo.txt` |
| `mkdir` | Cria um novo diretório. | `mkdir nova_pasta` |
| `rmdir` | Exclui um diretório (somente se estiver vazio). | `rmdir pasta_vazia` |

### 💡 Conceitos Chave

* **Caminho Absoluto:** Endereço completo a partir do diretório raiz `/` (ex: `/home/repl/seasonal/summer.csv`).
* **Caminho Relativo:** Endereço especificado a partir do local atual (ex: `seasonal/summer.csv`).
* **Atalhos Úteis:**
  * `.` : Diretório atual.
  * `..` : Diretório pai (um nível acima).
  * `~` : Diretório pessoal (*Home*).
  * `/tmp` : Diretório temporário do sistema.

---

## 📊 Módulo 2: Manipulação de Dados

Este módulo aborda ferramentas fundamentais do Unix para inspecionar, filtrar e extrair dados de arquivos de texto de forma rápida diretamente no terminal.

### 📌 Resumo de Comandos

| Comando | Descrição | Exemplo de Uso |
| :--- | :--- | :--- |
| `cat` | Imprime todo o conteúdo de um arquivo na tela. | `cat course.txt` |
| `less` | Visualiza arquivos grandes com paginação (espaço rola, `:q` sai). | `less seasonal/spring.csv` |
| `head` | Exibe as primeiras linhas de um arquivo (`-n` especifica quantas). | `head -n 5 winter.csv` |
| `tail` | Exibe as últimas linhas de um arquivo (`-n +N` exibe a partir da linha N). | `tail -n +7 spring.csv` |
| `ls -R -F` | Lista de forma recursiva todos os subdiretórios e identifica pastas/executáveis. | `ls -R -F /home/repl` |
| `man` | Exibe a página do manual de ajuda de um comando. | `man tail` |
| `cut` | Extrai colunas específicas usando delimitadores (`-d`) e campos (`-f`). | `cut -d , -f 1 spring.csv` |
| `history` | Exibe o histórico de comandos executados recentemente. | `history` |
| `grep` | Busca e seleciona linhas que contêm um texto ou padrão específico. | `grep molar autumn.csv` |
| `paste` | Une arquivos de dados lado a lado linha por linha. | `paste autumn.csv winter.csv` |

### 💡 Conceitos Chave

* **Tab Completion:** Pressionar `Tab` completa automaticamente o nome de arquivos e pastas para economizar digitação e evitar erros.
* **Flags / Sinalizadores:** Modificam o comportamento dos comandos (ex: `-n` no `head`, `-R` no `ls`).
* **Limitações do `cut`:** O comando `cut` é simples e não interpreta aspas, podendo quebrar valores de colunas que contêm vírgulas internas.

---

## 📝 Licença & Créditos

Exercícios e materiais baseados no curso de Introdução ao Shell da plataforma de estudos [DataCamp](https://app.datacamp.com/).
