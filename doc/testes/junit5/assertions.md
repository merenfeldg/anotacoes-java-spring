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
void testCalculadora_MetodoDividir_v1() {
    //GIVEN
    final double numeradorRecebido = 10;
    final double denominadorRecebido = 5;
    final double valorQueEuEspero = 2;

    //WHEN
    double retornoDoMetodoDividir = calculadora.dividir(numeradorRecebido, denominadorRecebido);

    //THEN
    assertEquals(valorQueEuEspero, retornoDoMetodoDividir);
}
```
### Exemplo assertNotEquals
```java
@DisplayName("Test Calculadora.dividir(), passando 10 e 5 e verificando se o retorno não é 10 e 5")
@Test
void testCalculadora_MetodoDividir_v2() {
    //GIVEN
    final double numeradorRecebido = 10;
    final double denominadorRecebido = 5;
    final double valorQueEuEspero = 2;

    //WHEN
    double retornoDoMetodoDividir = calculadora.dividir(numeradorRecebido, denominadorRecebido);

    //THEN
    assertNotEquals(numeradorRecebido, retornoDoMetodoDividir);
    assertNotEquals(denominadorRecebido, retornoDoMetodoDividir);
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
<br>

## assertNotNull
Esse método recebe um parâmetro e verifica se é diferente de null  

```java
    @Test
    public testAssertNotNull() {

        String nomePessoa = "Amanda";
        assertNotNull(nomePessoa);
    }
}
```

<br>

## assertTrue | assertFalse
Verifica o retorno do método que queremos testar se é verdadeiro ou falso

### Exemplo 
Tenho uma classe VerificadorNumero que tem dois métodos, um para verificar se o número passado no parâmetro é par e ou outro verifica se é impar

```java
public class VerificadorNumero {

    public boolean verificaSeEhPar(int numero) {
        return numero % 2 == 0;
    }
    
    public boolean verificaSeEhImpar(int numero) {
        return numero % 2 != 0;
    }
}
```
```java
public class VerificadorNumeroTest {
    @Autowired
    private VerificadorNumero verificador;

    @DisplayName("Test verificaSeEhPar, recebendo 2 e testando se o método retorna true")
    @Test
    void testVerificadorNumero_MetodoVerificaSeEhPar() {
        //GIVEN
        final int numeroRecebido = 2;
    
        //WHEN
        boolean retornoDoMetodo = verificador.verificaSeEhPar(numeroRecebido);

        //THEN
        assertTrue(retornoDoMetodo);
    }

    @DisplayName("Test verificarSeEhImpar, recebendo 6 e testando se o método retorna false")
    @Test
    void testVeficiadorNumero_MetodoVerificaSeEhImpar() {
        //GIVEN
        final int numeroRecebido = 3;

        //WHEN
        boolean retornoDoMetodo = verificador.verificaSeEhImpar(numeroRecebido);

        //THEN
        assertFalse(retornoDoMetodo);
    }
}
```
<br>

## assertThrows

Aqui verificamos se o método que iremos testar vai gerar a excessão esperada, assim recebendo 2 parâmetros: 
- A classe da excessão que vai ser lançada
- Recebe um Supplier. ex: () -> metodo();

### Exemplo
Vou reaproveitar o exemplo que eu dei no assertEquals e no assertNotEquals. Porém agora vou passar 0 como denominador assim gerando uma excessão ArithmeticException.
E o intuito do teste vai ser se essa excessão vai ser lançada.

```java
@DisplayName("Test Calculadora.dividir(), passando 20 e 0 e verificando se é lançada excessao")
@Test
void testCalculadora_MetodoDividir_v3() {
    //GIVEN
    final double numeradorRecebido = 20;
    final double denominadorRecebido = 0;

    // WHEN e THEN
    assertThrows(ArithmeticException.class,
                () -> calculadora.dividir(numeradorRecebido, denominadorRecebido));
}
```
<br>

## assertAll
Esse método que agrupa outros assert dentro dele assim executando todos e se um ou mais darem erro ele vai mostrar. Diferente se eu escrever vários assert sem agrupar, 
pois os outros assert que iriam ser executados não vão ser mais.

### Exemplo
Classe calculadora tem também um método que soma dois valores inteiros, vou testar vários cenários no teste

```java
@DisplayName("Test Calculadora.somar(), verificando vários cenários")
@Test
void testCalculadora_MetodoSomar_v1() {
    assertAll(
        () -> assertEquals(30, calculadora.somar(10, 20)),
        () -> assertEquals(20, calculadora.somar(40, -20)),
        () -> assertNotEquals(5, calculadora.somar(5, 5)),
        () -> assertNotEquals(0, calculadora.somar(-5, 10))
    );
}
```

    
