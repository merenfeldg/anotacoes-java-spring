# @Value 
Tem o papel de injetar valores nas variáveis porém não deixamos essas informações no código e sim no arquivo .properties, então passando o caminho para o @Value acessar essas variáveis que decidi lá.
> Antes de passar o caminho precisa começar com o $ e estrar entres chaves {...}  ==> "${caminho.definido}"
<br>

### Exemplo: 
Quero criar uma classe Usuário e nela contem os atributos: nome, email e senha só que não quero deixar essas informações dentro da classe, então irei colocar no arquivo .properties
```java
usuario.nome=Gabriel
usuario.email=gabriel10@gmail.com
usuario.senha=tamanduaBandeira123 
```
Na classe Usuário 
```java
public class Usuario {

    @Value("${usuario.nome}")
    private Stringg nome;

    @Value("${usuario.email}")
    private String email;

    @Value("${usuario.senha}")
    private String senha;

    //(...)
}
```
