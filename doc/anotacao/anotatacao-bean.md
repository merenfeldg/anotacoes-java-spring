# @Bean
Outra forma de declarar um bean ao invés o @Component, @Service, @Controller, etc... O que diferencia que ao invés de anotar uma classe o @Bean anota um método e a instância retornada vai ser um Bean gerenciado pelo Spring
> Só pode ser usado dentro do scopo de uma classe que recebe a anotação @Configuration

Uma boa solução quando estamos trabalhando com bibliotecas de terceiros é usar essa annotation
<br>

### Exemplo: 
Vou usar a biblioteca ModelMapper, que serve para mapear dados de um objeto para outro, no meu código porém eu não tenho acesso ao código dessa bibliteca para anotar ela com @Component.
```java
@Configuration
public class AplicacaoConfiguration {

    @Bean
    public ModelMapper modelMapper() {
        return new ModelMapper();
    }
} 
```

