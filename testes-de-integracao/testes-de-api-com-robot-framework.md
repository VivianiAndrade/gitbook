# Testes de API com Robot Framework

No Robot existe duas librarys bem importantes que conseguimos desenvolver testes de API em nosso projeto.São elas:

**Library RequestsKeywords:** Usa uma library request do Python por baixo.

* Keywords:  [https://marketsquare.github.io/robotframework-requests/doc/RequestsLibrary.html](https://marketsquare.github.io/robotframework-requests/doc/RequestsLibrary.html)
  * Importante: CreateSession: para o Robot se conectar a API. Campos obrigatórios: url e alias.

**Library Collections:** para manipular o retorno da API em Json e os asserts. Trabalha com listas\(arrays\) e dicionários\(Json\).

* Keywords: [http://robotframework.org/robotframework/latest/libraries/Collections.html](http://robotframework.org/robotframework/latest/libraries/Collections.html)

**Importante:** 

O comando para rodar os testes no Visual Studio Code pelo cmd é: **robot -d .\results TestsCasesFakeAPI.robot,** sendo que results é a pasta que iremos guardar os arquivos .html de log e report e **TestsCasesFakeAPI.robot** é o nome da suite de teste aqui exemplificada.

## Automatizando uma requisição GET <a id="automatizando-uma-requisi&#xE7;&#xE3;o-get"></a>

Aqui a requisição Get é feita através do método **GET on Session** da Library RequestsLibrary.

Nela estamos passando a URL fakeAPI e a URI v1/Books e guardando a resposta na variável global RESPOSTA.

O Log exibe o trecho em formato texto através do sufixo .text.

![](../.gitbook/assets/api_robot_get.png)

![](../.gitbook/assets/api_robot_get_01.png)

* Mais formatos podem ser consultados neste [doc.](http://rch-sl04:9000/mod06-response.pdf)

## Conferências da requisição <a id="confer&#xEA;ncias-da-requisi&#xE7;&#xE3;o"></a>

Ex: Conferir o status code, reason e lista.

![](../.gitbook/assets/image-7-.png)

![](../.gitbook/assets/image-8-.png)

* [O que é HTTP, HTTP error e os principais códigos que você precisa saber](http://rch-sl04:9000/mod06_http_status.pdf)

## Conferências do JSON Body <a id="confer&#xEA;ncias-do-json-body"></a>

Importante ficar atento aos espaços, tabs.

Aqui estamos usando a variável &{BOOK\_15} que contem a resposta do dicionário.

Para a verificação dos campos podemos utilizar **Dictionary Should Contain Item** e também **Should Not Be Empty,** por exemplo.

![](../.gitbook/assets/image-9-.png)

![](../.gitbook/assets/image-10-.png)

* [Dicas de conferências em JSON](http://rch-sl04:9000/mod06_conferenciasjson.pdf)

## Automatizando uma requisição POST com HEADER e BODY <a id="automatizando-uma-requisi&#xE7;&#xE3;o-post-com-header-e-body"></a>

No Robot podemos enviar o POST através do método **Post On Session** da Library RequestsLibrary.

No exemplo abaixo estamos enviando o data, que é corpo da requisição e também o header.  


![](../.gitbook/assets/image-12-.png)

![](../.gitbook/assets/image-11-.png)

## Results <a id="results"></a>

Relátorio de Logs.

Dentro de cada Tag como Setup, Test, temos as Keywords executadas com seus retornos.

![](../.gitbook/assets/image-13-.png)

 fonte: Curso Automação de Testes com Robot Framework - Udemy. **por** [**Mayara Fernandes**](https://www.udemy.com/user/mayara-ribeiro-fernandes/)

