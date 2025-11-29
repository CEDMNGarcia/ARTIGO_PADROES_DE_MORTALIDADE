# Análise de Dados de Mortalidade (Óbitos) por Capítulo da CID-10, Idade e Sexo

## 1. Contexto Científico e Publicação

Este repositório contém o código-fonte (*Jupyter Notebook*) utilizado para a análise de dados que subsidiou o artigo científico a seguir.

| Detalhe | Especificação | Referência |
| :--- | :--- | :--- |
| **Título do Artigo** | PADRÕES DE MORTALIDADE NO BRASIL: UMA ANÁLISE EXPLORATÓRIA POR SEXO E FAIXA ETÁRIA | |
| **Evento de Submissão** | II CONGRESSO NACIONAL DE SAÚDE COLETIVA (II CONSAC) | |
| **Área Temática** | AT01: Saúde Pública | |

### Principais Achados (Resumo)

O estudo analisou os padrões de mortalidade no Brasil no ano de 2022, focando nas variáveis demográficas de idade e sexo:
* **Idade como Fator Predominante:** A idade é o principal fator que influencia o volume de óbitos, com a maior incidência concentrada nas faixas etárias acima de 35 anos. Foi observada uma forte correlação entre os grupos mais velhos.
* **Variabilidade por Sexo:** Embora homens e mulheres apresentem tendências de óbitos semelhantes, o sexo masculino demonstrou maior amplitude e variabilidade nos indicadores.
* **Vulnerabilidades Específicas:** O sexo masculino apresenta uma participação significativamente maior em **Causas Externas** (CID-10 XX), representando 73,9% dos óbitos nessa categoria, o que reflete vulnerabilidades sociais e de segurança. A distinção por sexo é crucial para a compreensão das causas de morte.

---

## 2. Descrição Técnica do Projeto

O *Jupyter Notebook* (`Untitled0.ipynb`) tem como finalidade principal a **preparação e integração** de dois conjuntos de dados de mortalidade, visando criar um *DataFrame* unificado para análises epidemiológicas. O processo inclui:
1.  Leitura e limpeza dos dados de óbitos por faixa etária (`obitos-idade.csv`).
2.  Leitura e limpeza dos dados de óbitos por sexo (`sexo-obitos.csv`).
3.  Mesclagem (*Merge*) dos dados através da coluna comum `'Capítulo CID-10'`.

## 3. Fontes de Dados

Os dados utilizados são públicos e provenientes do DATASUS (Ministério da Saúde do Brasil), referentes aos registros de óbitos ocorridos no ano de 2022.

| Arquivo | Conteúdo | Finalidade |
| :--- | :--- | :--- |
| `obitos-idade.csv` | Tabela de mortalidade desagregada por **Capítulo CID-10** e **faixa etária**. | Geração do *DataFrame* `df` |
| `sexo-obitos.csv` | Tabela de mortalidade desagregada por **Capítulo CID-10** e **sexo**. | Geração do *DataFrame* `df_sexo` |

**Formato Esperado dos Arquivos:**
Os arquivos `.csv` devem ser lidos com separador de colunas **ponto e vírgula** (`sep=;`) e a leitura deve começar a partir da 4ª linha, ignorando o cabeçalho inicial (`skiprows=3`).

---

## 4. Requisitos de Software

Para a execução e reprodução do código, são necessárias as seguintes bibliotecas Python:

* **`pandas`**: Essencial para a manipulação, limpeza e mesclagem dos dados.
* **`matplotlib`**: Utilizada para a geração de visualizações de dados (gráficos e *boxplots*).

### Instalação das Dependências

```bash
pip install pandas matplotlib
```
---
### Instruções para Reprodução

O processo de execução do *Jupyter Notebook* (`Untitled0.ipynb`) deve seguir os seguintes passos para garantir a correta preparação dos dados e a reprodutibilidade da análise:

1.  **Configuração do Ambiente:** Salve o *Jupyter Notebook* (`Untitled0.ipynb`) e os dois arquivos de dados (`obitos-idade.csv` e `sexo-obitos.csv`) em um diretório de trabalho comum.

2.  **Execução do Notebook:** Abra o arquivo `Untitled0.ipynb` em um ambiente Jupyter de sua preferência (Jupyter Lab, VS Code, Google Colab).

3.  **Montagem do Drive (Apenas Colab):** Caso esteja utilizando o ambiente **Google Colab**, a célula de montagem do Google Drive deve ser executada para garantir o acesso aos arquivos:

    ```python
    from google.colab import drive
    drive.mount('/content/drive')
    ```
    *É fundamental que os caminhos de leitura dos dados (`pd.read_csv`) sejam ajustados para refletir a localização exata dos seus arquivos no Drive.*

4.  **Processamento:** Execute sequencialmente todas as células do *notebook* para realizar o carregamento, a limpeza e a integração dos dados, gerando o *DataFrame* unificado para análise.
