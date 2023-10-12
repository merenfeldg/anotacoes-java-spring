# @Bean
Outra forma de declarar um bean ao invés o @Component, @Service, @Controller, etc... O que diferencia que ao invés de anotar uma classe o @Bean anota um método e a instância retornada vai ser um Bean gerenciada pelo Spring
> Só pode ser usado dentro do scopo de uma classe que recebe a anotação @Configuration

Uma boa solução quando estamos trabalhando com bibliotecas de terceiros é usar essa annotation
<br>

### Exemplo: 

