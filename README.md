# GraphGeoNames

    Modelagem e Estruturação de Gazetteers com o Modelo de Dados de Grafos

Esse projeto tem por objetivo realizar a criação de um banco de dados geográficos orientado à grafos, de forma automática, utilizando scripts na linguagem Python. O SGBD em questão é o Ne4J e os dados usados foram extraídos do gazetteer global GeoNames.

* Para criar o banco, é necessário ter os arquivos em formato .csv, com os devidos atributos que atendem ao seu obejtivo.
* Após separar os arquivos de acordo com sua finalidade, deve-se passar as credencias do seu banco (o host, nome do banco e a senha de acesso).
* Utilizando a biblioteca py2neo, há várias variáveis, denominadas cqlCreate, que servem para armazenar as consultas da linguagem Cypher.
* Através delas, os nós e relacionamentos são criados.
* Os nomes alternativos dos locais, originalmente, estavam em uma coluna. Para facilitar a criação dos relacionamentos, fez-se necessário a separação desses nomes em outras colunas. Para tal, a função "div_names" separa essas propriedades em outras colunas. Ela também realiza a remoção de colunas, caso seja necessário.
* Para realizar a checagem das coordenadas dos lugares, existem várias funções denominadas "check_place". Nelas são lidos arquivos em formato .wkt e feitas comparações entre as coordenadas que estão neles, e as coordenadas que estão no arquivo .csv.
* Caso as coordenadas que estão no .csv estejam no .wkt, os relacionamentos entre os vértices são criados.
* A chamada das variáveis que armazenam as consultas em Cypher são realizadas no fim do código. 
* A função "create_nodes" realiza a chamada das variáveis que criam os nós.
* Após esse passo, a função "create_indexes" deve ser executada para criar os indexes dos vértices.
* A função "create_relationships" cria os relacionamentos entre os nós dos lugares e seus nomes alternativos.


* Obersvação: o código está em processo de aprimoramento, por isso mudanças serão perceptíveis e explicadas no repositório.
