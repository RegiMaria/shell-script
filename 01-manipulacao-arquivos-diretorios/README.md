# Módulo 1: Manipulação de Arquivos e Diretórios

Este módulo aborda os conceitos essenciais do sistema de arquivos Unix,
como navegar entre pastas, entender caminhos absolutos e relativos e gerenciar arquivos e diretórios.

### Resumo de Comandos

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

### Conceitos Chave

* **Caminho Absoluto:** Endereço completo a partir do diretório raiz `/` (ex: `/home/repl/seasonal/summer.csv`).
* **Caminho Relativo:** Endereço especificado a partir do local atual (ex: `seasonal/summer.csv`).
* **Atalhos Úteis:**
  * `.` : Diretório atual.
  * `..` : Diretório pai (um nível acima).
  * `~` : Diretório pessoal (*Home*).
  * `/tmp` : Diretório temporário do sistema.
