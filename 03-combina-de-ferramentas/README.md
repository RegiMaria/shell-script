# Módulo 3: Combinação de Ferramentas

Este módulo apresenta o verdadeiro poder do Unix: redirecionadores,
*pipes* e caracteres curinga (*wildcards*), que permitem encadear comandos simples para construir
fluxos de processamento complexos de dados.

### Resumo de Comandos e Operadores

| Comando / Operador | Descrição | Exemplo de Uso |
| :--- | :--- | :--- |
| `>` | Redireciona a saída de um comando para um arquivo (sobrescreve o conteúdo). | `head -n 5 seasonal/summer.csv > top.csv` |
| `>>` | Redireciona a saída acrescentando ao final do arquivo (*append*). | `tail -n 2 seasonal/winter.csv >> top.csv` |
| `<` | Usa o conteúdo de um arquivo como entrada padrão para um comando. | `cmd < input.txt` |
| `\|` (*pipe*) | Conecta a saída de um comando diretamente como entrada para outro. | `head -n 5 seasonal/summer.csv \| tail -n 1` |
| `wc` | Conta linhas, palavras e caracteres de um arquivo (`-l` para linhas). | `wc -l seasonal/*.csv` |
| `*` | Curinga que substitui zero ou mais caracteres em nomes de arquivos. | `ls seasonal/*.csv` |
| `?` | Curinga que substitui exatamente um caractere qualquer. | `ls seasonal/s?mmer.csv` |
| `[...]` | Curinga que corresponde a qualquer um dos caracteres entre colchetes. | `ls seasonal/[as]*` |
| `{...}` | Expansão de chaves para especificar alternativas em nomes. | `ls seasonal/{spring,summer}.csv` |
| `sort` | Classifica/ordena linhas de texto (`-n` ordenação numérica, `-r` reversa). | `cut -d , -f 2 seasonal/winter.csv \| sort` |
| `uniq` | Remove ou conta linhas duplicadas **adjacentes** (`-c` conta ocorrências). | `sort dados.txt \| uniq -c` |
| `Ctrl + C` | Envia o sinal `SIGINT` para interromper imediatamente um programa travado. | `Ctrl + C` |

###  Conceitos Chave

* **Pipes (`\|`):** Evitam a criação de arquivos temporários desnecessários no disco, passando os dados diretamente pela memória de um programa para o outro.
* **Uso combinado `sort \| uniq`:** Como o `uniq` só remove duplicatas que estejam em linhas vizinhas, **sempre devemos rodar `sort` antes do `uniq`**.
* **Wildcards (Curingas):** O próprio shell se encarrega de expandir os curingas antes mesmo de repassá-los para os comandos.
