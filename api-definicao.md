# API - Application Programming Interface
- Traduzindo para o português: interface de programação de aplicações.
<br>
É o intermediador do cliente para o servidor, o cliente não necessariamente tem que ser uma pessoa, pode ser um site, aplicativo, bot, etc... Então API é a "ponte" da aplicação e da plataforma que quero puxar informações.
Muito interessante para quem fornece esses dados(Meta, GitHub, etc...) pois é uma maneira segura de disponibilizar esses dados

### Exemplo: 
<div align = "center">
    <img src="https://github.com/merenfeldg/anotacoes-java-spring/assets/129122790/a2db86db-fabd-4278-b34b-06000dbf408d"/>
</div>
<br>
Tim Maia após curtir uma praia em Copacabana, o cantor decide comprar pães na padaria para levar para sua família. Ele então é atendido pelo atendente e faz o seu pedido, que são os três pães e isso no contexto de API é a REQUEST(requisição) para o atendente que é a API.
<br>
<br>

Na ilustração Tim Maia fala com o atendente e ele entendeu o que o cantor quer. Na realidade de consumir API não é tão simples assim mas também não é nada como um bicho de sete cabeças. 
<br>
<br>
Para fazer a comunicação entre máquinas diferentes usamos o protocolo HTTP que padroniza a forma de se comunicar com as API. Então usamos os métodos HTTP, que são os tipos de comunicação com o servidor. No exemplo acima Tim Maia fez um GET para obter os dados(pães).
<br>
<br>
O servidor vai responder(Response) usando um JSON ou um XML, é mais comum reponder com JSON.
<br>
<div align = "center">
    <img src="https://github.com/merenfeldg/anotacoes-java-spring/assets/129122790/4caee3f2-1e22-4384-8dc4-94ee09511e96"/>
</div>
