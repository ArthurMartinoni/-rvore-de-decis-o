# Classificação de Cogumelos com Árvore de Decisão - Mushroom (UCI)

## Descrição

Classificação de cogumelos como comestíveis ou venenosos usando árvore de decisão, com comparação entre uma árvore sem limite de profundidade e uma árvore podada. Projeto individual desenvolvido em Python, baseado no tutorial [Decision Tree Classification in Python (DataCamp)](https://www.datacamp.com/pt/tutorial/decision-tree-classification-python) e adaptado para o dataset Mushroom.

## Fonte dos dados

[Mushroom (UCI Machine Learning Repository)](https://doi.org/10.24432/C5959T) - 8.124 amostras de cogumelos descritas por 22 características físicas categóricas (formato do chapéu, odor, cor das lamelas, etc.), classificadas como comestíveis (`e`) ou venenosas (`p`). Os dados são carregados diretamente pela biblioteca `ucimlrepo`.

## Ferramentas utilizadas

- Python
- Pandas
- Scikit-learn
- Matplotlib
- ucimlrepo

## Etapas do projeto

1. Coleta de dados - carregamento do dataset via `ucimlrepo` e leitura dos metadados.
2. Tratamento de dados - identificação de valores faltantes na coluna `stalk-root`, tratados como uma categoria própria (`'missing'`).
3. Codificação - aplicação de One-Hot Encoding (`pd.get_dummies`), já que o scikit-learn só aceita entradas numéricas e todas as features são categóricas.
4. Divisão dos dados - 70% para treino e 30% para teste.
5. Árvore completa - treino de uma árvore sem limite de profundidade e avaliação da acurácia.
6. Pré-poda - treino de uma árvore com `max_depth=3` e `criterion="entropy"`, para obter um modelo menor e mais interpretável.
7. Visualização - gráficos das duas árvores com `plot_tree`.

## Principais achados

- A árvore completa atingiu acurácia de 1.0 no teste: o dataset é praticamente separável por regras simples.
- A variável `odor` é a raiz da árvore completa, o que mostra que o odor é o principal separador entre cogumelos comestíveis e venenosos.
- A única coluna com valores faltantes é `stalk-root`.
- A árvore podada (`max_depth=3`, `entropy`) atingiu acurácia de 0.9619, perdendo cerca de 4 pontos em troca de um modelo que cabe em uma única imagem e é fácil de interpretar.

## Como executar

1. Clone este repositório.
2. Instale as dependências: `pip install pandas scikit-learn matplotlib ucimlrepo`
3. Abra o notebook `arvore_decisao.ipynb` no VS Code e execute as células em ordem (o dataset é baixado automaticamente, não precisa de arquivo local).

## Autor

Arthur Martinoni [LinkedIn](https://linkedin.com/in/ArthurMartinoni) | [GitHub](https://github.com/ArthurMartinoni)
