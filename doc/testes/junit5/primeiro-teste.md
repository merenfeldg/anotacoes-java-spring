# Primeiro Teste Unitário
Vamos utilizar só o JUnit5 que se você baixou o projeto pelo Spring Initializr já vem a depedência do JUnit5 e do Mockito

Cada teste precisa receber a anotação @Test

<br>

## Antes de tudo como eu nomeio os meus testes?
- Começar com test
- Colocar o nome do método (testImprimir)
- O que você vai fazer
- Qual o retorno que desejamos

**EXEMPLO:** testSomar_Quando_DoisMaisDois_DeveRetornarQuatro

Ou podemos usar o @DisplayName() que é outra forma de normear testes, passando uma string

**EXEMPLO:** 
```java
@DisplayName("Test Somar quando dois mais dois deve retornar quatro")
@Test
void testCalculadora_MetodoSomar() {
    //(...)
}
```

## Como organizar bem os testes 
- **GIVEN:** Onde declaramos nossas variáveis.
- **WHEN:** Onde o método que vai ser testado.
- **THEN:** Onde vai validar o retorno e verificando o comportamento se é o mesmo que a gente esperava.

<br>

## Implementando TDD na prática! 
Criar uma classe chamada StringManipulator que ela tem dois métodos:
- Inverte uma String
- Verifica se é um palíndromo

### RED
Escrever um teste para o méotodo de inverter, retornando a String invertida
```java
public class StringManipulatorTest {

    @Autowired
    private StringManipulator manipulator;

    @DisplayName("Test inverter, recebendo uma String e retornando ela invertida")
    @Test
    void testStringManipulator_metodoInverter() {
        //GIVEN
        String stringRecebida = "exemplo";
        String stringInvertidaQueEuEspero = "olpmexe";

        //WHEN
        String retornoDoMetodoInverter = manipulator.inverter(stringRecebida);

        //THEN
        assertEquals(stringInvertidaQueEuEpero, retornoDoMetodoInverter);
        assertNotEquals(stringRecebida, retornoDoMetodoInverter);
    }
}
```
O assertEquals é para testar se os dois valores passados são iguais. O primeiro parâmetro é o valor que eu espero e o segundo é o valor retornado do método testado.

### GREEN 
Pronto agora sabemos como o nosso método tem que se comportar agora vamos implementar
```java
@Component
public class StringManipulator {

    public String inverter(String str) {
        StringBuilder stringInvertida = new StringBuilder(str).reverse();
        return stringInvertida.toString();
    }
}
```
O teste passou
### REFACTOR
Podemos refatorar o método inverter
```java
public class StringManipulator {

    public String inverter(String str) {
        return new StringBuilder(str)
                        .reverse()
                        .toString();
    }
}
```
