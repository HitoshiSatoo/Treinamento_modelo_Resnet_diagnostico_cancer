# Classificação de Câncer de Pulmão com a Arquitetura ResNet

Este repositório contém a implementação e os resultados do treinamento de uma Rede Neural Convolucional (CNN) baseada na arquitetura **ResNet18** para a classificação automatizada de imagens histopatológicas de tecido pulmonar em três classes: **adenocarcinoma**, **carcinoma de células escamosas** e **tecido saudável**.

O projeto faz parte de um estudo comparativo mais amplo, e esta documentação é focada especificamente nos processos, resultados e conclusões obtidos com o modelo ResNet, que apresentou o melhor desempenho.

## 1. Metodologia e Processos

### 1.1. Arquitetura do Modelo
Foi utilizada a arquitetura **ResNet18**, uma rede neural de 18 camadas conhecida por suas conexões residuais (*skip connections*). Essa estrutura permite um fluxo de gradiente mais eficaz, superando o problema de desaparecimento do gradiente e facilitando o treinamento de redes profundas. A técnica de **Transferência de Aprendizado (Transfer Learning)** foi aplicada, utilizando pesos pré-treinados para otimizar e acelerar o processo.

### 1.2. Conjunto de Dados e Pré-processamento
* **Dataset:** O projeto utilizou o dataset público **LC25000**, disponível no Kaggle, focado em imagens histopatológicas de pulmão.
* **Pré-processamento:** As imagens foram padronizadas para o formato de entrada da ResNet, com redimensionamento para `224x224` pixels e normalização dos valores dos pixels com as médias e desvios padrão do dataset ImageNet.

### 1.3. Ambiente e Ferramentas
* **Linguagem:** Python 3.11
* **Framework de Deep Learning:** PyTorch e Pytorch Lightning
* **Interpretabilidade:** Grad-CAM
* **Ambiente de Execução:** Google Colab e Kaggle Notebooks (com suporte de GPU).

## 2. Treinamento e Validação

### 2.1. Evolução do Treinamento
Durante o treinamento, o modelo ResNet18 demonstrou uma capacidade de aprendizado extremamente rápida e estável. Os gráficos de Acurácia e Perda por Época mostraram que a acurácia atingiu valores próximos de 1.0 já nas primeiras iterações, enquanto a perda apresentou uma redução acentuada, indicando uma convergência eficiente.

* **(Inserir aqui a imagem do gráfico "Acurácia por época (ResNet18)" - Figura 8 do seu TCC)**
* **(Inserir aqui a imagem do gráfico "Perda por época (ResNet18)" - Figura 9 do seu TCC)**

### 2.2. Resultados no Conjunto de Validação
No conjunto de validação, o modelo obteve um **desempenho perfeito**, classificando corretamente 100% das imagens das três classes sem nenhum erro. As métricas de acurácia, sensibilidade, precisão e F1-score (macro) atingiram o valor de **1.000**.

### 2.3. Resultados no Conjunto de Teste (Performance Final)
A robustez e a capacidade de generalização do modelo foram confirmadas no conjunto de teste. Mesmo com dados nunca vistos, o desempenho permaneceu excepcionalmente alto.
* **Acurácia Final:** **99,60%**
* **Métricas Adicionais:** O F1-score, precision e recall (média macro) também alcançaram **0.9960**, demonstrando a alta capacidade do modelo em generalizar seu aprendizado.

* **(Inserir aqui a imagem da "Matriz de Confusão no conjunto de teste (ResNet18)" - Figura 12 do seu TCC)**

### 2.4. Análise de Interpretabilidade com Grad-CAM
Para garantir a transparência e a confiabilidade do modelo, a técnica **Grad-CAM** foi aplicada para gerar mapas de calor. As visualizações demonstraram um foco mais preciso do modelo ResNet18 em comparação a outras arquiteturas, destacando as regiões relevantes para a detecção de anomalias, mesmo em padrões sutis.

* **(Inserir aqui a imagem da "Visualização Grad-CAM (ResNet18)" - Figura 14 do seu TCC)**

## 3. Conclusão

A arquitetura **ResNet18** se mostrou mais robusta e eficaz para a tarefa de diagnóstico automatizado, alcançando uma acurácia de **99,60%**. A superioridade pode ser atribuída às suas conexões residuais, que permitem uma aprendizagem mais estável.

A combinação da alta performance quantitativa com a interpretabilidade visual fornecida pelo Grad-CAM consolida a ResNet18 como uma ferramenta de grande potencial para aplicações clínicas, servindo como um sistema de apoio à decisão confiável para diagnósticos de câncer de pulmão.

## Como Utilizar este Projeto

1.  **Clone o repositório:**
    ```bash
    git clone [URL_DO_SEU_REPOSITORIO_AQUI]
    ```
2.  **Instale as dependências:**
    ```bash
    pip install -r requirements.txt
    ```
3.  **Estrutura de Dados:**
    * Baixe o dataset LC25000 do Kaggle.
    * Organize as imagens nas pastas `train`, `val` e `test`, com as subpastas para cada classe (`lung_aca`, `lung_n`, `lung_scc`).
4.  **Execute os notebooks:**
    * Siga os notebooks focados no modelo ResNet para realizar o pré-processamento, treinamento e avaliação.
