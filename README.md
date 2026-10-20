# Melhores Compras | Análise de Vendas

**Exploração de vendas semanais, comparação de modelos de regressão e apresentação em Power BI.**

Projeto acadêmico desenvolvido pelo **Grupo 68**, em 2024, no PBL da fase 7 do 2º ano. A entrega combina análise exploratória em Python, experimentos de machine learning e comunicação visual dos resultados.

[Notebook](notebooks/modelagem_vendas.ipynb) · [Power BI](powerbi/dashboard_vendas.pbix) · [Relatório](reports/relatorio_grupo68.pdf) · [Guia técnico](docs/execucao.md)

## Problema de negócio

Como explorar o comportamento das vendas semanais e comparar estimativas a partir das variáveis disponíveis?

O estudo investiga o histórico de vendas, feriados e indicadores econômicos, utilizando gráficos e modelos de regressão para apoiar a interpretação dos dados.

## Entregas

| Frente | Conteúdo |
| --- | --- |
| Preparação dos dados | Conversão de datas, ajustes de escala e verificação de duplicidades e valores ausentes. |
| Análise exploratória | Evolução semanal, gráficos de dispersão e correlações. |
| Engenharia de atributos | Construção da variável de semana do ano. |
| Modelagem | Comparação entre Regressão Linear, SVR, Random Forest e XGBoost. |
| Avaliação dos experimentos | Métricas de regressão e validação cruzada registradas no notebook. |
| Comunicação | Relatório acadêmico e dashboard com as páginas Home, Visão Geral e Insights. |

## Visualizações

### Evolução das vendas semanais

![Histórico de vendas semanais com linha de tendência](assets/vendas_semanais.png)

### Comparação dos modelos

![Comparação exploratória dos modelos por MAE e R²](assets/comparacao_modelos.png)

Visualizações extraídas das saídas registradas no notebook acadêmico.

## Competências demonstradas

- Preparação e exploração de dados com pandas e NumPy.
- Visualização com Matplotlib e Seaborn.
- Construção e comparação de modelos de regressão.
- Leitura de métricas e discussão de metodologia.
- Apresentação de análises em Power BI e relatório técnico.

## Tecnologias

Python · pandas · NumPy · Matplotlib · Seaborn · scikit-learn · XGBoost · Power BI

## Explorar o projeto

O [notebook](notebooks/modelagem_vendas.ipynb) pode ser consultado no GitHub com gráficos e saídas salvas. Para reexecutá-lo, é necessária a base original `sales.csv`. O [guia técnico](docs/execucao.md) descreve o ambiente e a estrutura esperada dos dados.

O [dashboard](powerbi/dashboard_vendas.pbix) está disponível para abertura no Power BI Desktop. Os critérios de interpretação dos experimentos estão nas [notas metodológicas](docs/notas_metodologicas.md).

## Contexto e autoria

Trabalho acadêmico do **Grupo 68**, publicado no portfólio de Gabriel de Assis. Notebook, relatório e dashboard preservam a entrega original. A análise tem caráter exploratório; os experimentos e seus resultados devem ser interpretados no contexto documentado.
