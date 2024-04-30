# MS_Azure_AI900_DIO_Azure_Cognitive_Search
 _Projeto realizado para a Certificação IA900 oferecida pela Microsoft em parceria com a DIO - Digital Innovation One_

---
## O Azure Cognitive Search

O _Azure Cognitive Search_ ou _Azure AI Search_ é uma ferramenta que compõe o conjunto de serviços de AI e Machine Learning do Azure. Ele não é apenas uma ferramenta de pesquisa, mas oferece recuperação segura de informações em escala, como catálogos e/ou documentos em bancos de dados, através de vetores e indexadores. Além disso, o _Azure AI Search_ integra-se com outros serviços do Azure.

---
## Criando um _Resource_ do _AI Search_
---
Na pagina inicial do Azure, clique em _Create a resource_. 

<img src="Prints/Img01.png" width="700" height="600">

Na nova página, no canto esquerdo clique em _AI + MAchine Learning_ e selecione o _AI Search_.

<img src="Prints/Img02.png" width="1200" height="800">

Em seguida, clique em _Create_ no canto superior esquerdo. 

<img src="Prints/Img03.png" width="1200" height="800">

O Azure solicita que você preencha alguns dados, como o _Subscription_,  _Resource group_, _Region_. Em _Princint tier_, clique em _Change Pricing Tier_.

<img src="Prints/Img04.png" width="800" height="600">

Selecione o _Basic_.

<img src="Prints/Img05.png" width="1000" height="800">

Dê um nome ao seu _service name_ (no meu exemplo, 'labcognitivesearch') E não esqueça de marcar a _checkbox_, onde você concorda com os termos do Azure AI Services. Por fim, clique em _Review + create_.

<img src="Prints/Img06.png" width="700" height="600">

Por fim, clique em _Create_.

<img src="Prints/Img07.png" width="700" height="600">

Aguarde aparecer a mensagem _Your deployment is complete_. Quando ele estiver concluído, vá em _Go to resource_.

<img src="Prints/Img08.png" width="700" height="700">

Pronto! Seu _resource_ está criado, agora vá na barra superior do canto esquerdo e clique em _Home_, pois é necessário criar outro _resource_.

<img src="Prints/Img09.png" width="1300" height="300">

---
## Criando um _Resource_ do _AI Services_
---
Para construir nossa ferramenta de pesquisa, além do recurso do _AI Search_, por isso é necessário criar um recurso no _AI Services_, já que a ferramenta de pesquisa deve se basear em serviço de AI, como por exemplo, busca de padrões em imagens(utilza-se o _Vision_), ou ler e compreender textos (utilza-se o _Leitor Imersivo_), ou que detecte e identifique pessoas e emoções em imagens (utilza-se o _Face_), entre outros.

Na nova página, no canto esquerdo clique em _AI + MAchine Learning_ e selecione o _Azure AI Services_.

<img src="Prints/Img10.png" width="1400" height="600">

O Azure solicita que você preencha alguns dados, como o _Subscription_,  _Resource group_, _Region_. Além disso, você criar um nome para seu recurso (no meu exemplo, _LabPesquisaIA_).

<img src="Prints/Img11.png" width="1000" height="890">

Em _Princint tier_, selecione o _Standard SO_. E não esqueça de marcar a _checkbox_, onde você concorda com os termos do Azure AI Services. Por fim, clique em _Review + create_.

<img src="Prints/Img12.png" width="900" height="890">

Clique em _Create_ e aguarde.

<img src="Prints/Img13.png" width="900" height="890">

Aguarde aparecer a mensagem _Your deployment is complete_.

<img src="Prints/Img14.png" width="1000" height="390">

---
## Criando uma Conta para Armazenamento e configurando-a 
---

Voltamos novamente para a página inicial do Azure, através de _Home_. Agora é necessário criar e configurar uma _Storage Accounts_ para armazenar os documentos e/ou banco de dados que serão a base da pesquisa.

<img src="Prints/Img15.png" width="1000" height="230">

Na pagina inicial, clique em _Storage Accounts_.

<img src="Prints/Img16.png" width="1400" height="220">

Clique em _Create_.

<img src="Prints/Img17.png" width="900" height="490">

O Azure solicita que você preencha alguns dados, como o _Subscription_,  _Resource group_, _Region_. Além disso, você criar um nome para o _Storage account name_ (no meu exemplo, _iapesquisacognitive_). 

<img src="Prints/Img18.png" width="990" height="890">

Em _Redundancy_, selecione o _LRS - Locally-redundant storage_.

<img src="Prints/Img19.png" width="970" height="890">

Clique em _Review + create_ e por fim em _Create_.

<img src="Prints/Img20.png" width="940" height="860">

Aguarde aparecer a mensagem _Your deployment is complete_. Após isso, clique em _Go to resource_.

<img src="Prints/Img21.png" width="900" height="600">

Agora, vamos configurar nosso recurso.

<img src="Prints/Img22.png" width="1750" height="590">

No menu lateral esquerdo, na aba _Settings_, clique em _Configuration_.

<img src="Prints/Img23.png" width="340" height="230">

Na opção _Allow Blob anonymous access_ e clique em _Enabled_.Depois clique em _Save_.

<img src="Prints/Img24.png" width="1350" height="670">

---
## Upload dos arquivos
---

No menu lateral esquerdo, na aba _Data storage_, clique em _Containers_.

<img src="Prints/Img25.png" width="320" height="220">

Clique em _+ Container_ para criar um novo.

<img src="Prints/Img26.png" width="920" height="390">

Crie um nome para seu _container_ (como regra, o nome deve ter todas as letras minúsculas, sem caracteres especiais e sem espaços). Em _Anonymous access level_ escolha _read access for containers and blobs_ (para liberar essa opção, a ação interior de permitir ao _Blob_ acesso é necessária). Por fim, cliqye em _Create_.

<img src="Prints/Img27.png" width="540" height="820">

Voltando para a página inicial dos _Containers_, veja se o _container_ criado aparece. Clique nele.

<img src="Prints/Img28.png" width="690" height="490">

Vá em _Upload_.

<img src="Prints/Img29.png" width="1000" height="530">

Selecione os documentos ou base de dados para a pesquisa.

<img src="Prints/Img30.png" width="340" height="240">

---
## Configurando a pesquisa da 32 a 53
---

Volte para a _home_.

<img src="Prints/Img32.png" width="290" height="240">

Acesse o _Azure AI services_ e selecione o recurso criado (no meu exemplo é _labcognitivesearch_).

<img src="Prints/Img33.png" width="1340" height="440">

Selecione o _Import data_.

<img src="Prints/Img34.png" width="1320" height="280">

Os documentos estão na conta criada no _Blob Storage_, então selecionamos o _Azure Blob Storage_.

<img src="Prints/Img35.png" width="910" height="800">

Uma guia lateral é aberta, com as opções de _Containers_, escolhemos o que queremos utilizar na pesquisa (no meu exemplo é _coffeereviews_).

<img src="Prints/Img36.png" width="930" height="440">

O momento de importar é o momento de indexação dos dados, mas antes é necessário informar o _Data Source_, o _Data Source name_, quais dados serão extraídos (_Content and metadata_), _Parsing Mode_ (é recomendável o _default_), além da _Subscription_ e em _Connection string_, selecionamos a _storage account_ e o container _coffee-reviews_.

<img src="Prints/Img37.png" width="910" height="880">

Agora, vamos 'enriquecer' nossa ferramenta de pesquisa com os dados. Então crio um nome para o _skillset_ (no meu exemplo, coffee-slillset) e ativamos o serviço de AI _OCR_ (Optical Character Recognition) que utilizaremos. Além disso, em Ensure that the _Source data field_ selecione _merged content_ e em _Enrichment granularity level_ selecione _Pages (5000 character chunks)_.

<img src="Prints/Img38.png" width="790" height="470">

Escolhemos os parâmetros de nossa ferramenta de pesquisa. Temos que selecionar quais _Text Cognitive Skills_ iremos utilizar em coluna.

<img src="Prints/Img39.png" width="1380" height="570">

É necessário conectar com a _Storage Account_. Selecione a _Storage Account_ criada anteirormente.

<img src="Prints/Img40.png" width="967" height="380">

Acesse _container_ criado. 

<img src="Prints/Img41.png" width="570" height="430">

Crie um novo _container_ para armazenar dados da pesquisa, com _Anonymous Access Level_ _Private_. Por fim, clique em _Create_.

<img src="Prints/Img42.png" width="360" height="820">

Aqui configuramos o _container_ recém criado. O Azure irá buscar por páginas, _key phrases_, entidades, detalhes de imagens e referências.

<img src="Prints/Img43.png" width="470" height="400">

Agora é o momento da indexação. Mude o somente o nome, em _Key_ mantenha o _metadata storage path_ e o _Suggester name_ em branco.

<img src="Prints/Img44.png" width="1460" height="430">

Faça uma revisão nos campos selecionados e marque a checkbox _filterable_ para todos os campos selecionados.

<img src="Prints/Img45.png" width="1270" height="480">

Dê um nome ao seu Index e selecione _Once_ em _Schedule_.

<img src="Prints/Img46.png" width="1000" height="530">

Expanda as opções avançadas e marque a checkbox _Base-64 Encode Keys_ para deixar a indexação mais eficiente. E por fim, clique em _Submit_. 

<img src="Prints/Img47.png" width="520" height="700">

Após criar o data source, skillset, index e o  indexer. Voltamos para a página inicial do _Azure AI Search_. No menu lateral, dentro de _Search Management_, selecione _Indexers_.

<img src="Prints/Img48.png" width="410" height="550">

Selecione o _indexer_ recém-criado e depois _&orarr;_. Aguarde até receber a mensagem de sucesso e selecione o indexer.

<img src="Prints/Img49.png" width="560" height="240">

Dentro do indexer, selecione _Search explorer_.

<img src="Prints/Img50.png" width="1110" height="280">

Dentro do _Search explorer_ é onde escrevemos as _queries_, para fazer a pesquisa e é também onde vemos os resultados em JSON.

<img src="Prints/Img51.png" width="1430" height="390">

No exemplo abaixo, foi adicionado dois parâmetros: "sentiment: 'positive'"  e "count": true. Então o _AI Search_ retorna os feedbacks com avaliações positivas.

<img src="Prints/Img52.png" width="1340" height="680">


***
## Conclusões

O Azure AI Search mostra-se uma ferramenta completa para quem deseja fazer pesquisas pelo fato de ter a sua disposição todos os serviços de IA do Azure, criando a possibilidade de ter em um só local o banco de dados junto com a ferramenta de IA (seja reconhecimento de texto ou de imagem) junto com a ferramenta de pesquisa. Além de possuir os tutoriais, que auxiliam na construção do projeto, não exigindo do usuário um conhecimento profundo em Machine Learning.

----
## Fontes/Links Úteis
---
- **** Disponível em: https://learn.microsoft.com/pt-pt/azure/search/search-what-is-azure-search, Acesso em: 21 de Abril de 2024.
- **** Disponível em: https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/11-ai-search.html
, Acesso em: 21 de Abril de 2024.
- **** Disponível em: https://learn.microsoft.com/en-us/training/modules/analyze-receipts-form-recognizer/2-document-intelligence-capabilities, Acesso em: 21 de Abril de 2024.
- **** Disponível em: https://learn.microsoft.com/pt-pt/azure/search/search-create-service-portal, Acesso em: 21 de Abril de 2024.
