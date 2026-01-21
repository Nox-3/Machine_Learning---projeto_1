# Análise Exploratória de Dados - Dataset Censo Adulto

## 📋 Descrição do Projeto

Este projeto realiza uma **Análise Exploratória de Dados (EDA)** completa do dataset **Adult Census Income**, com o objetivo de preparar os dados para futuros modelos de Machine Learning que preveem se a renda anual de um indivíduo é superior a $50.000.

## 🎯 Objetivo

Analisar características demográficas e socioeconômicas de indivíduos para entender quais fatores estão associados a rendas superiores a $50.000 anuais, preparando o dataset para modelagem preditiva.

## 📊 Sobre o Dataset

O **Adult Census Income Dataset** contém informações demográficas extraídas de dados de censo, com 32.561 registros e 15 variáveis.

**Fonte:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/2/adult)

### Variáveis do Dataset

| Variável | Tipo | Descrição |
|----------|------|-----------|
| `age` | Numérica | Idade do indivíduo |
| `workclass` | Categórica | Categoria de emprego (Private, Self-emp-not-inc, etc.) |
| `fnlwgt` | Numérica | Peso estatístico final (representa quantas pessoas a amostra representa) |
| `education` | Categórica | Nível de escolaridade |
| `education-num` | Numérica | Número que representa o nível de escolaridade |
| `marital-status` | Categórica | Estado civil |
| `occupation` | Categórica | Tipo de ocupação |
| `relationship` | Categórica | Relação do indivíduo na família |
| `race` | Categórica | Raça do indivíduo |
| `sex` | Categórica | Gênero (Male ou Female) |
| `capital-gain` | Numérica | Ganhos de capital |
| `capital-loss` | Numérica | Perdas de capital |
| `hours-per-week` | Numérica | Número de horas trabalhadas por semana |
| `native-country` | Categórica | País de origem |
| `income` | Categórica | **Variável alvo:** >50K ou <=50K |

## 🔍 Principais Descobertas

### Distribuição da Variável Alvo
- **75,92%** dos indivíduos têm renda ≤ $50K
- **24,08%** dos indivíduos têm renda > $50K
- Dataset apresenta desbalanceamento de classes

### Fatores Associados a Alta Renda (>$50K)

#### 📈 Variáveis Numéricas
- **Idade:** Indivíduos mais velhos têm maior probabilidade de alta renda
- **Horas trabalhadas:** Maior carga horária semanal está associada a rendas mais altas
- **Escolaridade:** Níveis educacionais mais elevados correlacionam com maior renda

#### 📊 Variáveis Categóricas
- **Educação:** Doutorado (74%), Mestrado (56%) e Bacharelado (41%) apresentam maior proporção de alta renda
- **Estado Civil:** Casados (45%) têm maior probabilidade de renda >$50K
- **Ocupação:** Cargos executivos (48%) e profissionais especializados (45%) lideram
- **Tipo de Trabalho:** Autônomos incorporados (56%) apresentam maior proporção
- **Gênero:** Desbalanceamento significativo - homens (31%) vs mulheres (11%)

### Valores Ausentes
- `occupation`: 5,66% de valores ausentes
- `workclass`: 5,64% de valores ausentes
- `native-country`: 1,79% de valores ausentes

## 🛠️ Preparação dos Dados

### Etapas Realizadas

1. **Tratamento de Valores Ausentes**
   - Remoção de 2.399 linhas com valores ausentes
   - Dataset final: 30.162 registros

2. **Criação de Variáveis Derivadas**
   - `age_group`: Faixas etárias (jovem, adulto, meia-idade, idoso)
   - `hours_per_week_group`: Faixas de carga horária (até 30h, 31-40h, 41-60h, mais de 60h)

3. **Padronização de Variáveis Numéricas**
   - Aplicação de `StandardScaler` nas variáveis: `age`, `fnlwgt`, `education-num`, `capital-gain`, `capital-loss`, `hours-per-week`
   - Média ≈ 0 e desvio-padrão ≈ 1

4. **Codificação de Variáveis Categóricas**
   - One-hot encoding para todas as variáveis categóricas
   - Dataset final: 102 features

5. **Preparação da Variável Alvo**
   - Conversão para formato binário: 0 (≤$50K) e 1 (>$50K)

## 📁 Estrutura do Projeto

```
Machine_Learning - projeto_1/
│
├── data/
│   └── adult.data              # Dataset original
│
├── projeto_1_eda.ipynb         # Notebook com análise completa
│
└── README.md                   # Este arquivo
```

## 🚀 Como Executar

### Pré-requisitos

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

### Executando o Notebook

1. Clone o repositório ou baixe os arquivos
2. Certifique-se de que o arquivo `adult.data` está na pasta `data/`
3. Abra o Jupyter Notebook:
   ```bash
   jupyter notebook projeto_1_eda.ipynb
   ```
4. Execute as células sequencialmente

## 📚 Bibliotecas Utilizadas

- **pandas**: Manipulação e análise de dados
- **numpy**: Operações numéricas
- **matplotlib**: Visualizações básicas
- **seaborn**: Visualizações estatísticas avançadas
- **scikit-learn**: Pré-processamento e padronização

## 🔮 Próximos Passos

1. **Divisão Treino/Teste**: Separar dataset em conjuntos de treino (70-80%) e teste (20-30%)
2. **Modelagem**: Testar algoritmos de classificação
   - Regressão Logística
   - Árvore de Decisão
   - Random Forest
   - Gradient Boosting
   - XGBoost
3. **Validação Cruzada**: Otimização de hiperparâmetros
4. **Avaliação**: Métricas de desempenho (Acurácia, Precisão, Recall, F1-Score, AUC-ROC)
5. **Interpretabilidade**: Análise de importância das features

## 📝 Observações

- O dataset apresenta desbalanceamento de classes que deve ser considerado na modelagem
- Variáveis como `capital-gain` e `capital-loss` apresentam distribuições altamente assimétricas
- O desbalanceamento de gênero na variável alvo sugere possíveis vieses nos dados
- A padronização das variáveis numéricas é essencial para modelos sensíveis à escala

## 👨‍💻 Autor

Projeto desenvolvido por Lucas para fins de estudo e aprendizado.

## 📄 Licença

Este projeto é de código aberto e está disponível para fins educacionais.

---

**Data de Criação:** Janeiro de 2026
