<h1 align="center">
    🥗 Ecossistema de Inteligência Alimentar — São Luís/MA
</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas">
  <img src="https://img.shields.io/badge/Folium-77B829?style=for-the-badge&logo=folium&logoColor=white" alt="Folium">
  <img src="https://img.shields.io/badge/Estruturas%20de%20Dados-77808C?style=for-the-badge" alt="Estruturas de Dados">
  <img src="https://img.shields.io/badge/Acadêmico-orange?style=for-the-badge" alt="Acadêmico">
</p>

Plataforma de inteligência de dados desenvolvida para otimizar e apoiar a gestão de segurança alimentar em áreas de vulnerabilidade socioeconômica na capital maranhense, com foco estratégico em comunidades ribeirinhas e zonas de alto risco mapeadas.

## 📌 Visão Geral do Problema & Impacto
O sistema centraliza dados demográficos e automatiza a análise estratégica de risco, permitindo que a gestão pública e as secretarias municipais se antecipem a crises sazonais — como as severas enchentes que historicamente afetam São Luís no primeiro semestre. A ferramenta transforma dados brutos em inteligência geográfica para a tomada de decisões rápidas na distribuição de suprimentos emergenciais.

---

## 🛠️ Engenharia de Dados & Estruturas de Dados Customizadas

Para garantir a máxima performance, previsibilidade de tempo de execução e integridade no processamento dos dados, o projeto foi construído utilizando estruturas otimizadas para cada caso de uso:

| Estrutura / Algoritmo | Operação no Sistema | Justificativa Teórica & Complexidade |
| :--- | :--- | :--- |
| **Dicionários (Hash Maps)** | Cadastro e busca unificada de famílias por CPF/NIS | Permite acesso aos atributos de vulnerabilidade em complexidade de tempo constante **$O(1)$**. |
| **Conjuntos (Hash Sets)** | Monitoramento da cobertura territorial e auditoria | Operações de diferença de conjuntos para identificar instantaneamente bairros oficiais ainda desassistidos em **$O(1)$** por verificação. |
| **Merge Sort Customizado** | Algoritmo de ordenação estável para o ranking de prioridades | Garante a **estabilidade** dos dados (famílias com o mesmo risco mantêm a ordem relativa) com tempo previsível de **$O(n \log n)$** mesmo no pior caso. |
| **Matrizes (Listas Aninhadas)** | Cruzamento de dados geoespaciais e pluviométricos | Estrutura base para alimentar os mapas de calor e os gráficos de tendência temporal ($n$ bairros $\times$ $m$ meses) com complexidade de iteração de **$O(n \times m)$**. |

### O Critério de Ordenação Composto
A engine de priorização (implementada em `src/sorting.py`) adota dois níveis hierárquicos rígidos:
1. **Nível de Insegurança Alimentar (Peso Máximo):** `Grave (3)` > `Moderada (2)` > `Leve (1)` > `Seguro (0)`. Situações críticas são atendidas prioritariamente, independente de fatores financeiros.
2. **Renda Per Capita (Desempate):** Em caso de empate no nível de insegurança, o sistema prioriza a família com a menor renda per capita em salários mínimos (`renda_pc_sm`).

---

## 📊 Inteligência Visual (Dashboard Interativo)

O ecossistema orquestra dados e exporta um painel estratégico puramente em HTML corporativo (`dashboard_slz.html`), composto por:

1. **Mapa de Calor (Geospatial Heatmap):** Renderização visual das zonas de risco alimentar utilizando a biblioteca `Folium`, permitindo o mapeamento de precisão de comunidades isoladas.
2. **Monitoramento Sazonal:** Gráficos que cruzam índices pluviométricos simulados com alertas automáticos de necessidade de estoque emergencial.
3. **Perfil de Vulnerabilidade:** Distribuição estatística percentual do nível de segurança alimentar da base cadastrada.

---

## 📂 Arquitetura do Sistema

```text
/
├── /.vscode             # Configurações padronizadas do ambiente (Workspace)
├── /data                # Base de dados (JSON) e scripts simuladores / pipeline de ETL
│   ├── bairros_coords.json
│   ├── chuvas_slz.json
│   ├── familias_slz.json
│   └── [scripts de geração e classificação de dados...]
├── /docs                # Relatórios técnicos, benchmarks e documentação de suporte
│   └── relatorio.md     # Análise de complexidade e testes empíricos dos algoritmos
├── /src                 # Camadas de código-fonte (Arquitetura modularizada)
│   ├── logic.py         # Regras de negócio centrais e análise territorial
│   ├── sorting.py       # Implementação pura de algoritmos de ordenação (Merge Sort)
│   ├── structures.py    # Modelagem de dados e abstração de I/O
│   └── visuals.py       # Motor de integração gráfica (Folium e Chart.js)
├── main.py              # Script central de orquestração e execução do ecossistema
├── dashboard_slz.html   # Interface dashboard interativa gerada dinamicamente
└── requirements.txt     # Dependências estruturais do projeto

```

---

## 🚀 Como Executar o Projeto

### Pré-requisitos

Certifique-se de ter o **Python 3.10 ou superior** instalado na sua máquina.

### Passos para execução

1. **Acesse o repositório e faça o clone:**
   Você pode acessar a página do projeto em [github.com/cassia-nascimento/intel-alimentar-slz](https://github.com/cassia-nascimento/intel-alimentar-slz) ou clonar diretamente pelo terminal com o comando abaixo:

```bash
git clone https://github.com/cassia-nascimento/intel-alimentar-slz.git
cd intel-alimentar-slz

```

2. **Instale as dependências necessárias:**

```bash
pip install -r requirements.txt

```

3. **Execute o processamento e gere o Dashboard:**

```bash
python main.py

```

4. **Visualizar os Resultados:**
O script gerará um arquivo chamado `dashboard_slz.html` na raiz do projeto. Basta abrir esse arquivo diretamente em qualquer navegador web (Chrome, Edge, Firefox) para interagir com o mapa e os dados.

---

## 👩‍💻 Equipe de Desenvolvimento

Projeto acadêmico desenvolvido para a disciplina de **Estruturas de Dados** na **UNDB**.

* **Cássia Nascimento** — [GitHub](https://github.com/cassia-nascimento)
* **Leonardo Ferreira** — [GitHub](https://github.com/leonardoferrza)
* **Melissa Wolff** — [GitHub](https://github.com/melwolff13)
