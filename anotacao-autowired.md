# Autowired
Facilita a vida do programador que passa responsabilidade de injeção de dependência para o Spring, que procura um bean correspondente para injetar na variável anotada com o @Autowired.
<br><br>
### Exemplo:
Vou criar uma interface de Service.
```java
public interface PessoaService {
    (...)
}
```
Agora uma classe vai implementar a interface Service que criamos
```java
@Service
public class PessoaServiceImpl implements PessoaService {
     (...)
}
```
Agora para mostrar o funcionamento do @Autowired utilizarei uma classe Controller que vai precisar utilizar o Service
```java
@RestController
@RequestMapping("/pessoas")
public class PessoaController {

    @Autowired
    public PessoaService service

    (...)
}
```
A anotação vai procurar um Bean que implemente a interface PessoaService e vai injetar o PessoaServiceImpl para nós. Não vamos precisar de construtor nem nada, deixando o código mais simples, legível e fácil de manter.
