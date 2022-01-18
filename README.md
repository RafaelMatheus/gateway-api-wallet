# WALLET BACKEND

Projeto de uma WALLET utilizando microsserviços, java e spring.
## Arquitetura do projeto

![Desenho arquitetural](https://user-images.githubusercontent.com/25590639/150031129-5ca1fdd4-e610-4958-8605-c8c13751ca77.jpeg)


### Como executar o projeto

###### Pré requisitos

* Necesário java 11 instalado, docker ou docker-compose instalado no computador.
* Necessário a instalação do maven caso não tenha o docker ou o docker-compose instalados.
* Se for utilizar o docker-compose ou docker neste repositório há um arquivo com o docker-compose.yml ou dockerfile assim como em todos os outros projetos.


###### Download dos projetos
* É necessário baixar o projeto do [gateway](https://github.com/RafaelMatheus/gateway-api-wallet) e executá-lo.
* É necessário baixar o projeto do [usuário](https://github.com/RafaelMatheus/usuario-service) e executá-lo.
* É necessário baixar o projeto de [transação](https://github.com/RafaelMatheus/transacao-service) e executá-lo. 
* É necessário baixar o projeto de [conta](https://github.com/RafaelMatheus/account-service) e executá-lo

### Exemplos

##### usuário-service

* post request: http://{URL_GATEWAY}/api/usuarios

```json
{
  "cpf": "string",
  "dataNascimento": "yyyy-mm-dd",
  "endereco": {
    "cep": "string",
    "cidade": "string",
    "estado": "string",
    "logradouro": "string",
    "numero": "string"
  },
  "nome": "string",
  "telefones": [
    "string"
  ]
}
```

* GET request http://{URL_GATEWAY}/usuarios/0123456789


##### Contas-service

###### contas
* POST request http://{URLGATEWAY}/api/contas

``` json 
{
  "cpfUsuario": "string",
  "numeroAgencia": "string"
}
```
* GET request http://{URLGATEWAY}/api/contas

###### Agencias
* POST request http://{URLGATEWAY}/api/agencias

``` json 


{
  "descricao": "string"
}

```
* GET request http://{URLGATEWAY}/api/agencias

###### Transacoes

* POST request http://{URLGATEWAY}/api/transacoes

``` json 
{
  "contaDestino": {
    "numeroAgencia": "string",
    "numeroConta": "string"
  },
  "contaOrigem": {
    "numeroAgencia": "string",
    "numeroConta": "string"
  },
  "tipoTransacao": "TRANSFERENCIA",
  "valorTransacao": 0
}

```

``` json 
{
  "contaDestino": {
    "numeroAgencia": "string",
    "numeroConta": "string"
  },
  "tipoTransacao": "TRANSFERENCIA",
  "valorTransacao": 0
}

```

``` json 
{
  "contaOrigem": {
    "numeroAgencia": "string",
    "numeroConta": "string"
  },
  "tipoTransacao": "TRANSFERENCIA",
  "valorTransacao": 0
}

```


#### É possivel acessar a documentação de cada projeto separado.

* http://{URL}:{PORT}/swagger-ui.html
