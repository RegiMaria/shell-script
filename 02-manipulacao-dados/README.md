# Módulo 2: Manipulação de Dados

Este módulo aborda ferramentas fundamentais do Unix para inspecionar,
filtrar e extrair dados de arquivos de texto de forma rápida diretamente no terminal.

### Resumo de Comandos

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

### Conceitos Chave

* **Tab Completion:** Pressionar `Tab` completa automaticamente o nome de arquivos e pastas para economizar digitação e evitar erros.
* **Flags / Sinalizadores:** Modificam o comportamento dos comandos (ex: `-n` no `head`, `-R` no `ls`).
* **Limitações do `cut`:** O comando `cut` é simples e não interpreta aspas, podendo quebrar valores de colunas que contêm vírgulas internas.

---
