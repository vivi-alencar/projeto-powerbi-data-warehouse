# ⚙️ Decisões de Design — Projeto Power BI (Camada Gold)

Este documento registra as principais escolhas feitas no desenvolvimento do dashboard de vendas (anos 2011–2013), destacando a lógica de modelagem, KPIs, filtros e visualizações.  
Mais do que listar gráficos, ele explica **como cada página foi desenhada para contar uma parte da história de negócio**.

---

## 🔧 Modelagem de Dados

- **Período considerado:** apenas 2011–2013.  
  - 2010 e 2014 foram excluídos porque os dados estavam incompletos, distorcendo KPIs anuais e análises comparativas.  
  - Mantendo apenas anos completos, garantimos consistência temporal.  

- **Esquema estrela:**  
  - Fato: `fact_sales` (transações de vendas).  
  - Dimensões: `dim_products`, `dim_customers`, `date_dim`.  

- **Medidas e organização:**  
  - Criada tabela `00_Measures` para centralizar cálculos DAX.  
  - Incluídas medidas auxiliares (ex.: `[Year First]`, `[Year Last]`) para KPIs como Δ Receita.  
  - Ticket médio (AOV) calculado como **Receita ÷ Pedidos** (cálculo derivado).  

---

## 🎯 KPIs Principais

- **Receita Total** → indicador central de crescimento.  
- **Pedidos (Order Count)** → reflete volume de clientes/ordens.  
- **Ticket Médio (AOV)** → receita por pedido; ajuda a entender mudança de mix.  
- **Margem Bruta %** → escolhido em vez de margem absoluta, permitindo comparações relativas entre anos, produtos e países.  
- **Rolling 12M** → suaviza variações mensais e mostra tendência de longo prazo.  
- **YoY % e Δ p.p.** → evolução anual recente, aplicada a Receita, Pedidos, Ticket Médio e Margem.  
- **Clientes Ativos, Novos e % Retornantes** → KPIs adicionados na Página 3 para entender fidelização.  

---

## 🎚️ Filtros e Slicers

- **Página 1 (Executiva):** sem slicers → visão fixa, comparável entre prints.  
- **Página 2 (Produtos & Margem):** slicers de **Ano** e **Categoria** → análise focada no produto, sem misturar escalas.  
- **Página 3 (Clientes & Geografia):** slicer de **País** e **Ano**.  
- **Página 4 (Tempo & KPIs Avançados):** slicer de **País** → foco em comparação temporal (2011–2013 fixos).  

---

## 📊 Visualizações e Narrativa

### Página 1 – Executiva  
**Missão:** entregar um retrato rápido e coerente da evolução do negócio 2011–2013.  
- **Linha 1 (KPIs + deltas):** “foto” → crescimento em Receita/Pedidos, trade-off no Ticket Médio, Margem preservada.  
- **Linha 2 (Receita mensal + Rolling 12M):** evolução ao longo do tempo, destacando o salto de 2013.  
- **Linha 3a (Receita por país):** concentração geográfica → Austrália e EUA em 2011, expansão em 2013.  
- **Linha 3b (Pedidos % por categoria):** mudança de mix → de 100% Bikes para inclusão de Acessórios/Roupas.  
👉 Fecha a narrativa executiva: **crescimento forte + expansão geográfica + diversificação de portfólio + margens preservadas**.  

---

### Página 2 – Produtos & Margem  
**Missão:** mostrar como o portfólio evoluiu em profundidade (subcategorias) e o impacto em margem e representatividade.  
- **Linha 1 (KPIs por categoria):** visão agregada da categoria selecionada → Receita, Pedidos, Margem Bruta %.  
- **Linha 2 (Top subcategorias):** composição interna → quem puxa a categoria em valor e % relativo.  
- **Linha 3 (Scatter subcategorias):** Sales × Margin% → distingue produtos campeões de volume/rentabilidade dos que reduzem a margem.  
👉 Fecha a narrativa de produto: **do foco em poucas bikes premium para um mix amplo, com diversificação trazendo volume, mas também desafios de rentabilidade**.  

---

### Página 3 – Clientes & Geografia  
**Missão:** mostrar como a base de clientes cresceu, se diversificou geograficamente e como evoluiu o perfil de consumo.  
- **Linha 1 (cards de clientes e retenção):** quantos clientes ativos, quantos novos, quantos retornam, quantos pedidos/cliente.  
- **Linha 2 (Receita por país ao longo dos anos):** evolução geográfica → de Austrália/EUA para maior peso da Europa e Canadá.  
- **Linha 3 (perfil demográfico):** gênero e estado civil → retrato simples do público atendido.  
👉 Fecha a narrativa de clientes: **não só mais volume, mas novos mercados e diversidade no perfil demográfico**.  

---

### Página 4 – Tempo & KPIs Avançados  
**Missão:** oferecer leitura temporal mais profunda, com tendências, variações anuais e padrões sazonais.  
- **Linha 1 (KPIs YoY):** visão de variação → Receita e Pedidos disparam, Ticket Médio cai, Margem preservada.  
- **Linha 2 (Receita acumulada YTD):** ritmo de crescimento dentro do ano → curva de 2013 dispara cedo e supera totais anteriores.  
- **Linha 3 (Heatmap de sazonalidade):** 2011–2012 com picos concentrados vs. 2013 mais equilibrado.  
👉 Fecha a narrativa temporal: **o negócio deixou de depender de eventos pontuais e entrou em ritmo de escala consistente, mantendo margens mesmo com ticket menor**.  

---

## 🎨 Estilo e Data-Ink Ratio

- **Cores:** consistência entre páginas; heatmap com escala própria (laranja) para diferenciar função analítica.  
- **Simplicidade:** evitados visuais redundantes ou de baixa densidade.  
- **Títulos dinâmicos:** adaptam-se ao filtro (ex.: “Clientes & Geografia – United States”).  
- **Página Executiva fixa:** sem slicers para garantir comparabilidade.  

---

## 📌 Conclusão

Cada decisão buscou equilibrar:  
- **Consistência temporal** (anos completos, 2011–2013).  
- **Clareza analítica** (KPIs comparáveis, foco no que importa).  
- **História de negócio** (de boutique premium → operação diversificada e internacional).  
- **Boas práticas de visualização** (data-to-ink ratio, clareza nos filtros, narrativa em linhas por página).  
