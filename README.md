# dashboard-delivery-analysis
Projeto 3: Dashboard de Delivery — Análise operacional com Power BI + Chart.js | Portfólio Data Analyst
# 🛵 Dashboard de Delivery — Food Delivery Analysis

## Sobre o Projeto

Análise operacional de um serviço de food delivery na Índia, com foco em **tempo de entrega, fatores de impacto (clima, tráfego, festivais)** e desempenho de entregadores. Inclui dashboard interativo e fórmulas DAX para replicação no Power BI.

Este projeto faz parte do meu portfólio como **Data Analyst** em transição de carreira.

## 🎯 Perguntas de Negócio

1. Qual o tempo médio de entrega e como varia por cidade?
2. Qual o impacto do tráfego no tempo de entrega?
3. Como condições climáticas afetam a operação?
4. Festivais impactam o tempo de entrega?
5. Qual tipo de veículo é mais usado?
6. Como está a distribuição de ratings dos entregadores?

## 🔍 Principais Insights

- **Festivais DOBRAM o tempo de entrega** (45.5 min vs 26.1 min normal)
- **Congestionamento (Jam)** adiciona ~10 min ao tempo vs tráfego baixo
- **Neblina (Fog)** é a pior condição climática — +7 min vs dias de sol
- **Semi-Urban** tem os maiores tempos (~50 min) por distâncias maiores
- **Motos** dominam 60% das entregas — mais ágeis no trânsito
- **Rating médio** de 4.63/5 — qualidade alta dos entregadores
- **Scooters elétricas** ainda são 8% — oportunidade de sustentabilidade

## 📊 KPIs do Dashboard

| Métrica | Valor |
|---|---|
| Total de Pedidos | 42.548 |
| Entregadores Ativos | 1.320 |
| Tempo Médio de Entrega | 26.4 min |
| Rating Médio | 4.63 ⭐ |
| Distância Média | 38.0 km |

## 💡 Recomendações de Negócio

| Situação | Ação Recomendada |
|---|---|
| **Festivais** | Escalar entregadores extras — tempo dobra |
| **Congestionamento** | Rotas alternativas em horários de pico |
| **Neblina** | Alertar clientes sobre atraso estimado |
| **Semi-Urban** | Criar hubs intermediários para reduzir distância |
| **Scooters elétricas** | Expandir frota — reduz custo e poluição |

## 🛠️ Ferramentas Utilizadas

- **Power BI** — dashboard interativo (fórmulas DAX documentadas)
- **HTML/CSS + Chart.js** — preview do dashboard (abrir no navegador)
- **Python + Matplotlib/Seaborn** — análise e gráficos estáticos
- **Dataset** — [Food Delivery Dataset](https://github.com/Ritik1129/Food_Delivery_Dataset) — 43.685 pedidos

## 📁 Estrutura do Projeto

\`\`\`
├── README.md                     # Este arquivo
├── dashboard_delivery.html       # Dashboard interativo (abrir no navegador)
└── *.png                         # 8 gráficos de análise
\`\`\`

## 📐 Fórmulas DAX (Power BI)

\`\`\`dax
-- Tempo Médio de Entrega
Tempo Medio = AVERAGE(delivery[Time_taken_min])

-- Rating Médio
Rating Medio = AVERAGE(delivery[Delivery_person_Ratings])

-- Total de Pedidos
Total Pedidos = COUNTROWS(delivery)

-- % Entregas em Festival
% Festival = DIVIDE(
    CALCULATE(COUNTROWS(delivery), delivery[Festival] = "Yes"),
    COUNTROWS(delivery)
)

-- Impacto Festival
Tempo Festival = CALCULATE(AVERAGE(delivery[Time_taken_min]), delivery[Festival] = "Yes")
Tempo Normal = CALCULATE(AVERAGE(delivery[Time_taken_min]), delivery[Festival] = "No")
Impacto Festival = [Tempo Festival] - [Tempo Normal]
\`\`\`

## 👤 Autor

**ct-melo** — Estudante de Ciências de Dados, em transição de carreira para Data Analytics
