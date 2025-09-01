# 📊 Projeto Power BI – Análise de Vendas a partir da Camada Gold

Este projeto complementa o [🏢 projeto-sql-data-warehouse](https://github.com/vivi-alencar/projeto-sql-data-warehouse), demonstrando como a **Camada Gold** pode ser transformada em **dashboards no Power BI** para análise de vendas e suporte à tomada de decisão.

---

## 🎯 Objetivo

Explorar dados modelados em **esquema estrela (fatos e dimensões)** e traduzi-los em **indicadores de negócio** claros, através de visualizações interativas.

---

## 🏗️ Arquitetura de Páginas do Dashboard

O dashboard está organizado em quatro páginas principais:

1. **Executiva (v1 concluída ✅)**  
   - KPIs principais: Receita, Margem Bruta %, Pedidos, Crescimento YoY  
   - Linha de vendas mensal + Rolling 12M  
   - Top 5 produtos por receita  
   - Receita por país (overview)  
   - Slicers: Ano, Categoria  

2. **Produtos & Margem (em desenvolvimento 🚧)**  
   - *(Placeholder – visuais e prints serão adicionados em breve)*  

3. **Clientes & Geografia (planejado 📝)**  
   - *(Placeholder – página planejada, ainda não implementada)*  

4. **Tempo & KPIs Avançados (planejado 📝)**  
   - *(Placeholder – página planejada, ainda não implementada)*  

---

## 📂 Estrutura do Repositório

- **sales_analytics.pbix** → arquivo principal do Power BI  
- **/screenshots/** → capturas de tela das páginas do dashboard
- - **/documentacao/** → explicações complementares
  - `decisoes.md` → motivações por trás de escolhas de design e modelagem (ex.: exclusão de anos, categorias)  
  - `findings.md` → insights e descobertas do negócio a partir dos dados (evolução de produtos, ticket médio, etc.)  
- **README.md** → este documento  
- **LICENSE** → licença MIT  

---

## 📷 Capturas de Tela

*(Placeholder – capturas de tela serão adicionadas à medida que as páginas ficarem prontas)*

### Página Executiva
![executive](./screenshots/page1_executive.png)

---

## 🔗 Conexão com o Data Warehouse

Este projeto utiliza como fonte a **Camada Gold** modelada no repositório:  
👉 [projeto-sql-data-warehouse](https://github.com/vivi-alencar/projeto-sql-data-warehouse)

---

## ⚡ Como Abrir

1. Clone este repositório:
   ```bash
   git clone https://github.com/seu-usuario/projeto-powerbi-data-warehouse.git
   ```
2. Abra o arquivo `sales_analytics.pbix` no **Power BI Desktop (versão 2.146.1133.0 ou superior)**.  
3. Certifique-se de ter acesso ao banco ou dados exportados da **Camada Gold**.

---

## 📌 Roadmap

- [x] Página 1 – Executiva  
- [ ] Página 2 – Produtos & Margem (🚧 em andamento)  
- [ ] Página 3 – Clientes & Geografia (📝 planejada)  
- [ ] Página 4 – Tempo & KPIs Avançados (📝 planejada)  

---

## 📎 Créditos

Este dashboard foi construído a partir do modelo de DW inspirado no projeto *SQL Data Warehouse* criado por **Baraa Khatib Salkini**.  
Conteúdo original em:  
🔗 [https://www.datawithbaraa.com](https://www.datawithbaraa.com)  
Licenciado sob a **Licença MIT**.

---

## 📜 Licença

Este projeto é disponibilizado sob a licença **MIT**.  
Consulte o arquivo [LICENSE](LICENSE) para mais detalhes.

