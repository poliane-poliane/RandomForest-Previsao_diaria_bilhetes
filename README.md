# Previsão de Demanda de Bilhetes: Pipeline de ML

Este projeto tem como objetivo desenvolver um modelo preditivo para estimar o total diário de bilhetes vendidos. O foco é trabalhar com dados reais de rotas, preservando a distribuição original do histórico para garantir previsões que respeitem a realidade operacional, sem a criação de conexões artificiais.

##  Status do Projeto: Em Desenvolvimento
O projeto encontra-se em fase de construção do *pipeline* de dados e modelagem inicial. O código está versionado para acompanhamento e iteração contínua.

##  Pipeline e Abordagem Técnica
Para garantir a qualidade dos dados, o projeto adota as seguintes etapas:
* **Normalização de Dados:** Utilização da biblioteca `unidecode` para padronizar nomes de rotas (ex: remoção de acentos), evitando a criação de duplicidade de categorias.
* **Pré-processamento:** Aplicação de `LabelEncoder` para transformar variáveis categóricas em numéricas, adequando-as aos algoritmos de regressão.
* **Modelagem:** Estruturado com algoritmos baseados em árvores de decisão (`RandomForestRegressor`), escolhidos por sua robustez em lidar com dados tabulares complexos e relações não lineares.

##  O que está funcionando
* **Limpeza e Padronização:** O pipeline de tratamento de texto com `unidecode` está operante e eliminando ruídos nas categorias de rotas.
* **Estrutura de Dados:** A carga e o tratamento básico do *dataframe* via `pandas` estão estáveis.
* **Definição de Objetivo:** A lógica de preservação da distribuição histórica (não reponderação) está implementada no conceito do projeto.

##  Desafios e "O que ainda não deu certo"
Como o projeto está em andamento, alguns pontos críticos estão sob análise:
* **Data Leakage:** Identificamos riscos de vazamento de dados durante o treino. Estamos refinando o processo para garantir que o modelo não tenha acesso a informações futuras no momento da previsão.
* **Métricas de Erro:** Os valores de `mean_absolute_error` (MAE) ainda precisam ser calibrados, pois a distribuição de bilhetes por rota é muito assimétrica.
* **Ajuste de Hiperparâmetros:** O modelo atual utiliza configurações padrão; a tunagem fina (*tuning*) ainda será realizada para melhorar a precisão.

##  Próximos Passos
1. **Validação Cruzada:** Implementar *Cross-Validation* temporal para garantir que o modelo seja testado em períodos distintos dos usados no treino.
2. **Engenharia de Recursos (Feature Engineering):** Criar variáveis como "dia da semana", "feriados" e "sazonalidade", que devem aumentar significativamente o poder explicativo do modelo.
3. **Análise de Erros:** Realizar o *plot* dos resíduos para entender onde o modelo está errando sistematicamente.
4. **Deploy de Avaliação:** Gerar o gráfico de previsão vs. real para validar visualmente a aderência do modelo.

##  Observações Técnicas
* **Ambiente:** O projeto foi desenvolvido em ambiente Jupyter Notebook (Google Colab).
* **Bibliotecas Principais:** `pandas`, `numpy`, `unidecode`, `scikit-learn`.

---
*Documentação em constante atualização conforme o progresso do pipeline de Machine Learning.*
