# 🏦 Previsão de Aprovação de Crédito

Este projeto tem como objetivo prever a aprovação de crédito com base em características socioeconômicas dos clientes. Utilizamos técnicas de Machine Learning, com atenção especial ao desequilíbrio de classes, para desenvolver um modelo preditivo robusto e interpretável.

---

## 📊 Sobre o Dataset

- Origem: [Kaggle - Credit Card Approval Prediction](https://www.kaggle.com/datasets/rikdifos/credit-card-approval-prediction)
- Tamanho: ~37 mil amostras
- Variável-alvo: `Status` (1 = aprovado, 0 = não aprovado)

---

## 🧠 Técnicas Utilizadas

- Pré-processamento com `Pipeline` do Scikit-learn
- Codificação de variáveis categóricas com `OneHotEncoder`
- Balanceamento de dados:
  - `SMOTE`
  - `Undersampling`
  - `Class Weight = balanced`
- Modelagem com `Random Forest`
- Avaliação com:
  - F1-score
  - AUC
  - Matriz de confusão
  - Relatório de classificação
  - Curva ROC

---

## 📈 Principais Resultados

| Estratégia        | F1-score | AUC   | Recall Classe 0 | Precision Classe 0 | Recall Classe 1 | Precision Classe 1 |
|-------------------|----------|-------|------------------|---------------------|------------------|---------------------|
| **SMOTE**         | 0.9273   | 0.7930 | 0.40             | 0.45                | 0.93             | 0.92                |
| **Undersampling** | 0.7901   | 0.7448 | 0.67             | 0.22                | 0.68             | 0.94                |
| **ClassWeight**   | 0.9091   | 0.7917 | 0.51             | 0.38                | 0.89             | 0.93                |

### 📌 Observações

Embora SMOTE e ClassWeight apresentem excelente performance para a classe majoritária (1), ambos mostram baixa eficácia para identificar a minoria (0). O Undersampling melhora o recall da classe 0, mas prejudica fortemente a classe 1.

---

## 🛠️ Como Executar

1. Clone o repositório:
   ```bash
   git clone https://github.com/gabrielbdoc/credito-aprovacao.git
   cd credito-aprovacao
   ```
2. Instale os requisitos
   ```bash
   pip install -r requirements.txt
   ```
3. Execute o notebook no Jupyter ou Google Colab:
   Previsao_Credito.ipynb
