
# Explorando o Azure AI Search Index (UI)

Neste Artigo, vou mostrar um pouco de como foi usar o Azure AI Search Index para configurar uma pesquisa baseada em dados fornecidos. Vou buscar passar um pouco dessa atividade para voces, os insights e possibilidades com essa ferramenta incrivel do Azure. Deixarei no final do artigo o link da documentação oficial dessa atividade, disponibilizado pela Microsoft Learning.

## Criando recursos
Para essa atividade, é necessario três recursos do Azure: o Azure AI Search, Azure AI services, e Azure storage accoun. Vou procurar explicar como cria-los tambem ao longo desse artigo.

# Azure AI Search
Para criar um recurso de pesquisa, no [Portal Azure](https://portal.azure.com/#home), selecione a opção de criar um recurso, e na barra de pesquisa procure por Azure AI Search, e clique em criar.
print
print
Deixe as configurações da seguinte maneira (importante deixar a camada de preços como **basico**), e caso não tenha um grupo de recursos, basta clica na opção de criar um novo, é bem simples. Após as configurações, clique em **Revisar + criar**, e após a validação clique em **criar** na tela que se abrir.
print

# Serviços Cognitivos (Azure AI Services)
Para criar este recurso, selecione a opção criar um recurso, vá na categoria **IA + Machine Learning**, e clique em criar do serviço **Serviços Cognitivos**.
print
print
Configure os detalhes e no campo **Tipo de preço**, selecione **Standard SO**, e marque a caixa de termos.
print
print

# Azure Storage Account
Para criar o recurso de armazenamento, na Home do portal Azure, selecione a opção **Contas de armazenamento** e clique em criar. 
print
Prrencha as configurações. Importante: Em desempenho, selecione **Standard**, e **Redundância**, selecione **LRS(Armazenamento com redundância local)**, e depois clique em **Revisar + criar**.
print
print
Após finalizar essa etapa, volte na home do portal Azure, e clique no serviço de armazenamento que voce criou, e vá na aba configuração, do menu configurações, que fica a esquerda da pagina, e deixe habilitado a opção **Permitir acesso anônimo ao Blob**.
print
print

Feito isso, va no menu a esuqerda **Armazenamento de dados**, e clique na opção **Contêineres**. Cique na opção **+ Contêiner**. Ao fazer isso, abrirá uma tela, na qual voce **precisa** dar o nome do contêiner como **coffeereviews**, e na opção **nivel de acesso anônimo**, selecionar **Contêiner(Acesso de leitura anônimo para contêineres e blobs)*, e clique em **Criar**. Depois de criado, ele deverá aparecer na lista ao clicar novamente no menu Contêineres da aba de armazenamento de dados.
print
print
print

# Usando o recurso AI Search
Na pagina inicial do protal Azure, selecione o serviço de armazenamento criado anteriormente, e vá no menu **Contêineres**, e selecione o contêiner criado anteriormente, e clique no menu carregar,e faça uploado de arquivos de exemplo, vamos usar de exemplo arquivos de avaliação de cafés, baixe eles aqui, descompacte a pasta no seu computador e faça upload dos arquivos.
print
print
print

Após isso, volte da na home do portal, e selecione o serviço de pesquisa criado anteriormente.
print
print
Em fonte de dados, selecione **Armazenamento de blob do Azure**,e deixe as configurações conforme imagem abaixo. Caso na opção Cadeia de conexão aponte que esta vazia, selecione a opção **Escolher uma conexão existente**, tera uma opção para voce lá.
print
No menu de **Adicionar enriquecimentos**, deixe as configurações assim conforme imagens abaixo:
print
print
No menu **Salvar os enriquecimentos em um repositório de conhecimento**, deixe as seguinets opções marcadas conforme imagem, e escolha uma conexão existente caso venha sem nada preenchido.
print
No menu de **configuração de indicesde destino**, deixe as informações conforme imagem abaixo.
print
No ultimo menu, a ntes de clicar en **Enviar**, abra o menu **Opções aavançadas**, e deixe marcado a opção **Chaves de codificação de base 64**, após isso, pode clicar em Enviar.
print
Feito isso, volte para a pagina inicial do serviço de pesquisa cognitiva, vá na opção **Indexadores**, do menu **Gerenciamento de pesquisa**, selecione o indexador criado e veja se esta com êxito.
print
print
Verificado isso, va na opção **Gerenciador de pesquisa**, do menu **Visão geral**, vamos testar de fato o serviço de pesquisa. Seleione o índice criado e na opção Exibir, selecione **Exibição JSON**.
print
print
No campo do editor de consultas JSON , copie e cole:
{
    "search": "*",
    "count": true
}
Selecione Pesquisar . A consulta de pesquisa retorna todos os documentos no índice de pesquisa, incluindo uma contagem de todos os documentos no campo @odata.count . O índice de pesquisa deve retornar um documento JSON contendo os resultados da pesquisa.
print
print
Agora vamos filtrar por localização. No campo do editor de consultas JSON , copie e cole:
{
 "search": "locations:'Chicago'",
 "count": true
}
Selecione Pesquisar . A consulta pesquisa todos os documentos no índice e filtra revisões com localização em Chicago. Você deveria ver 3 no campo @odata.count.
print
print


# Conclusão
Essa foi a atividade mais complexa que tive até o momento para testar recursos do Azure, no qual estou buscando conhecimento para a certificação **Microsoft Azure AI900**, mas tambem foi a atividade mais legal, e que me mostrou mais horizontes do que pode ser feito com esse recurso de pesquisa. Pense se cada empresa que voce frequenta, trablha, possui, etc, tivesse um recurso desses, no qual voce armazenaria as avaliações de serviços por exemplo, e poderia fazer uma pesquisa depois, seja por palavra-chave, localização, ou até mesmo por extração de sentimentos de texto, outro recurso muito legal que tem no Azure, as possibilidades são muitas para uso do Azure AI Search, esse recurso muito interessante do Azure.

# Excluindo grupo de recurso
Pode parecer algo sem importancia, mas é recomendado que após não utilizar mais os recursos, voce excluir o grupo de recursos, para que o mesmo não consuma créditos da sua conta ou até mesmo gere gastos, caso voce não esteja mais no período gratuito de testes e ja tenha usado os 200 dólares concedidos ao criar uma conta nova. Então deixei aqui tambem um resumo de como excluir um grupo de recursos.


# Saiba mais
[Explore o Azure AI Search (UI)](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/11-ai-search.html)








