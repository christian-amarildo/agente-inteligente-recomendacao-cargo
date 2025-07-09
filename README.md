
---

# Agente Inteligente para Recomendação de Cargo na Área de Dados com Machine Learning e n8n

## **Objetivo**
Este projeto tem como objetivo desenvolver um **agente inteligente** que sugere o cargo ideal na área de dados com base no perfil do usuário, utilizando **aprendizado de máquina (ML)** e **n8n** para automação de fluxos. O agente será capaz de processar dados recebidos via **Webhook**, **Google Forms** ou **Telegram Bot**, pré-processar os dados, aplicar um modelo de ML treinado, e retornar a recomendação do cargo ao usuário.

## **Integrantes do Grupo**
- **Christian Amarildo**
- **Daniel Naiff**
- **Rogério Barbosa**
- **DeLoreto Melo**

## **Estrutura do Projeto**
O projeto está organizado da seguinte forma:

```
/src
/model
\- treinamento\_modelo.py       # Código de treinamento do modelo de ML
\- avaliacao\_modelo.py          # Avaliação do modelo treinado
/n8n
\- fluxo\_n8n.json               # Arquivo exportado com o fluxo do n8n
/docs
\- fluxograma\_shc.png           # Fluxograma do Stochastic Hill Climbing
\- fluxograma\_ag.png            # Fluxograma do Algoritmo Genético
/data
\- dataset.csv                  # Dataset de entrada (State of Data Brazil 2022)
/notebooks
\- analise\_exploratoria.ipynb   # Jupyter Notebook com análise exploratória e pré-processamento
\- treinamento.ipynb            # Jupyter Notebook com treinamento de modelos e avaliação
/results
\- resultados\_modelo.csv        # Resultados das avaliações dos modelos

````

---

## **Descrição do Dataset: State of Data Brazil 2022**
A base de dados é proveniente do estudo **State of Data Brazil 2022**, conduzido pela Data Hackers e Bain & Company. O dataset contém informações de mais de 4200 respondentes sobre perfil demográfico, formação acadêmica, ferramentas utilizadas e cargos na área de dados.

### **Atributos do Dataset**:
1. **idade**: Idade do respondente (Inteiro)
2. **genero**: Gênero do respondente (String)
3. **etnia**: Etnia do respondente (String)
4. **pcd**: Pessoa com Deficiência? (String)
5. **vive_no_brasil**: O respondente mora no Brasil? (Booleano)
6. **estado_moradia**: Estado onde o respondente mora no Brasil (String)
7. **nivel_ensino**: Nível de instrução do respondente (String)
8. **formacao**: Formação acadêmica do respondente (String)
9. **tempo_experiencia_dados**: Tempo de experiência na área de dados (String)
10. **linguagens_preferidas**: Linguagens de programação preferidas do respondente (String)
11. **bancos_de_dados_preferidos**: Bancos de dados preferidos (String)
12. **cloud_preferida**: Ferramentas de cloud computing preferidas (String)
13. **cargo**: Cargo atual do respondente (String)

Você pode baixar o dataset completo em: [Link para download](https://bit.ly/facomp-sods).

---

## **Etapas do Projeto**
As etapas a serem seguidas no desenvolvimento do agente inteligente são:

### **1. Seleção e Análise Exploratória**
- Justificação da escolha dos atributos.
- Análise exploratória com visualizações (distribuições, correlações, valores ausentes e outliers).
- Ferramentas: **pandas**, **matplotlib**, **seaborn**.

### **2. Pré-processamento e Enriquecimento**
- Tratamento de dados ausentes, inconsistentes ou ruidosos.
- Criação de atributos derivados (como converter tempo de experiência em anos).
- Codificação de variáveis categóricas usando **OneHotEncoder** ou **LabelEncoder**.
- Normalização dos dados com **MinMaxScaler** ou **StandardScaler**.
- Ferramentas: **pandas**, **scikit-learn**.

### **3. Formatação e Divisão de Dados**
- Divisão estratificada dos dados em 70% treino e 30% teste, mantendo a proporção das classes de cargo.
- Ferramenta: **train_test_split** do **scikit-learn**.

### **4. Mineração de Dados (Machine Learning)**
- Escolha de dois modelos: **Regressão Logística**, **Árvore de Decisão**, **Floresta Aleatória**, **SVM**, **Rede Neural**.
- Treinamento e avaliação dos modelos com **Acurácia**, **Precisão**, **Recall** e **Matriz de Confusão**.
- Justificação dos hiperparâmetros escolhidos.
- Ferramentas: **scikit-learn**, **keras** (se utilizar redes neurais).

### **5. Construção do Agente Inteligente no n8n**
- Automação do fluxo de entrada de dados, pré-processamento, classificação e retorno de recomendação ao usuário.
- O agente deve receber dados via **Webhook**, **Google Forms** ou **Telegram Bot**, processar e classificar os dados com o modelo treinado, e retornar a recomendação.
- Ferramentas: **n8n** (para automação), **Telegram Bot API** (opcional para interação com o usuário).

### **6. Documentação da Solução**
- O notebook Jupyter deve conter explicações detalhadas sobre as decisões tomadas em cada etapa.
- O código do modelo e as visualizações geradas durante a análise exploratória e avaliação dos modelos.
- Capturas de tela do fluxo no **n8n** em funcionamento.
- Link para teste (se aplicável).
- Arquivo `.json` exportado do fluxo no **n8n**.

---

## **Ferramentas e Tecnologias Utilizadas**

1. **GitHub**:
   - Para versionamento de código e colaboração.
   - **Branches** para cada membro da equipe, realizando **Pull Requests** para revisão.

2. **Docker** (opcional):
   - Para garantir que todos os membros da equipe utilizem o mesmo ambiente de desenvolvimento.

3. **Máquina Virtual Ubuntu**:
   - Instalação de ferramentas necessárias para o desenvolvimento, como **Python**, **Jupyter Notebooks**, e **n8n**.
  
4. **n8n**:
   - Para automação dos fluxos de entrada de dados, pré-processamento, e recomendação.
  
5. **Google Colab** (alternativo para Jupyter):
   - Caso algum membro prefira usar o **Google Colab**, o notebook será compartilhado como link público.

6. **Python**:
   - Para todas as tarefas de processamento de dados, treinamento de modelos e pré-processamento.

7. **Bibliotecas**:
   - **pandas**, **scikit-learn**, **matplotlib**, **seaborn**, **n8n**.

---

## **Organização das Tarefas por Integrante**

### **Christian Amarildo**:
- **Responsável por**:
  
### **Daniel Naiff**:
- **Responsável por**: 
  
### **Rogério Barbosa**:
- **Responsável por**: 

### **DeLoreto Melo**:
- **Responsável por**: 

---

## **Como Rodar o Projeto**

1. **Clonar o Repositório**:
   Clone o repositório com o comando:
   ```bash
   git clone https://github.com/seu-usuario/seu-repositorio.git

2. **Configuração do Ambiente**:
   Se estiver usando **Docker**, rode o contêiner para garantir o mesmo ambiente de desenvolvimento.
   Caso contrário, instale as dependências no Ubuntu ou Google Colab:

   ```bash
   pip install -r requirements.txt
   ```

3. **Executar o Notebook**:

   * Execute o Jupyter Notebook em sua máquina local ou use **Google Colab** com o link público fornecido.

4. **Fluxo no n8n**:

   * Importe o arquivo `.json` do fluxo n8n para o seu ambiente de n8n.

---

## **Link para o Teste (se aplicável)**

Se você utilizou **Google Colab** ou hospedou o modelo em **Hugging Face** ou **Replit**, insira o link aqui.

---

### **Prazo de Entrega:**

Até **27/08/2025**, às **23:59h**, via **SIGAA**.

---
