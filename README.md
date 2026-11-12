# 🩺 Regressão Linear Múltipla — Previsão de Colesterol

Projeto de Machine Learning que usa **Regressão Linear Múltipla** para prever o resultado do **exame de colesterol total** de um paciente a partir de características como idade, peso, altura, nível de atividade física, tabagismo e grupo sanguíneo. O projeto cobre o ciclo completo: análise exploratória, treinamento, validação do modelo e entrega das previsões por meio de uma **interface web com Gradio**.

> 🚧 Projeto em desenvolvimento.

## 💡 Contexto

Um laboratório de análises clínicas que conduz testes de colesterol deseja avaliar, com base em características dos pacientes (idade, nível de atividade física, peso, entre outras), **se essas variáveis influenciam o resultado do exame de colesterol total**.

Para isso, o projeto treina um algoritmo de **regressão linear múltipla** capaz de **prever o resultado do exame de colesterol** a partir das características do paciente.

## 🎯 Objetivo

- Avaliar quais características dos pacientes influenciam o nível de colesterol.
- Treinar e validar um modelo capaz de prever o colesterol total de um paciente.
- Salvar o modelo treinado e disponibilizá-lo em uma interface (UI).

## 📐 Como funciona a regressão linear múltipla

A regressão linear múltipla estende a regressão linear simples para **várias variáveis independentes** (`x1, x2, ..., xn`):

```
colesterol = β0 + β1·x1 + β2·x2 + ... + βn·xn
```

- **β0 (intercepto):** valor previsto quando todas as features valem zero.
- **β1 ... βn (coeficientes):** quanto o colesterol varia para cada unidade a mais da feature correspondente, **mantendo as demais constantes**.

Variáveis categóricas (como grupo sanguíneo e tabagismo) precisam ser convertidas para formato numérico (ex.: *one-hot encoding*) antes do treino.

## 📊 Dataset

Arquivo: [`datasets/dataset_colesterol.csv`](datasets/dataset_colesterol.csv) — 1.000 registros, com alguns valores ausentes (3 a 4 por coluna) a serem tratados.

| Coluna               | Tipo        | Descrição                       | Valores / faixa              |
|----------------------|-------------|---------------------------------|------------------------------|
| `Id`                 | —           | Identificador do paciente       | 1 a 1000                     |
| `Grupo Sanguíneo`    | Categórica  | Tipo sanguíneo                  | A, B, AB, O                  |
| `Fumante`            | Categórica  | Se o paciente fuma              | Sim, Não                     |
| `Nível de Atividade` | Categórica  | Nível de atividade física       | Baixo, Moderado, Alto        |
| `Idade`              | Numérica    | Idade em anos                   | 20 a 79                      |
| `Peso`               | Numérica    | Peso em kg                      | 15,4 a 158,1                 |
| `Altura`             | Numérica    | Altura em cm                    | 160 a 190                    |
| `Colesterol`         | Numérica    | Colesterol total (alvo)         | 36,26 a 372,67               |

## 🧠 Etapas do projeto

```
Carregar os Dados → Realizar EDA → Preparar Dataset Treino e Teste → Treinar Modelo
→ Validar Modelo (Métricas + Análise de Resíduos) → Salvar Modelo → Entregar Modelo via UI
```

- [ ] Carregamento dos dados em um DataFrame do Pandas
- [ ] Análise exploratória dos dados (EDA)
- [ ] Preparação do dataset de treino e teste (tratamento de nulos e encoding)
- [ ] Treinamento do modelo de regressão linear múltipla
- [ ] Validação do modelo com métricas (R², MAE, RMSE)
- [ ] Análise de resíduos
- [ ] Salvamento do modelo treinado
- [ ] Entrega do modelo via UI com Gradio

## 🛠️ Tecnologias

| Finalidade | Bibliotecas |
|---|---|
| Manipulação de dados | Pandas |
| Visualização | Matplotlib, Seaborn |
| Modelagem | Scikit-learn |
| Estatística | SciPy |
| Interface (UI) | Gradio |
| Ambiente | Jupyter, Pipenv |

## 🚀 Como executar

Pré-requisitos: Python 3.14 e [pipenv](https://pipenv.pypa.io/).

```bash
git clone https://github.com/Manoelhns/regressao-linear-multipla.git
cd regressao-linear-multipla
pipenv install
```

Abra o [`modelo_colesterol.ipynb`](modelo_colesterol.ipynb) no VS Code ou no Jupyter e selecione o kernel do ambiente pipenv.

## 📁 Estrutura

```
.
├── datasets/
│   └── dataset_colesterol.csv   # dados dos pacientes e resultado do exame
├── modelo_colesterol.ipynb      # EDA, treino, validação e análise de resíduos
├── Pipfile
├── Pipfile.lock
├── LICENSE
└── README.md
```

## 📄 Licença

Distribuído sob a licença MIT. Veja [LICENSE](LICENSE).
