# Análise de Machine Learning - Validação Final e Preparação para Produção 🎶

Este repositório contém a resolução do 7º e último desafio do projeto **#7DaysOfCode - Machine Learning**. O foco principal foi validar o desempenho do modelo treinado em dados de teste nunca vistos e preparar o modelo para uso em produção através da serialização e documentação do pipeline de pré-processamento.

---

## 📌 Sobre o Projeto

O projeto contempla as seguintes etapas principais:

- ✅ **Análise exploratória** realizada no desafio 1, incluindo gráficos sobre distribuição de popularidade e correlações;
- ✅ **Criação da variável alvo** `popular_binaria` com **critério próprio e personalizado**, divergindo da proposta original da Alura;
- ✅ **Feature Engineering personalizada**, incluindo:
    - Criação da variável `artistas_relevantes` com base nos 5000 artistas mais populares;
    - Aplicação de **OneHotEncoding** na variável `track_genre` com 113 categorias;
- ✅ **Divisão dos dados** em treino, validação (com validação cruzada) e teste (20% dos dados reservados exclusivamente para teste final);
- ✅ **Balanceamento das classes** utilizando **RandomOverSampler** aplicado apenas no treino;
- ✅ **Treinamento do modelo final** Random Forest **sem ajuste de hiperparâmetros**, após análise prévia que mostrou desempenho competitivo já com os parâmetros padrão;
- ✅ **Validação cruzada estratificada** (StratifiedKFold) para avaliação robusta do modelo;
- ✅ **Teste final** no conjunto de teste (20% dos dados não vistos);
- ✅ **Salvamento do modelo** em arquivo `.sav` para uso futuro;
- ✅ **Documentação clara do pipeline para predição em produção**, incluindo requisitos de pré-processamento.

---

## 📊 Principais Resultados

### ✅ Validação Cruzada no Treino (com Oversampling):

| Métrica    | Resultado Médio |
|-------------|-----------------|
| Acurácia    | 0.9561          |
| Precisão    | 0.9502          |
| Recall      | 0.9627          |
| F1-Score    | 0.9564          |

---

### ✅ Teste Final no Conjunto Não Visto (20%):

| Métrica    | Resultado |
|-------------|-----------|
| Acurácia    | 0.8935    |
| Precisão    | 0.8429    |
| Recall      | 0.7231    |
| F1-Score    | 0.7784    |

> 📌 **Conclusão Principal:** Apesar da queda natural nas métricas ao testar em dados não vistos, os resultados mantêm patamares elevados, **sem evidência de overfitting**, mostrando boa capacidade de generalização do modelo.

---

## 📝 Como Executar

### Clone o repositório:
```bash
git clone [https://github.com/GlauberBomtempo/7daysofcode7/blob/main/7daysofcode7.ipynb]
```
Instale as bibliotecas necessárias:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn openpyxl
```
Execute o notebook:
```bash
Abra o 7daysofcode7.ipynb no Jupyter Notebook, Google Colab ou ambiente de sua preferência.
```

🚀 Requisitos para Produção
O notebook documenta claramente o pipeline necessário para que o modelo possa ser utilizado em produção, incluindo:

✅ Transformações obrigatórias para novos dados:

    - Remoção de colunas (track_id, track_name, album_name);

    - Criação de artistas_relevantes baseado em lista fixa dos artistas mais populares;

    - Aplicação de OneHotEncoding na variável track_genre, gerando 113 colunas;

✅ Exemplo de função para leitura de nova observação via planilha .xlsx com 19 colunas e transformação automática para as 128 colunas finais necessárias ao modelo;

✅ Exemplo de carregamento do modelo .sav e execução de predição;

✅ Flexível para integração em dashboards (Streamlit, Gradio) ou APIs (Flask, FastAPI).

📂 Estrutura do Repositório
```cpp
7daysofcode7.ipynb → Notebook completo da análise final do desafio 7;
README.md → Este arquivo de descrição do projeto.
```
🚩 Conclusão
Este projeto avança além da proposta base da Alura, aplicando práticas robustas de feature engineering customizadas, validação cruzada rigorosa e um pipeline transparente para predição em produção.

Os resultados confirmam boa generalização sem overfitting, além de documentar boas práticas para uso prático em aplicações reais.

📢 Observação Importante
Este projeto tem finalidade educacional, utilizando dataset público do Spotify via Alura.

👨‍💻 Desenvolvido por
Gláuber Lopes Bomtempo
