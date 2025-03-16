
# 📌 Monitoramento de Preços de Café e Ovos com PySpark e AWS Glue

## 📍 Descrição Geral
Este projeto tem como objetivo monitorar os preços de café e ovos em tempo real na plataforma Mercado Livre, utilizando AWS Glue Studio para processar dados com PySpark. Os preços coletados serão armazenados no AWS S3 e no DynamoDB, permitindo a análise de tendências e variações ao longo do tempo.
Além disso, será feita a verificação dos vendedores, permitindo identificar padrões de preço por vendedor. A solução permite que usuários acompanhem mudanças nos preços, identifiquem oportunidades de compra/venda e recebam insights sobre produtos populares.


## 🎯 Objetivos do Projeto
✔️ Coletar e processar dados de preços de café e ovos do Mercado Livre em tempo real.  
✔️ Armazenar os preços históricos no AWS S3 para análise futura.  
✔️ Salvar os preços mais recentes no DynamoDB para acesso rápido.  
✔️ Criar um dashboard interativo para visualizar as tendências de preços.  
✔️ Permitir análise e consultas nos dados usando AWS Athena + Spark SQL.  

## 📌 Arquitetura do Projeto

### 1️⃣ Ingestão de Dados
Um job PySpark no AWS Glue Studio fará chamadas periódicas à API do Mercado Livre.  
Os dados coletados serão armazenados em um bucket no AWS S3.  
As informações mais recentes serão inseridas no AWS DynamoDB para acesso rápido.

### 2️⃣ Processamento e Análise
O AWS Glue usará Spark Structured Streaming para processar os dados.  
Os preços serão analisados para identificar variações, tendências e padrões.  
AWS Athena permitirá consultas SQL nos dados armazenados no S3.

### 3️⃣ Armazenamento
- **AWS S3** → Para armazenar os dados históricos de preços.  
- **AWS DynamoDB** → Para manter uma base de preços sempre atualizada.

### 4️⃣ Visualização e Insights
Criar um dashboard interativo com Streamlit para exibir:
- Histórico de preços dos produtos.
- Variações de preço em tempo real.
- Comparação entre produtos semelhantes.
AWS QuickSight ou Grafana podem ser usados para criar relatórios e gráficos mais avançados.

## 📌 Tecnologias Utilizadas
- **PySpark (Spark Structured Streaming)** → Para coletar e processar os dados.  
- **AWS Glue Studio** → Para gerenciar e executar jobs PySpark.  
- **AWS S3** → Para armazenar os dados coletados em formato JSON/Parquet.  
- **AWS DynamoDB** → Para armazenar os preços mais recentes.  
- **API do Mercado Livre** → Para obter os dados dos produtos.  
- **AWS Athena + Spark SQL** → Para consultas analíticas sobre os preços.  
- **Streamlit / AWS QuickSight** → Para visualização dos dados.

## 📌 Fluxo de Funcionamento
1️⃣ AWS Glue Job (PySpark) consulta a API do Mercado Livre periodicamente.  
2️⃣ Os dados são processados e salvos no S3 e no DynamoDB.  
3️⃣ Spark Structured Streaming analisa os preços em tempo real.  
4️⃣ AWS Athena permite consultas sobre os preços históricos.  
5️⃣ Dashboard (Streamlit/QuickSight) exibe gráficos com variações de preço.

## 📌 Funcionalidades Principais
✔️ Coleta de dados em tempo real da API do Mercado Livre.  
✔️ Armazenamento de histórico de preços no S3 para análise.  
✔️ Monitoramento de variação de preços e alertas para mudanças significativas.  
✔️ Análise de tendências para identificar produtos que estão subindo ou caindo de preço.  
✔️ Dashboard interativo para acompanhar os preços e insights de mercado.

## 📌 Como Executar o Projeto?

### 1️⃣ Criar o Job no AWS Glue Studio
- Acesse o AWS Glue Studio na AWS.
- Clique em "Criar job" → Escolha "Código Python".
- Escolha um IAM Role com permissões para acessar S3 e DynamoDB.
- Escolha um S3 bucket para armazenar logs e outputs.
- Copie e cole o código PySpark no editor do Glue.
- Salve e execute o job.

### 2️⃣ Monitorar os Dados
- Verifique os arquivos JSON no AWS S3.
- Consulte os dados recentes no DynamoDB.
- Utilize o AWS Athena para rodar queries SQL.

### 3️⃣ Criar um Dashboard
- Utilize Streamlit para criar um painel interativo.
- Ou configure o AWS QuickSight para gerar relatórios visuais.

## 📌 Benefícios do Projeto
🚀 **Automatização total** → Dados coletados e analisados sem intervenção manual.  
📊 **Análises estratégicas** → Empresas podem prever tendências de preços.  
⚡ **Escalabilidade** → Pode ser aplicado a qualquer marketplace ou e-commerce.  
💡 **Insights acionáveis** → Permite identificar oportunidades de compra e venda rapidamente.

## 📌 Próximos Passos
🔹 Configurar AWS Glue e criar o job PySpark para coletar os dados da API.  
🔹 Armazenar os dados no S3 e DynamoDB para processamento contínuo.  
🔹 Criar consultas no AWS Athena para análise dos preços.  
🔹 Construir um dashboard interativo para visualização dos dados.

✉️ **Contato**: Caso tenha dúvidas ou sugestões, fique à vontade para contribuir! 🚀
