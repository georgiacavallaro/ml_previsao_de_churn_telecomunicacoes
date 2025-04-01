# Projeto de *Machine Learning* para Previsão de Churn - Telecomunicações (*Interconnect*)

Autora: Georgia A. Cavallaro <br>
Data: 06/03/2025

## Descrição do projeto

Este projeto é uma tarefa de *Machine Learning* da empresa *Interconnect*, uma empresa de telecomunicações fictícia. Ele foi desenvolvido como a entrega final do curso de Cientista de Dados da [Tripleten](https://tripleten.com/pt-bra/data-scientist/meet) e tem como objetivo demonstrar na prática os conhecimentos adquiridos durante o curso.

**Tabela de conteúdo:**
- [Objetivo](#objetivo-)
- [Resultados](#resultados-)
- [Ferramentas Utilizadas](#ferramentas-utilizadas-)
- [Metodologia](#metodologia-)
- [Como executar o projeto](#como-executar-o-projeto-)
- [Aprendizados](#aprendizados-)
- [Contato](#contato-)

## Objetivo 🏔

Desenvolver um modelo de Machine Learning visando identificar clientes propensos ao cancelamento e oferecer incentivos para retenção.

- <mark>**Métrica principal:** AUC-ROC > 0.75</mark>
- **Métrica adicional:** Acurácia

**Serviços oferecidos pela empresa:**

- **Principais:** Telefonia fixa e Internet *(DSL ou fibra óptica).*
- **Secundários:** Segurança na Internet, suporte técnico, armazenamento na nuvem e streamings *(TV e filmes).*

## Resultados 🏁

### 🎯 O objetivo do projeto foi alcançado:

O modelo *CatBoost Classifier* apresentou o melhor desempenho, alcançando um **AUC-ROC de 0.87** no conjunto de treino e de **0.89** no conjunto de teste.

Além disso, **desenvolvi uma Pipeline** para automatizar o processo de tratamento, treinamento e predição de novos dados. A pipeline consiste em:

- Função para carregar e unir os dados;
- Função para tratamento inicial dos dados;
- Função para criação do pipeline de Machine Learning;
- Função para realizar novos treinamentos do modelo;
- Função para fazer predições a partir de dados em .csv.
  
Essa estrutura garante a reprodutibilidade e a escalabilidade do processo, tornando a aplicação do modelo em novos dados mais eficiente.

### 💡 Insights Relevantes:

O cancelamento de clientes (*"Churn"*) está fortemente relacionado a fatores como:

- **Tempo de contrato:** contratos mais recentes têm maior taxa de cancelamento;
- **Tempo de renovação do contrato:** contratos com períodos de renovação mais curtos (como o *Mensal*), têm maior taxa de cancelamento;
- Contratos com **cobranças eletrônicas porém *não automáticas*** também são mais propensos ao cancelamento;
- Dos contratos com serviço de internet os de **Fibra Ótica** são os mais cancelados.

## Ferramentas Utilizadas 🧰

<p align="center">
  <a href="https://skillicons.dev">
    <img src="https://go-skill-icons.vercel.app/api/icons?i=cuda,jupyter,numpy,pandas,python,scikitlearn,seaborn,vscode&theme=light&perline=10" />
  </a>
</p>

- **Caderno de desenvolvimento:** *Jupyter Notebook*;
- **Linguagem de programação:** *Python*;
- **Biblioteca para exploração de arquivos:** *Zipfile*;
- **Bibliotecas para manipulação e análise dos dados:** *Pandas • Numpy • Itertools*;
- **Bibliotecas para geração dos gráficos:** *Matplotlib Pyplot • Seaborn*;
- **Bibliotecas para contrução de modelos de *machine learning*:** *Sklearn • CatBoost*;
- **Bibliotecas para monitoramento de tempo de execução:** *Timeit • Tqdm*;
- **Aceleração do processo de treinamento em GPU:** CUDA;
- **Software de edição de código:** *VsCode*.

## Metodologia 🔍

**1. Coleta e Preparação dos Dados**

- Leitura e unificação dos dados provenientes de arquivos *.csv*, garantindo a integridade e consistência das informações.

  **Pré-processamento dos dados:**
  - *Tratamento de valores ausentes:* preenchimento ou remoção de dados inconsistentes;
  - *Normalização e padronização:* aplicação de técnicas para garantir que os dados estejam em uma escala apropriada para os modelos com *Robust Scaler*;
  - *Conversão de variáveis:* transformação de colunas categóricas em variáveis numéricas para compatibilidade com os modelos com *One-Hot Encoder e Ordinal Encoder*.

**2. Engenharia de Features**

- Exclusão de variáeis de baixa relevância aparente;
- Exploração e criação de novas variáveis a partir das informações disponíveis, entre elas:
  
  - **Início de contrato:** variável derivada para capturar o impacto da duração do serviço na retenção de clientes.

**3. Desenvolvimento e Treinamento dos Modelos**

- Divisão dos dados na proporção **3:1** *(conjunto de treino (80%) e conjunto de teste (20%))*;
- Treinamento de três algoritmos de Machine Learning supervisionado a procura da melhor *performance* utilizando *Validação Cruzada* para garantir robustez nos resultados:

  - *CatBoost Classifier*;
  - *Random Forest Classifier*;
  - *K Neighbors Classifier*.

- Avaliação do desempenho dos modelos pela métrica **AUC-ROC**.

**4. Análise dos Resultados e Melhorias**

- Análise do desempenho dos modelos em relação a *tempo de predição* e *métrica AUC-ROC*;
- Novos treinamentos e busca de melhorias e seleção do melhor *modelo* e *pré-tratamento* dos dados.

**5. Construção da Pipeline**

- Desenvolvimento de *Pipeline automatizada em funções* para garantir reprodutibilidade e escalabilidade.

  **Etapas essenciais da pipeline:**
  - Carregamento e unificação dos dados;
  - Pré-processamento e tratamento dos dados;
  - Criação e treinamento do modelo;
  - Novas predições com dados externos.

## Como executar o projeto 💽

Este projeto foi desenvolvido em **Python** utilizando *Jupyter Notebook* você consegue visualizá-lo rapidamente [aqui](https://github.com/georgiacavallaro/ml_previsao_de_churn_telecomunicacoes/blob/main/projeto17_GeorgiaCavallaro_git.ipynb). Para executar o projeto, siga os passos abaixo:

**1. Pré-requisitos:**
  - Certifique-se de ter instalado:
    - *Python 3.12*;
    - *Jupyter Notebook*.
  - Instale as bibliotecas necessárias (indicadas em `requirements.txt`):
    
    ```sh
    pip install -r requirements.txt

**2. Clone o repositório:**

    git clone https://github.com/georgiacavallaro/ml_previsao_de_churn_telecomunicacoes.git
    cd ml_previsao_de_churn_telecomunicacoes

**3. Abra o Jupyter Notebook:**
    
    jupyter notebook

  - Abra o arquivo `.ipynb` e execute as células na ordem indicada.
  
**Para executar o pipeline a fazer predições:**

  - Siga os passos dentro do notebook para:
  1. Carregar os dados;
  2. Pré-processar e tratar as informações;
  3. Treinar o modelo;
  4. Fazer predições com novos dados *(substituindo o arquivo de entrada, se necessário)*.

## Aprendizados 📝

### Habilidades Técnicas:
- **Machine Learning:** Desenvolvimento, treinamento e avaliação de modelos preditivos para Churn (*cancelamentos*);
- **Modelos Supervisionados:** Experiência com *CatBoost, Random Forest* e *K Neighbors Classifier*;
- **Métricas de Avaliação:** Uso do *AUC-ROC* para comparar o desempenho dos modelos;
- **Feature Engineering:** Identificação de variáveis relevantes para prever o cancelamento de clientes;
- **Pipeline de Machine Learning:** *Automação* do processo de tratamento de dados, treinamento e predição;
- **Manipulação de Dados:** Leitura e processamento de arquivos *.csv* para alimentar modelos preditivos.

### Habilidades Analíticas:
- **Análise de Fatores de Churn:** *Identificação de padrões* como tempo de contrato, método de pagamento e tipo de serviço;
- **Geração de Insights Estratégicos:** Transformação de análises em *ações concretas* para retenção de clientes;
- **Interpretação de Modelos:** *Comparação entre* modelos para recomendar o mais eficiente para o negócio.

### Habilidades de Aplicabilidade:
- **Documentação de projetos:** Elaboração de *documentação* clara e detalhada para garantir que o projeto seja compreensível e replicável;
- **Tomada de Decisão Baseada em Dados:** *Aplicação do modelo* para campanhas de retenção e otimização de planos;
- **Escalabilidade:** Construção de uma estrutura *reprodutível* e *eficiente* para novos dados;
- **Impacto Empresarial:** Uso de *inteligência preditiva* para reduzir cancelamentos e aumentar a retenção.

## Contato 😄

Georgia Cavallaro <br>
[![Linkedin](https://i.stack.imgur.com/gVE0j.png) LinkedIn](https://www.linkedin.com/in/georgia-cavallaro/) ✉ georgia.alexa@outlook.com

Caso tenha dúvidas ou queira contribuir, fique à vontade para abrir uma issue no repositório! 🚀
