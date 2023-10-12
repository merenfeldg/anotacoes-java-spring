# @Qualifier
Quando eu tenho duas ou mais classes ou métodos que implementam ou retornam o mesmo objeto o Spring não sabe qual delas injetar. A anotattion @Qualifer então recebe o nome de qual implementação que queremos injetar.
> Essa annotation sempre embaixo do @Autowired e a primeiro caracter do nome passado tem que ser em minúsculo
<br>

### Exemplo: 
Vou criar uma interface de Service
```java
public interface PessoaService {
    (...)
}
```
E crio duas classes que vão implementar essa mesma interface Service só que cada uma tem sua lógica de negócio própria
```java
public class PessoaServiceImplV1 implements PessoaService{
    (...)
}
public class PessoaServiceImplV2 implements PessoaService{
    (...)
}
```
Usei o mesmo exemplo da explicação da annotation @Autowired porém agora na classe Controller eu preciso injetar um PessoaService só que tenho a implementação V1 e a V2, para dizer qual que eu quero vou usar o @Qualifier
```java
@RestController
@RequestMapping("/pessoas")
public class PessoaController {

    @Autowired
    @Qualifier("pessoaServiceImplV2")
    private PessoaService service;

    (...)
}
```
