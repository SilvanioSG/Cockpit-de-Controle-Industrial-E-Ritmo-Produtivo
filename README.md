# Cockpit de Controle Industrial & Ritmo Produtivo (CCIRP)

> **Autor:** Silvanio Gois — Gestor de Operações e Negócios Orientado a Dados
>
> **Contatos Profissionais:** [Website Oficial](https://www.silvaniogois.com.br?utm_source=gemini) | [LinkedIn](https://www.linkedin.com/in/silvanio-gois/?utm_source=gemini) | [GitHub](https://github.com/SilvanioSG?utm_source=gemini) | **E-mail:** sg@silvaniogois.com.br
>
> **Demonstração Online:** [Acessar Relatório no Power BI Service](https://app.powerbi.com/view?r=eyJrIjoiM2RkOTc2NGMtMGEzYy00OWFmLTkxZGMtMzNmYWIwZjFlMzE5IiwidCI6IjJlYmQyYzU0LWY1ZDMtNGVmYi05ZGE3LWU4Yzk0YmQyMWQzOSJ9&utm_source=gemini)

## 1. Visão Geral do Projeto

O **Cockpit de Controle Industrial & Ritmo Produtivo (CCIRP)** é uma solução analítica avançada desenvolvida para o Planejamento e Controle da Produção (PCP). A aplicação consolida dados transacionais extraídos da base corporativa `RitmoProdutivo.xlsx`, transformando-os em inteligência acionável de suporte à decisão executiva e operacional.

O objetivo central é monitorar em tempo real os principais indicadores de eficiência fabril (KPIs), cruzando o planejado versus realizado, taxas de OEE, perdas por refugo e o alinhamento com a demanda comercial para reuniões de *Daily/S&OP*.

## 2. Metodologia Técnica e Arquitetura de Dados

O projeto foi estruturado seguindo as melhores práticas de engenharia de Business Intelligence e modelagem dimensional:

* **Modelagem de Dados (Star Schema):** Implementação de uma arquitetura centralizada unindo tabelas de fatos de produção a dimensões estruturadas, complementada por uma **Tabela Calendário** dedicada para suporte completo a operações de *Time Intelligence*.

* **Tratamento e ETL (Power Query):** Limpeza, tipagem, consolidação de fontes e tratamento de inconsistências de registros fabris volumosos para garantir a integridade relacional.

* **Modelagem DAX (Cálculo Padrão):** Desenvolvimento de medidas analíticas estruturadas com expressões lógicas diretas e agregação contextuais para o cálculo dos pilares fundamentais do OEE:
  
  $$
  OEE = Disponibilidade \times Desempenho \times Qualidade
  $$

* **UI/UX Industrial (Clean Design):** Interface projetada para ambientes corporativos e de chão de fábrica, com paletas de cores de alto contraste focadas na identificação rápida de anomalias (paradas de máquinas e índices de refugo).

## 3. Estrutura do Relatório e Navegação de Páginas

O relatório está distribuído em uma narrativa sequencial dividida em 5 seções principais:

### Página 0: Capa / Início
* **Objetivo:** Introdução executiva ao projeto, alinhamento de escopo, definições conceituais e sumário interativo para navegação no cockpit.

### Página 1: Visão Executiva (Cockpit Gerencial)
* **Objetivo:** Oferecer um panorama rápido e consolidado do desempenho global da fábrica para a diretoria, respondendo ao alinhamento de metas de volume e eficiência.
* **Métricas Principais:** 
  * `% OEE`: $56,57\%$
  * `% Produtividade`: $68,79\%$
  * `% Qualidade`: $89,62\%$
  * `% Disponibilidade`: $91,76\%$
  * **Composição de Horas:** Horas Disponíveis ($92,39\%$) vs. Horas Paradas ($7,61\%$).

### Página 2: Desempenho de Produção e Ritmo (Foco Operacional)
* **Objetivo:** Analisar o ritmo produtivo por linha ou equipamento, medindo desvios de capacidade e aderência ao plano de produção.
* **Métricas Principais:** 
  * `Qtd Produzida Total`: $54.123.698,00$ vs. `Qtd Planejada Total`: $78.680.000,00$.
  * Tabela analítica detalhada por linha (Linha A à Linha E) contendo volume planejado, produzido, refugado, percentual de produtividade e horas paradas.

### Página 3: Qualidade, Perdas e OEE (Deep Dive)
* **Objetivo:** Investigar as perdas fabris, focando estritamente na qualidade dos produtos (refugos) e nas paradas de máquinas que reduzem o OEE global.
* **Métricas Principais:** 
  * `Qtd Refugada Total`: $6.269.263,00$.
  * Análise cruzada de produção vs. refugo por linha e por operador, destacando o ranking de horas paradas por operador e por equipamento.

### Página 4: Alinhamento de Demanda e Comercial (Supply vs. Demand)
* **Objetivo:** Garantir que o ritmo produtivo da fábrica esteja em perfeita sincronia com as vendas e compromissos comerciais, mitigando riscos de rupturas de entrega ou superávits de estoque.
* **Métricas Principais:** 
  * `Quantidade Vendida`: $65.324.685,78$
  * `Quantidade Produzida`: $54.123.698,00$
  * `Cobertura Comercial (Saldo / Déficit)`: $-11.200.987,78$ (evidenciando gargalo de suprimento frente à demanda comercial).

## 4. Análise Crítica e Insights Estratégicos

1. **Lacuna de OEE e Desempenho:** Embora a Disponibilidade mecânica opere em patamares excelentes ($91,76\%$), o OEE consolidado atinge $56,57\%$. Isso decorre do baixo índice de Desempenho / Produtividade ($68,79\%$), indicando que os equipamentos operam com alta frequência, mas abaixo da cadência nominal de velocidade ou sofrem microparadas recorrentes.
2. **Déficit Comercial (Supply Gap):** O comparativo entre a quantidade produzida ($54,12\text{M}$) e a quantidade comercializada ($65,32\text{M}$) revela um déficit de mais de $11,2\text{ milhões$ de unidades, demonstrando a necessidade urgente de revisão da capacidade produtiva ou redimensionamento do plano de suprimentos.
3. **Impacto de Qualidade:** Com um volume de refugos superior a $6,2\text{ milhões}$ de peças e uma taxa de qualidade de $89,62\%$, há perdas significativas de matéria-prima e capacidade fabril passíveis de recuperação através de programas de melhoria contínua (Lean Manufacturing).

## 5. Estrutura de Arquivos do Repositório

* `RitmoProdutivo.xlsx`: Base de dados transacional em Excel utilizada como fonte.
* `RitmoProdutivo.pbix`: Arquivo de projeto do Power BI contendo modelo de dados, relações e layouts.
* `RitmoProdutivo.pdf`: Relatório executivo compilado em PDF.
* `pagina0` a `pagina4`: Mapeamento e estruturação visual das telas que compõem o dashboard.

## 6. Licença

Este projeto é desenvolvido para fins de demonstração de competência sênior em gestão de operações, PCP e arquitetura de Business Intelligence. Todos os direitos reservados ao autor.