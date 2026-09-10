# Mini-Projeto Avaliativo: Análise Exploratória e Pipeline ETL - Base Varejo

**Curso:** Carreira Tech - Trilha Análise de Dados  
**Módulo:** 01 | **Semana:** 07  
**Turma:** `Analise_de_Dados_T6`  
**Aluno:** Mario Enrique Calvo Medina  

---

##  1. Visão Geral do Projeto
Este projeto consiste no desenvolvimento de um pipeline de **ETL (Extract, Transform, Load)** e uma **Análise Exploratória de Dados (AED)** aplicada a uma base de dados reais do setor varejista. O objetivo principal foi identificar inconsistências estruturais, realizar a limpeza e padronização dos dados com Python (Pandas e Seaborn) e gerar visualizações para suporte à tomada de decisão.

---

## 2. Estrutura do Repositório


├── Base Varejo.csv                    # "/content/drive/MyDrive/Colab Notebooks/Analise de Dados /Base Varejo.csv"
├── Varejocsv_tratado.csv              # "/content/drive/MyDrive/Colab Notebooks/Analise de Dados /Varejocsv_tratado.csv"
├── Miniprojeto_Analise_Varejo.ipynb   # Notebook com código comentado e em execução
├── painel_visualizacao_varejo.png     # Painel de gráficos exportado via Seaborn
└── README.md                          # Documentação e reflexão teórica do projeto

---

## 3. Para descarregar arquivos referenciais

├── https://drive.google.com/file/d/1XzXLe3qRQoG-sXyekl3Z97JWuDP1bB2U/view?usp=drive_link
├── https://drive.google.com/file/d/10myT5wjE0MhH6Ws-TtfdLKx9ObFKM-mn/view?usp=drive_link

---
## 4. Insights da Análise

**Eliminação de Distorções:** A remoção das duplicatas reduziu a base em 11,6%, corrigindo distorções no cálculo do volume real de transações.

**Dominância de Categorias:** As categorias Alimentos (384.197 itens) e Higiene (137.702 itens) representam a maior fatia do volume de itens vendidos no varejo.

**Perfil Familiar dos Clientes:** A análise da coluna de número de filhos (CL_FHL) indicou média de 1,14 filhos, com mediana e moda igual a 0, apontando forte concentração de clientes sem dependentes ou com até 2 filhos.

**Volume por Gênero:** A contagem de compras únicas (CO_ID) revelou um público equilibrado, com ligeira predominância de compras realizadas pelo público feminino (9.615 pedidos únicos vs. 8.856 do público masculino).

**Comportamento por Carrinho:** Confirmou-se que cada linha da base representa um item individual, sendo a coluna CO_ID necessária para agrupar e identificar pedidos completos.

**Limitações Remanescentes:** A base original não possui colunas de preços unitários ou faturamento monetário (R$), limitando a análise exploratória ao volume físico de itens e frequência de compras.

## 5. Dificuldades Encontradas 

- O processo de estruturação do código e preparação do pipeline de dados passou por desafios técnicos em limpeza de dados, visualização e requisitos do repositório:

- Engenharia de Dados e Qualidade da Base (ETL)

- Colunas Fantasmas (Unnamed): Delimitadores (;) excedentes no arquivo original geraram 4 colunas nulas adicionais e 3,32 milhões de valores nulos ocultos.

- Inconsistências Mapeadas como Texto: As falhas de preenchimento em categorias e nomes de produtos vieram gravadas como a string "#N/D" em vez de valores ausentes padrões (NaN), exigindo tratamento condicional específico antes do preenchimento.

- Volume Significativo de Duplicatas: A identificação e eliminação de 96.553 linhas repetidas (11,6% da base) para evitar a inflação artificial dos números de vendas.

- Regras de Negócio e Agrupamentos

- Granularidade do Carrinho de Compras: A constatação de que cada linha representa um item isolado e não um pedido fechado. Para obter o total real de compras por gênero, foi necessário aplicar a contagem distinta (nunique()) na coluna CO_ID.

- Ausência de Dados Monetários: A base original limita-se a volumes físicos de itens, impedindo análises diretas de faturamento financeiro (R$).

- Ajustes de Código e Bibliotecas (Python / Seaborn / Colab)

- Tipagem Temporal: A coluna DATA foi importada originalmente como texto (object), impedindo a criação de gráficos de linha temporais até a conversão por pd.to_datetime().

- Alertas de Depreciação no Seaborn: A atualização do Seaborn passou a emitir FutureWarning ao utilizar o parâmetro palette sem atribuir a variável categórica ao parâmetro hue.

- Caminhos de Arquivo no Google Drive: Gerenciamento do caminho do diretório com espaços no Google Colab (/Colab Notebooks/Analise de Dados /).

