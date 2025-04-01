# Projeto de *Machine Learning* para Previsão de Churn - Telecomunicações (*Interconnect*)

Autora: Georgia A. Cavallaro
Data: 06/03/2025

## Descrição do projeto

Este projeto é uma tarefa de *Machine Learning* da empresa Interconnect, uma empresa de telecomunicações fictícia. Ele foi desenvolvido como a entrega final do curso de Cientista de Dados da Tripleten e tem como objetivo demonstrar na prática os conhecimentos adquiridos durante o curso.

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
    <img src="https://go-skill-icons.vercel.app/api/icons?i=jupyter,numpy,pandas,python,scikitlearn,seaborn,vscode&theme=light&perline=10" />
  </a>
</p>

- **Caderno de desenvolvimento:** *Jupyter Notebook*;
- **Linguagem de programação:** *Python*;
- **Biblioteca para exploração de arquivos:** *Zipfile*;
- **Bibliotecas para manipulação e análise dos dados:** *Pandas • Numpy • Itertools*;
- **Bibliotecas para geração dos gráficos:** *Matplotlib Pyplot • Seaborn*;
- **Bibliotecas para contrução de modelos de *machine learning*:** *Sklearn • CatBoost*;
- **Bibliotecas para monitoramento de tempo de execução:** *Timeit • Tqdm*;
- **Software de edição de código:** *VsCode*.
