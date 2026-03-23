# Requisitos Funcionais

## Auth

### - **RF-01 - Cadastro**

**Story:** Como visitante, quero criar uma conta,
para acessar o Memovox e começar a estudar idiomas.

**Critérios de aceitação:**

- Dado que preencho meu nome, email e senha válidos e confirma, minha conta é criada e o sistema encaminha um email para verificação da criação.
- Dado que deixo algum campo obrigatório vazio, o sistema emite mensagem de erro.
- Dado que uso um email que já existe, o sistema exibirá um dialog com a mensagem pergunta se deseja fazer login ou contestar essa utilização de email.

### - **RF-02 - Login**

**Story:** Como usuário já cadastrado, quero fazer login, para acessar meus decks e estudar.

**Critérios de aceitação:**

- Dado que insiro email e senha válidos e verificado, o sistema me redireciona para o dashboard com a lista decks
- Dado que eu fiz o cadastro, insiro o email e senha para fazer o primeiro login, e não validei o email, o sistema exibirá uma mensagem para validar o e-mail com um botão para reenviar o email.
- Dado que eu insiro email ou senha inválidos, o sistema emite uma mensagem de erro que os dados são incorretos(sem específicar qual está errado.)
- Dado que não insiro email ou senha, o sistema emite uma mensagem de erro informando que o campo é obrigatório.

### - **RF-03 - Logout**

**Story:** Como usuário já logado no sistema, quero fazer logout, para poder encerrar minha sessão.

**Critérios de aceitação:**

- Dado que estou logado, com um sessão válida, eu clico no botão fazer logout, o sistema encerra minha sessão e redireciona para a página home do site (Deve limpar os cookies, dados de autenticação e invalidar tokens).
- Dado que fiz logout, tento acessar uma página protegida, o sistema me redirecionará para a página de login
