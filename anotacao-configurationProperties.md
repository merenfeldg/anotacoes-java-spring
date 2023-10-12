# ConfigurationProperties
Uma forma mais simples de injetar valores em variáveis do que a anotação @Value. Criamos uma classe que vai receber todos os valores desejados no arquivo .properties
> Para dar certo esses valores precisam ter o mesmo prefixo
<br>

### Exemplo 
Vou usar o mesmo exemplo que fiz com o @Value 
```java
@Component 
@ConfigurationProperties(prefix = "usuario")
public class UsuarioProperties {

    private String nome;
    private String email;
    private String senha;

    //(...)
}
```
Agora ao invés da classe Usuario receber 3 atributos desses que eu especifiquei vai receber um UsuarioProperties. Deixou mais simples o código.
```java
public class Usuario {

    @Autowired
    private UsuarioProperties usuarioProperties;

    //(...)
}

```
