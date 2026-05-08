# Curso Completo de Machine Learning em Python

Curso prático de Machine Learning em português, com 16 Jupyter Notebooks cobrindo desde os fundamentos até técnicas avançadas. Cada módulo traz teoria com equações, exemplos com dados reais brasileiros e visualizações didáticas.

---

## Conteúdo do Curso

| # | Notebook | Tópicos |
|---|----------|---------|
| 01 | Introdução ao ML | Tipos de aprendizado, processo de ML, comparação com programação tradicional |
| 02 | Pré-processamento | Valores ausentes, outliers (IQR/Z-score), normalização, encoding, WOE/IV |
| 03 | Feature Engineering | RFM, features temporais, Box-Cox, Yeo-Johnson, PCA, t-SNE |
| 04 | Regressão | OLS, Ridge, LASSO, Elastic Net, GLM Poisson, diagnóstico de resíduos |
| 05 | Classificação | Regressão Logística, Árvores de Decisão, KNN, OvO/OvA multiclasse |
| 06 | Avaliação de Modelos | Matriz de confusão, ROC, CAP, Lift, KS, cross-validation |
| 07 | Regras de Associação | Apriori, suporte, confiança, lift, regras de sequência |
| 08 | Clustering | K-means, DBSCAN, hierárquico, silhueta, perfil de segmentos |
| 09 | Redes Neurais | Perceptron, MLP, Keras, funções de ativação, SOM |
| 10 | SVM | Linear, RBF, kernels, One-Class SVM, SVR |
| 11 | Ensemble | Bagging, AdaBoost, Random Forest, XGBoost |
| 12 | Redes Bayesianas | Teorema de Bayes, Naive Bayes (Gaussian, Multinomial, Bernoulli) |
| 13 | Seleção de Variáveis | Filter, RFE, LASSO, BART, AUC vs nº de features |
| 14 | Interpretação (XAI) | Feature Importance, PDP, ICE, LIME, SHAP |
| 15 | Deploy | Pipeline sklearn, joblib, PSI (drift), fairness, Model Card |
| 16 | Armadilhas | Data leakage, overfitting, imbalanceamento, maldição da dimensão |

---

## Pré-requisitos

- Python 3.10 ou superior
- pip atualizado
- ~3 GB de espaço em disco (ambiente + outputs)

Não é necessário instalar Anaconda, mas é recomendado para gerenciar ambientes.

---

## Configuração do Ambiente

### Opção 1 — Ambiente virtual com pip (recomendado)

```bash
# 1. Crie e ative o ambiente virtual
python -m venv .venv

# Windows (PowerShell)
.venv\Scripts\Activate.ps1

# Linux / macOS
source .venv/bin/activate

# 2. Atualize o pip
pip install --upgrade pip

# 3. Instale todas as dependências
pip install -r requirements.txt
```

### Opção 2 — Conda

```bash
# 1. Crie o ambiente
conda create -n ml-curso python=3.11 -y

# 2. Ative
conda activate ml-curso

# 3. Instale as dependências
pip install -r requirements.txt
```

### Opção 3 — uv (instalação mais rápida)

```bash
# Instale o uv se ainda não tiver
pip install uv

# Crie o ambiente e instale tudo de uma vez
uv venv .venv
uv pip install -r requirements.txt
```

---

## Executando o Curso

### Iniciar o Jupyter

```bash
# Com o ambiente ativado, na raiz do projeto
jupyter notebook notebooks/
```

Isso abrirá o Jupyter no navegador. Abra os notebooks em ordem numérica.

### Executar um notebook pela linha de comando

```bash
jupyter nbconvert --to notebook --execute --inplace notebooks/01_introducao_ml.ipynb
```

### Executar todos os notebooks em sequência

```bash
# Windows (PowerShell)
Get-ChildItem notebooks\*.ipynb | Sort-Object Name | ForEach-Object {
    Write-Host "Executando $($_.Name)..."
    jupyter nbconvert --to notebook --execute --inplace $_.FullName
}

# Linux / macOS
for nb in notebooks/*.ipynb; do
    echo "Executando $nb..."
    jupyter nbconvert --to notebook --execute --inplace "$nb"
done
```

---

## Estrutura de Diretórios

```
ML-course/
├── notebooks/          # 16 Jupyter Notebooks
│   ├── 01_introducao_ml.ipynb
│   ├── 02_preprocessamento_dados.ipynb
│   └── ...
├── imagens/            # Gráficos gerados pelos notebooks (criado automaticamente)
├── requirements.txt    # Dependências Python
└── README.md
```

Os notebooks salvam automaticamente os gráficos em `imagens/` ao serem executados.

---

## Dependências Principais

| Biblioteca | Versão mínima | Uso |
|------------|---------------|-----|
| scikit-learn | 1.3 | Algoritmos de ML, pipelines, métricas |
| pandas | 2.0 | Manipulação de dados |
| numpy | 1.24 | Computação numérica |
| matplotlib / seaborn | 3.7 / 0.12 | Visualizações |
| xgboost | 2.0 | Gradient Boosting |
| shap | 0.43 | Explicabilidade (SHAP values) |
| lime | 0.2 | Explicações locais |
| statsmodels | 0.14 | GLM, testes estatísticos |
| mlxtend | 0.23 | Apriori, regras de associação |
| minisom | 2.3 | Self-Organizing Maps |
| imbalanced-learn | 0.11 | SMOTE, dados desbalanceados |
| networkx | 3.0 | Grafos de regras de associação |

> **Nota:** As bibliotecas `shap`, `lime`, `mlxtend` e `minisom` são opcionais — os notebooks detectam automaticamente se estão instaladas e exibem alternativas quando não estão disponíveis.

---

