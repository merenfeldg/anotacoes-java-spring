# @Service, @Repository, @Controller, @RestController
Todas são @Component. A finalidade delas serve para dar mais expressividade para as classes que vão receber a anotação.

### @Service 
Classe que vai implementar a lógica de negócio.
### @Repository 
Classe responsável pela persistência e recuperação de dados.

<br><br>
Um classe controller tem o papel de receber **requisições HTTP**. Essas duas anotações temos que prestar atenção pois as duas tem retorno diferente. 

### @Controller
Controller que respeita o padrão MVC, assim retornando uma view para o cliente

### @RestController
Junção das anotações @Controller e @ResponseBody (O objeto vai ser serializado e enviado como **response** para o cliente). É um controller que retorna um JSON.
