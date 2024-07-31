# 📊 Previsão de Estoque Inteligente na AWS com [SageMaker Canvas](https://aws.amazon.com/pt/sagemaker/canvas/)

Bem-vindo ao desafio de projeto "Previsão de Estoque Inteligente na AWS com SageMaker Canvas. Neste Lab DIO, você aprenderá a usar o SageMaker Canvas para criar previsões de estoque baseadas em Machine Learning (ML). Siga os passos abaixo para completar o desafio!

## 📋 Pré-requisitos

Antes de começar, certifique-se de ter uma conta na AWS. Se precisar de ajuda para criar sua conta, confira nosso repositório [AWS Cloud Quickstart](https://github.com/digitalinnovationone/aws-cloud-quickstart).


## 🎯 Objetivos Deste Desafio de Projeto (Lab)

![image](https://github.com/digitalinnovationone/lab-aws-sagemaker-canvas-estoque/assets/730492/72f5c21f-5562-491e-aa42-2885a3184650)

- Dê um fork neste projeto e reescreva este `README.md`. Sinta-se à vontade para detalhar todo o processo de criação do seu Modelo de ML para uma "Previsão de Estoque Inteligente".
- Para isso, siga o [passo a passo] descrito a seguir e evolua as suas habilidades em ML no-code com o Amazon SageMaker Canvas.
- Ao concluir, envie a URL do seu repositório com a solução na plataforma da DIO.


## 🚀 Passo a Passo

### 1. Selecionar Dataset

Dataset : `canvas-sample-retail-electronics-forecasting`, para a prática do SageMaker. 

- item_id: Identificador único de produtos.
- location: Localização das vendas.
- time_stamp: Data e hora.
- demand: Demanda.
- price: Preço de venda.
- product_category: Categoria.

### 2. Construir/Treinar

 Configuração das variáveis de entrada e saída de acordo com os dados e inicio do treinamento do modelo.

- Variável-alvo: `price` (para previsão de preço).
- Timestamp: Data e hora dos registros.
- Identificador único: `item_id`.
- Agrupador: `location`.

 Modelo treinado em modo Standart.

### 3. Analisar

Métricas de Desempenho do Modelo

- **Média da Precisão em Quantis Ponderados (Avg. wQL):** Reflete a precisão do modelo em diferentes quantis ponderados (P10, P50, P90). Um valor de `0.017` demonstra uma alta precisão.
- **Erro Percentual Médio Absoluto (MAPE):** Mede o erro percentual médio das previsões. Com um valor de `0.012` (1.2% de erro médio), indica previsões muito próximas dos valores reais.
- **Erro Absoluto Ponderado (WAPE):** Avalia o erro absoluto ajustado por ponderação. Um valor de `0.013` (1.3% de erro absoluto) sugere um desempenho muito eficaz.
- **Raiz Quadrada do Erro Médio Quadrático (RMSE):** Calcula a raiz quadrada da média dos erros quadráticos. Um valor de `2.278` aponta para uma baixa média de erros quadráticos, indicando previsões precisas.
- **Erro Absoluto Escalado (MASE):** Mede o erro absoluto relativo à série temporal. Um valor de `0.000` denota uma precisão excepcional do modelo.

### 4. Previsões

Devido ao grande número de SKUs, a previsão em `batch` não é viável no plano gratuito. Por isso, as  previsões realizadas foram individuais, com intervalos de P10 (cenário pessimista), P90 (cenário otimista) e P50 (cenário neutro). As estimativas de lucro ou prejuízo podem ser calculadas para o período de três meses a partir do último dado disponível.
