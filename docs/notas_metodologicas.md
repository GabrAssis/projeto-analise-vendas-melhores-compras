# Notas metodológicas

Estas notas acompanham a publicação do material acadêmico original. Não alteram os arquivos de análise nem representam uma nova validação experimental.

## O que foi possível verificar

- O notebook tem 34 células, com código, comentários e saídas salvas.
- As saídas registram 143 observações e sete colunas na base de entrada.
- O treino efetivo usa `Holiday_Flag`, `Unemployment` e `WeekOfTheYear`. As variáveis `CPI`, `Temperature` e `Fuel_Price` são removidas na construção de `train_x`.
- O PBIX contém três páginas de relatório: Home, Visão Geral e Insights.
- Os três anexos originais foram mantidos sem alteração de conteúdo.

Não houve reexecução dos modelos nem validação funcional do dashboard. O arquivo `sales.csv` não foi fornecido.

## Divisão temporal

O notebook usa `train_test_split` com embaralhamento padrão e validação com `KFold(shuffle=True)`. Para estimar desempenho em previsão de semanas futuras, o próximo experimento deve separar os dados por data e usar validação temporal.

O gráfico de reais versus preditos segue a ordem do conjunto de teste aleatório, não uma sequência cronológica de semanas.

## Padronização e unidade dos erros

O `StandardScaler` é ajustado na base completa antes da divisão em treino e teste, incluindo a variável alvo. Isso permite que informações do conjunto de teste participem do pré-processamento.

Em uma revisão, o ajuste dos transformadores deve usar somente o treino. Como o alvo está padronizado, RMSE e MAE registrados não estão em reais, dólares ou na escala original das vendas. O MAPE também não deve ser interpretado como percentual de erro sobre as vendas originais, pois foi calculado com o alvo padronizado.

## Valores 39,60 e 50,35

As células identificadas pelos textos “Modelo Com Hiperparãmetros” e “Modelo Sem Hiperparãmetros” calculam:

```python
100 * cross_val_score(modelo, train_x, train_y).mean()
```

Para esses estimadores de regressão, sem um `scoring` explícito, a pontuação é R². Assim, os valores salvos de aproximadamente **39,60** e **50,35** correspondem ao **R² médio multiplicado por 100**, e não ao RMSE.

O relatório original interpreta esses números como RMSE e cita aproximadamente 50,55 no segundo caso. Essa interpretação não corresponde ao código nem à saída salva.

O modelo configurado melhora o R² do teste salvo (de cerca de 0,66 para 0,72), mas sua pontuação média de validação cruzada nessa comparação é menor (de cerca de 0,50 para 0,40). Portanto, não se deve afirmar uma melhora geral de desempenho com base apenas no teste.

## Divergências no relatório

O relatório contém números diferentes para alguns modelos e mistura descrições de famílias de algoritmos. XGBoost e Random Forest não são regressões lineares, e SVR não é um método de boosting.

O README usa os resultados salvos no notebook para apresentar os modelos e aponta suas limitações. O PDF foi preservado como registro da entrega acadêmica.

## Dados e dashboard

A unidade das variáveis econômicas e a fonte original precisam ser confirmadas antes de novos experimentos. As referências do relatório a moeda e inflação não foram validadas com um dicionário de dados externo.

O PBIX inclui um modelo de dados incorporado. Sua estrutura foi inspecionada, mas consultas, medidas, credenciais e a atualização de fontes não foram integralmente validadas no Power BI Desktop.
