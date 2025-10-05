# Classificação de Câncer de Pulmão com a Arquitetura ResNet

Este repositório contém a implementação e os resultados do treinamento de uma Rede Neural Convolucional (CNN) baseada na arquitetura **ResNet18** para a classificação automatizada de imagens histopatológicas de tecido pulmonar em três classes: **adenocarcinoma**, **carcinoma de células escamosas** e **tecido saudável**.

O projeto faz parte de um estudo comparativo mais amplo, e esta documentação é focada especificamente nos processos, resultados e conclusões obtidos com o modelo ResNet.

## 1. Metodologia e Processos

### 1.1. Arquitetura do Modelo
[cite_start]Foi utilizada a arquitetura **ResNet18**, uma rede neural de 18 camadas conhecida por suas conexões residuais (*skip connections*)[cite: 695, 696]. [cite_start]Essa estrutura permite um fluxo de gradiente mais eficaz, superando o problema de desaparecimento do gradiente e facilitando o treinamento de redes profundas[cite: 696, 697]. [cite_start]A técnica de **Transferência de Aprendizado (Transfer Learning)** foi aplicada, utilizando pesos pré-treinados para otimizar e acelerar o processo[cite: 324].

### 1.2. Conjunto de Dados e Pré-processamento
* [cite_start]**Dataset:** O projeto utilizou o dataset público **LC25000**, disponível no Kaggle, focado em imagens histopatológicas de pulmão[cite: 665].
* [cite_start]**Pré-processamento:** As imagens foram padronizadas para o formato de entrada da ResNet, com redimensionamento para `224x224` pixels e normalização dos valores dos pixels com as médias e desvios padrão do dataset ImageNet[cite: 676, 677, 678].

### 1.3. Ambiente e Ferramentas
* [cite_start]**Linguagem:** Python 3.11 [cite: 662]
* [cite_start]**Framework de Deep Learning:** PyTorch e Pytorch Lightning [cite: 667]
* [cite_start]**Interpretabilidade:** Grad-CAM [cite: 667]
* [cite_start]**Ambiente de Execução:** Google Colab e Kaggle Notebooks (com suporte de GPU)[cite: 660].

## 2. Treinamento e Validação

### 2.1. Evolução do Treinamento
Durante o treinamento, o modelo ResNet18 demonstrou uma rápida capacidade de aprendizado. [cite_start]Os gráficos de Acurácia e Perda por Época mostraram que a acurácia atingiu valores elevados rapidamente, estabilizando-se próximo de 1.0, enquanto a perda apresentou uma redução acentuada nas primeiras épocas, indicando uma convergência estável e eficiente[cite: 716, 717, 718].

* **(Inserir aqui a imagem do gráfico "Acurácia por época (ResNet18)" - Figura 8 do seu TCC)**
* **(Inserir aqui a imagem do gráfico "Perda por época (ResNet18)" - Figura 9 do seu TCC)**

### 2.2. Resultados no Conjunto de Validação
[cite_start]No conjunto de validação, o modelo obteve um desempenho perfeito, classificando corretamente todas as imagens das três classes sem nenhum erro[cite: 721]. [cite_start]As métricas de acurácia, sensibilidade, precisão e F1-score (macro) atingiram o valor de **1.000**, indicando um desempenho ideal[cite: 723].

### 2.3. Resultados no Conjunto de Teste (Performance Final)
A robustez e a capacidade de generalização do modelo foram confirmadas no conjunto de teste, com dados nunca antes vistos.
* [cite_start]**Acurácia Final:** **99,60%** [cite: 827, 837]
* [cite_start]**Métricas Adicionais:** O F1-score, precision e recall (média macro) também alcançaram **0.9960**[cite: 838, 839], demonstrando a alta capacidade do modelo em generalizar o aprendizado.

* **(Inserir aqui a imagem da "Matriz de Confusão no conjunto de teste (ResNet18)" - Figura 12 do seu TCC)**

### 2.4. Análise de Interpretabilidade com Grad-CAM
[cite_start]Para garantir a transparência e a confiabilidade do modelo, a técnica **Grad-CAM** foi aplicada para gerar mapas de calor[cite: 830]. [cite_start]As visualizações demonstraram um foco preciso do modelo ResNet18, destacando as regiões relevantes nas imagens para a detecção de anomalias, mesmo em padrões sutis, e aumentando a confiança na decisão algorítmica[cite: 1004].

* **(Inserir aqui a imagem da "Visualização Grad-CAM (ResNet18)" - Figura 14 do seu TCC)**

## 3. Conclusão

[cite_start]A arquitetura **ResNet18** se mostrou mais robusta e eficaz para a tarefa de diagnóstico automatizado em comparação com a VGG19, alcançando uma acurácia de **99,60%**[cite: 1010]. [cite_start]A superioridade pode ser atribuída às suas conexões residuais, que permitem uma aprendizagem mais estável[cite: 1001, 1011].

[cite_start]A combinação da alta performance quantitativa com a interpretabilidade visual fornecida pelo Grad-CAM consolida a ResNet18 como uma ferramenta de grande potencial para aplicações clínicas, servindo como um sistema de apoio à decisão confiável para diagnósticos de câncer de pulmão[cite: 1014].

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
