# Miniprojeto_MarioEnriqueMedina_Analise_de_Dados_T6
Mini projeto analise de dados T6. Modulo 01.

Miniprojeto Avaliativo — AED Base Varejo

Análise Exploratória de Dados (AED) aplicada a uma base de varejo, desenvolvida para o Módulo 1 da disciplina de Análise de Dados (Turma: Analise_de_Dados_T6).

Sobre o projeto

A base Base_Varejo.csv contém registros reais de compras (data, cliente, produto, categoria), em que cada linha representa um item comprado, não uma compra inteira — várias linhas podem compartilhar o mesmo CO_ID (identificador da compra).

O script Miniprojeto_Varejo.py realiza, em ordem:

Carga dos dados — leitura do CSV com pandas e inspeção de dimensões e tipos.
Diagnóstico de qualidade — colunas vazias, valores nulos, linhas duplicadas e a inconsistência conhecida da categoria ausente (#N/D).
Limpeza mínima — remoção de colunas vazias, tratamento da categoria ausente, remoção de duplicatas exatas e conversão da coluna DATA para datetime.
Validação do identificador de compra (CO_ID) — confirma que múltiplas linhas pertencem à mesma compra e calcula o número real de compras distintas.
Estatística descritiva da coluna CL_FHL (número de filhos do cliente): média, mediana, desvio padrão, moda, mínimo, máximo, contagem e quartis.
Agrupamentos — vendas por gênero, por categoria de produto, tabela dinâmica gênero × categoria, evolução mensal de vendas e média de filhos por segmento.
Conclusões — bloco final com os principais insights e problemas remanescentes na base.
Exportação — salva a base tratada em df_limpo.csv.
Como executar

VS Code:

bash
pip install pandas
python Miniprojeto_Varejo.py

(mantenha Base_Varejo.csv na mesma pasta do script)

Google Colab:

Faça upload de Base_Varejo.csv e Miniprojeto_Varejo.py (ou cole o conteúdo do script em células).
Rode todas as células.
Arquivos do repositório
Miniprojeto_Varejo.py — script principal da AED (comentado por blocos).
Base_Varejo.csv — base de dados original utilizada.
df_limpo.csv — base gerada pelo script após a limpeza.
README.md — este arquivo.
README_NomeDoAluno_Turma.md — instruções de execução para submissão (renomear com o nome do aluno).
Dataset

Base sugerida no Kaggle: Base Varejo
