# Métodos HTTP
Através do métodos dizemos pro servidor qual tipo de ação queremos executar em um determinado recurso através da URI.
<br>
Os métodos podem ser divididos em dois grupos: 
### Seguro
Um método seguro é quando não altera o estado do meu servidor, por exemplo o GET que é uma operação de leitura/consulta.

### Idempotente
Um método idempotente é quando uma requisição é feita várias vezes ele sempre vai retornar o mesmo resultado.
<br>
<br>

<div align="center">
    <img src="https://github.com/merenfeldg/anotacoes-java-spring/assets/129122790/32421052-6602-4e89-804d-4b13b8f8b399">
</div>

# GET 
- Consulta um recurso.
- Seguro.
- Idempotente.

# PUT
- Atualiza um determinado recurso. Não atualiza apenas os recursos passados no corpo da requisição e sim o recurso completo, não pode ser usado
em uma atualização parcial. Se meu recurso tem 2 atributos mas eu só passo 1 o outro que sobrou vai ser considerado null na atualização.
- Não é seguro.
- É Idempotente.

# POST
- Cria um recurso dentro de uma coleção de recursos, quando eu insiro várias vezes eu vou criar vários repetidos.
- Não seguro.
- Não é idempotente.

# DELETE
- Deleta um recurso.
- Não é seguro.
- É idempotente.
