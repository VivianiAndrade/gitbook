# Testes de API com Postman

## **Automatizando Testes de API com o Postman** <a id="automatizando-testes-de-api-com-o-postman"></a>

Antes de criarmos os testes no Postman precisamos ou criar api Rest ou importá-la.

Para criar:

* **New→ Collection → Name\(nome para sua Coleção\) → Authorization \(Ex: Basic Auth\) → Create**

Depois podemos ir na Aba **Collection → Na Coleção Criada → Add Request → Request Name \(EX: GET/programas\) → Save**

Para passar variáveis nas requisições devemos criar dessa forma: 

Exemplo:

* {{idPrograma}} no **Request → Gerenciar ambientes → Add →**
* No Enviroment → **Selecionar o Ambiente criado anteriormente.**

Para Importar:

* **Import → File → Upload files → Seleciona o contrato \(yaml ou json\) → ok → close**

No Postmam existe uma aba chamada **Tests.** Nela podemos escrever testes com JavaScript e eles estão baseados em uma lib chamada [Chai](https://www.chaijs.com/api/assert/). 

A direita temos uma aba com os **Snippets** onde costam exemplos de testes prontos. [Documentação sobre testes com scripts.](https://learning.postman.com/docs/writing-scripts/test-scripts/)

Exemplos: 

* Response body: Json value check

```text
pm.test("Your test name", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.value).to.eql(100);
});
```

* Teste de validação de tempo de resposta:

```text
pm.test("Validação do tempo de resposta do serviço menor que 1600ms", function (){
  pm.expect(pm.response.responseTime).to.be.below(1600);
});
```

* **pm:** objeto globlal do postman com diversas features.
* **ctrl+alt+c:** abre o console do postman para exibir as mensagens de console.log, console.info.

Na Aba Pre-request Script, podemos colocar parâmetros para iniciar nossos testes, carregar e excluir massas de testes:

**//TODO Colocar exemplo de código.**

Depois de salvarmos estes testes, podemos exportá-los para serem usados no CI/CD:

* **Export → exportar para dentro da API back na pasta test → resources.**

fonte: Curso Alura. **por** [**Juliana Amoasei** ](https://cursos.alura.com.br/user/juliana-amoasei)e ****[**Vinicius Dias**](https://cursos.alura.com.br/user/cviniciussdias)

## Testes Padrão <a id="padr&#xE3;o"></a>

//Todo

**Links Importantes:**

* [Understanding JSON Schema](https://json-schema.org/understanding-json-schema/)
* [Generate JSON schema from JSON](https://jsonschema.net/login)
* [Testes Automatizados de API com postman: O que testar e como testar. Parte 1](https://medium.com/rchlo-midway-tech/testes-automatizados-de-api-com-postman-o-que-testar-e-como-testar-parte-1-d388c8f41fa8)

