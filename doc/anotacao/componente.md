# @Component
Essa anotação indica para o Spring que a classe que criamos vai ser gerenciada por ele, chamada de Bean. Então é um objeto que é instanciado, montado e gerenciado pelo Spring IoC container.

O Spring há vários beans criado por ele mesmo e quando damos o start ele scanea todas as classses para achar se tem alguma classe @Component para poder gerenciar

## Exemplo: 
```java
@Component
public class Pessoa {
  //(...)
}
```
