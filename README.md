# 📊 Visualização do Projeto
[Clique aqui para abrir o Grafo Interativo](https://gabriel-bruck.github.io/Clash-Royale-Network-Analysis/)

## 🧠 A Lógica do Projeto

O diferencial desta análise é a **transformação de Decks (Listas)** em **Relacionamentos (Grafos)**. Em vez de apenas listar cartas populares, o algoritmo mapeia como elas coexistem no ecossistema competitivo.

## OBJETIVO

Demonstrar as possibilidades da biblioteca NetworkX para criação e modelagem de grafo.


### 🔄 Fluxo de Processamento
* **Extração:**  Utilizei os  **30 decks** com as maiores taxas de vitória (*Win Rate*) do cenário atual segundo site Royale Api, raspagem de dados feita anteriormente.
* **Criandos as ligações:** Se a **Carta A** e a **Carta B** aparecem no mesmo deck, o código estabelece uma **Aresta (ligação)** entre elas.
* **Peso de Conexão:** Quanto mais vezes o par de cartas aparece nos Top 30, maior o "peso" da ligação, indicando sinergias (combos).
* **Clusterização (K-Means):** O algoritmo de *Machine Learning* agrupa automaticamente cartas que compartilham os mesmos "parceiros", revelando grupos como *Log-Bait*

---

## 🛠️ Tecnologias e Bibliotecas

| Ferramenta | Aplicação |
| :--- | :--- |
| **Pandas** | Estruturação e limpeza dos dados crus |
| **NetworkX** | Motor de Teoria dos Grafos para calcular métricas de centralidade. |
| **Scikit-learn** | Implementação do agrupamento **K-Means** e validação de clusters. |
| **Plotly** | Engine de visualização para gerar gráficos interativos com Zoom e Hover. |
| **Itertools** | Processamento de combinações matemáticas para gerar pares de cartas. |

---

## 📊 Anatomia do Grafo

A visualização final utiliza dos seguintes elementos para traduzir os dados estatísticos complexos:

* **⭕ Nós (Vértices):** Representam as cartas individuais. O **tamanho** do círculo é proporcional à sua popularidade (frequência) no meta.
* **🔗 Linhas (Arestas):** Representam a sinergia. **Linhas mais grossas** indicam "combos" obrigatórios que definem o meta-jogo.


## 📊 Resultados da Análise: Identificação dos grupos/cluster:

Abaixo estão os 6 clusters (grupos) identificados pelo algoritmo **K-Means**. A análise revelou como o meta se organiza organicamente em torno de cartas "Core" e estratégias específicas.

### 🏗️ Estrutura dos Clusters e Lógica Estratégica

| Grupo | Nome do Arquétipo | Core Card | Lógica de Funcionamento |
| :--- | :--- | :--- | :--- |
| **0** | **Log Bait** | 🚀 Rocket | Foca em forçar o gasto do "Tronco" adversário com *Princess* e *Gang* para liberar o dano do *Goblin Barrel*. O Rocket serve como finalizador pesado. |
| **1** | **Beatdown** | 🔥 Fireball | Cartas pesadas (*Mega Knight*, *Gigante Real*) focadas em "atropelar" o adversário. A *Fireball* limpa o caminho para o push gigante chegar à torre. |
| **2** | **Ciclo Rápido** | 🪵 The Log | Estratégia de baixo custo (2.6 ou similar) para rodar o deck e jogar o *Corredor* o máximo de vezes possível. O *Log* é a peça de controle constante. |
| **3** | **Champions / Lendárias** | 🌪️ Tornado | Decks de alta técnica que giram em torno de combos específicos (ex: *Graveyard* ou *E-Giant*). O *Tornado* é o elo que puxa a eficácia dessas estratégias. |
| **4** | **Tank / Suporte** | 🛢️ Barb. Barrel | O grupo das "ferramentas". Cartas de utilidade como *P.E.K.K.A* e *Zap* que dão suporte a tanques. O barril faz o "trabalho sujo" de defesa rápida. |
| **5** | **Construções / Defesa** | 👑 Archer Queen | O estilo "Pedreiro" (Siege). Foco em defesa impenetrável com *Tesla/X-Besta* e contra-ataques precisos com a habilidade da Rainha Arqueira. |

---

### 💡 Insights Estratégicos (Data-Driven)

1.  **A CARTA PONTE:** O `The Log` foi identificado como o maior elo entre diferentes decks, possuindo a maior versatilidade geométrica no grafo.
2.  **O CORINGA DO META:** Devido à sua onipresença, o `The Log` é a carta que define a transição entre estilos, sendo essencial tanto no Ciclo Rápido quanto na defesa de outros grupos.
3.  **ESTILO DOMINANTE:** O **Cluster 2 (Ciclo Rápido)** é o maior grupo de cartas mapeado, indicando uma tendência atual de decks leves e alta rotatividade de cartas no Top 30.

---
### 🔍 Metodologia de Nomeação
Os nomes foram atribuídos com base na **Sinergia das cartas**:
* **Log Bait:** Nomeado pela mecânica de "isca" de feitiços.
* **Beatdown:** Nomeado pela força bruta de atropelamento.
* **Ciclo Rápido:** Nomeado pela velocidade de rotação do deck.
* **Champions:** Focado em cartas lendárias e campeões de mecânica complexa.
* **Tank/Suporte:** Identificado como o kit de ferramentas de proteção.
* **Construções/Defesa:** Identificado pela estratégia de atacar sem atravessar a ponte.

---
