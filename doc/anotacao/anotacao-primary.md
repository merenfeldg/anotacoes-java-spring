# @Primary
Quando uma classe recebe essa annotation é porque ela vai ter prioridade entre as classes que implementam a mesma interface, por default @Primary vai ser escolhida se não vou ter que especificar com o @Qualifier
<br>

### Exemplo: 
```java
@Service
public class PessoaServiceV1 implements PessoaService {
    /(...)
}

@Service
@Primary
public class PessoaServiceV2 implements PessoaService {
    /(...)
} 
```
No meu controller então se eu não especificar nada, o service que vai ser injetado vai ser o V2
```java
public class PessoaController {

    @Autowired
    private PessoaService service;
}
```
Quero o v1, como eu faço?
```java
public class PessoaController {

    @Autowired
    @Qualifier("pessoaServiceV2")
    private PessoaService service;
}
```
