📋 TO DO
Fazer sua collection usando a API Restful-booker
Exportar a collection
Subir a collection no repositório
✔️ Contida na pasta Postman: A collection foi feita no Postman e exportada como arquivo .json
Sobre Restful-booker: É uma API de teste criada para que possa ser utilizada em testes de integração e testes de aceitação. Ela permite que você faça operações CRUD (criar, ler, atualizar e deletar) em Bookings, criar usuários, autenticar usuários e muito mais. A API foi criada para simular uma aplicação real, e por isso ela possui regras de negócio e validações para garantir que os dados enviados para a API estejam corretos e seguindo as regras da aplicação. Alguns exemplos de operações que você pode realizar na API incluem criar um novo Booking, obter informações de um Booking existente, atualizar as informações de um Booking ou deletar um Booking.
👩‍💻 Automatizando com Rest Assured
Rest Assured é uma biblioteca Java que é usada para testar APIs REST. Ela permite que você envie solicitações HTTP para uma API e verifique se a resposta é o que você espera. Rest Assured facilita muito o processo de validação de respostas HTTP, pois fornece uma interface simples e intuitiva para isso. Além disso, é possível realizar vários tipos de validação, como verificar o código de status HTTP, os cabeçalhos da resposta e o corpo da resposta. Rest Assured também oferece suporte a vários formatos de dados, como JSON e XML.

🟩 As descrições a seguir são referentes às classes criadas tomando como referência a API Restful-booker
➔ Caminho dos códigos descritos: /src/main/java/Entities

Booking
A classe Java chamada Booking, representa uma reserva em um sistema de reservas de hospedagem. A classe possui diversos atributos, como nome e sobrenome do hóspede, preço total da reserva, informação sobre se o depósito já foi pago, detalhes da data da reserva (classe BookingDates) e informações adicionais. Ela também possui métodos getters e setters para cada atributo, permitindo obter e alterar os valores destes atributos.

BookingDates
A classe BookingDates representa a data de check-in e check-out de uma reserva (ou booking, em inglês). Ela possui dois atributos, checkin e checkout, ambos do tipo String, que armazenam essas informações.

Ela possui um construtor que recebe os valores dessas variáveis como parâmetros e os atribui aos atributos da classe. Além disso, possui métodos getters e setters para esses atributos, permitindo acessar ou modificar os valores das datas de check-in e check-out.

User
A classe User representa um usuário com os seguintes atributos:

username: nome de usuário do usuário
firstName: primeiro nome do usuário
lastName: sobrenome do usuário
email: email do usuário
password: senha do usuário
phone: telefone do usuário
Essa classe possui um construtor que recebe esses atributos como parâmetros e os atribui aos respectivos campos da classe. Além disso, há um método getter e um setter para cada um desses atributos. Isso permite que outras classes possam acessar e modificar os valores dos atributos de um objeto User.

🟩 As descrições a seguir são referentes à classe criada para fazer automação dos testes
BookingTests
➔ Caminho do código descrito: /src/test/java/

Este código é uma classe de teste JUnit para testar uma API de reservas.

A classe importa três outras classes: Booking, BookingDates e User. Essas classes representam os objetos de reserva, datas de reserva e usuário, respectivamente. A classe também importa a biblioteca Faker para gerar dados aleatórios para preencher esses objetos.

A classe também importa a biblioteca RestAssured, que é usada para fazer solicitações HTTP à API de reserva de hotel. A classe também usa os filtros RequestLoggingFilter, ResponseLoggingFilter e ErrorLoggingFilter da biblioteca RestAssured para registrar solicitações, respostas e erros durante os testes.

A classe possui três métodos de teste: getAllBookingsById_returnOk, getAllBookingsByUserFirstName_BookingExists_returnOk e CreateBooking_WithValidData_returnOk. Cada método de teste envia uma solicitação HTTP à API de reserva de hotel e verifica se a resposta é válida.

O método Setup é executado uma vez antes de todos os testes, e inicializa o objeto faker, cria um novo usuário e uma nova reserva com as informações do usuário e atribui a URL da API de reserva de hotel à propriedade baseURI da classe RestAssured.

O método setRequest é executado antes de cada método de teste e inicializa o objeto request com as configurações padrão para as solicitações HTTP (como o tipo de conteúdo e autenticação básica).

Os três métodos de teste enviarão solicitações HTTP à API de reserva de hotel e verificarão se as respostas são válidas de acordo com os critérios especificados.