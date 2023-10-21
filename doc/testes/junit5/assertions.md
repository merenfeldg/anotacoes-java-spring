# Assertions
É aonde de fato testamos o retorno do método que vamos verificar com o valor que esperamos que ele retorne. Existe vários assertions para cobrir os casos que iremos testar.

Para deixar o nosso teste mais simples e legível importamos estaticamente a classe Assertions.

<br> 

## assertEquals | assertNotEquals
Método **assertEquals** compara dois valores se são iguais:
- **1º parâmetro:** O valor que esperamos
- **2º parâmetro:** O retorno do método que vamos testar

Método **assertNotEquals** compara dois valores se **não são iguais**.

### Exemplo assertEquals
Vou testar o método de dividir da classe Calculadora
```java
@DisplayName("Test Calculadora.dividir(), passando 10 e 5 e retornando 2")
@Test
void testCalculadora_MetodoDividir() {
    //GIVEN
    final double primeiroNumeroRecebido = 10;
    final double segundoNumeroRecebido = 5;
    final double valorQueEuEspero = 2;

    //WHEN
    double retornoDoMetodoDividir = calculadora.dividir(primeiroNumeroRecebido, segundoNumeroRecebido);

    //THEN
    assertEquals(valorQueEuEspero, retornoDoMetodoDividir);
}
```
### Exemplo assertNotEquals
```java
###  Exemplo assertNotEquals
@DisplayName("Test Calculadora.dividir(), passando 10 e 5 e verificando se o retorno não é 10 e 5")
@Test
void testCalculadora_MetodoDividir() {
    //GIVEN
    final double primeiroNumeroRecebido = 10;
    final double segundoNumeroRecebido = 5;
    final double valorQueEuEspero = 2;

    //WHEN
    double retornoDoMetodoDividir = calculadora.dividir(primeiroNumeroRecebido, segundoNumeroRecebido);

    //THEN
    assertNotEquals(primeiroNumeroRecebido, retornoDoMetodoDividir);
    assertNotEquals(segundoNumeroRecebido, retornoDoMetodoDividir);
}
```

<br>

## assertArrayEquals
O conceito é o mesmo que o assertEquals só que esse método compara dois arrays.

### Exemplo
Vou testar um método que recebe uma lista de inteiros e retira todos os elementos negativos

```java
public class ControladorLista {

    public List<Integer> retiraValoresNegativos(List<Integer> lista) {
        return lista.stream()
                    .filter(valor -> valor > 0)
                    .collect(Collectors.toList());
    }
}
```
```java
public class ControladorDaListaTest {
    @Autowired
    private ControladorLista controlador;

    @DisplayName("Test método retiraValoreNegativos(), recebendo uma lista e retirando os inteiros negativos")
    @Test
    public testControladorLista_MetodoRetiraValoresNegativos() {
        //GIVEN
        final List<Integer> listaRecebida = new ArrayList<>(List.of(10, 5, -1, -19);
        final List<Integer> listaQueEuEspero = new ArrayList<>(List.of(10, 5));

        //WHEN
        List<Integer> retornoDoMetodo = controlador.retiraValoresNegativos(listaRecebida);

        //THEN
        assertArrayEquals(listaQueEuEspero, retornoDoMetodo);
    }
}
```

## assertNotNull
Esse método recebe um parâmetro e verifica se é diferente de null  

### Exemplo 

