# Explorar um índice de pesquisa do Azure AI 

Para a resolução deste projeto segui o tutorial do laboratório 04 [Explore an Azure AI Search index (UI)](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/11-ai-search.html), seguindo os passos abaixo:

# 1. Criar um resource Azure AI Search

1. Abrir o [portal Azure](https://portal.azure.com/)
   
2. Criar um novo resource to tipo `Azure AI Search` com as seguintes configurações:
   
![](https://github.com/CarlaAlves887/ai-search-lab/blob/main/images/Imagem1.png)

![](https://github.com/CarlaAlves887/ai-search-lab/blob/main/images/Imagem2.png)

# 2. Criar um resource Azure AI Services
   
1. Criar um novo resource to tipo `Azure AI Services` com as seguintes configurações:
   
![](https://github.com/CarlaAlves887/ai-search-lab/blob/main/images/Imagem3.png)

# 3. Criar uma Storage Account
   
1. Voltar para a Home page e escolher a opção `Storage accounts`
   
![](https://github.com/CarlaAlves887/ai-search-lab/blob/main/images/Imagem4.png)

2. Selecionar `Create` para criar uma storage account:

   ![](https://github.com/CarlaAlves887/ai-search-lab/blob/main/images/Imagem5.png)

3. Criar a storage account com as seguintes configurações:

   ![](https://github.com/CarlaAlves887/ai-search-lab/blob/main/images/Imagem6.png)

4. Após a criação do storage account, no menu lateral à esquerda expande a secção `Settings`, seleciona a opção `Configuration`, altera a configuração `Allow Blob anonymous access` de *Disabled* para *Enabled* e guarda as alterações

   ![](https://github.com/CarlaAlves887/ai-search-lab/blob/main/images/Imagem7.png)

# 4. Upload de documentos no Azure Storage

1. No menu lateral à esquerda, expandir a secção `Data storage`, selecionar a opção `Containers`, clicar em `+ Add container`, definir as seguintes configurações e clicar `Create`

   ![](https://github.com/CarlaAlves887/ai-search-lab/blob/main/images/Imagem8.png)

2. Selecione o container criado e faça upload dos [documentos](https://github.com/CarlaAlves887/ai-search-lab/tree/main/docs)

   ![](https://github.com/CarlaAlves887/ai-search-lab/blob/main/images/Imagem9.png)

# 5. Indexar os documentos

1. Volte para o resource Azure AI Search que foi criado e selecione a opção `Import data`

   ![](https://github.com/CarlaAlves887/ai-search-lab/blob/main/images/Imagem10.png)

2. Na tab `Connect to your data`, na lista `Data Source`, selecione a opção `Azure Blob Storage` e complete os detalhes com os seguintes valores:

   - **Data Source:** Azure Blob Storage
   - **Data source name:** coffee-customer-data
   - **Data to extract:** Content and metadata
   - **Parsing mode:** Default
   - **Subscription:** A sua subscrição
   - **Connection string:** *Selecione `Choose an existing connection`. Selecione a sua storage account, selecione o container `coffee-reviews`, e depois clique `Select`.*
   - **Managed identity authentication:** None
   - **Container name:** Esta configuração é preenchida automaticamente quando é escolhida uma conexão existente
   - **Blob folder:** Empty
   - **Parsing mode:** Default
   - **Description:** Avaliações das cafeterias Fourth Coffee.
    ![](https://github.com/CarlaAlves887/ai-search-lab/blob/main/images/Imagem11.png)

3. Click `Next: Add cognitive skills (Optional)`

4. A secção `Attach AI Services` deve ser a seguinte:

   ![](https://github.com/CarlaAlves887/ai-search-lab/blob/main/images/Imagem12.png)

5. Na secção `Add enrichments` deve alterar de acordo com a imagem abaixo:

   ![](https://github.com/CarlaAlves887/ai-search-lab/blob/main/images/Imagem13.png)

6. Na secção `Save enrichments to a knowledge store` deve alterar de acordo com a imagem abaixo:

   ![](https://github.com/CarlaAlves887/ai-search-lab/blob/main/images/Imagem14.png) 

7. Selecione `Next: Customize target index`, altere o `Index name` para *coffee-index*, garanta que os dados são os seguintes e clique em `Next: Create an indexer` no final:
   
   ![](https://github.com/CarlaAlves887/ai-search-lab/blob/main/images/Imagem15.png) 

9. Altere o `Indexer Name` para *coffee-indexer* e clique `Submit`

    ![](https://github.com/CarlaAlves887/ai-search-lab/blob/main/images/Imagem16.png)

10. No menu lateral à esquerda, expanda a secção `Search management` e selecione a opção `Indexers`
    
    ![](https://github.com/CarlaAlves887/ai-search-lab/blob/main/images/Imagem17.png)

11. Selecione o `coffee-indexer` para ver os detalhes

    ![](https://github.com/CarlaAlves887/ai-search-lab/blob/main/images/Imagem18.png)

# 6. Consultar o índice

1. Abra a `Overview` page do seu serviço de pesquisa e selecione a opção `Search explorer`

    ![](https://github.com/CarlaAlves887/ai-search-lab/blob/main/images/Imagem19.png)

2. Altere para `JSON view`, execute os seguintes testes e verifique os resultados

   ![](https://github.com/CarlaAlves887/ai-search-lab/blob/main/images/Imagem20.png)

   ![](https://github.com/CarlaAlves887/ai-search-lab/blob/main/images/Imagem21.png)




