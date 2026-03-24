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
- Dado que eu insiro email ou senha inválidos, o sistema emite uma mensagem de erro que os dados são incorretos(sem especificar qual está errado.)
- Dado que não insiro email ou senha, o sistema emite uma mensagem de erro informando que o campo é obrigatório.

### - **RF-03 - Logout**

**Story:** Como usuário autenticado no sistema, quero fazer logout, para poder encerrar minha sessão.

**Critérios de aceitação:**

- Dado que estou autenticado, eu clico no botão fazer logout, o sistema encerra minha sessão e redireciona para a página home do site (Deve limpar os cookies, dados de autenticação e invalidar tokens).
- Dado que fiz logout, tento acessar uma página protegida, o sistema me redirecionará para a página de login

### - **RF-04 - AI API KEY**

**Story:** Como usuário autenticado, quero cadastrar minha API Key para poder utilizar as funcionalidades de IA do Memovox.

**Critérios de aceitação**
- Dado que estou nas configurações do meu perfil, seleciono a opção de "Configurar AI API Key", eu insiro a API key válida do Gemini e clico em salvar, após o sistema emite uma mensagem de validado e salva a configuração.
- Dado que estou nas configurações do meu perfil, seleciono a opção de "Configurar AI API Key", insiro uma API Key inválida ou de outra AI, clico e salvar, então o sistema valida a key e emite um erro informando que aquela Key é inválida e que somente suporta Keys do Gemini.
- Dado que salvei uma key válida, então ela aparece mascarada na tela (sk-******) e posso remover quando quiser.
- Dado que quero remover uma Key, eu clico no botão remover, o sistema emite uma mensagem de confirmação, eu confirmo e então o sistema mostra uma mensagem de remoção concluída e limpa o campo de API Key.

### - **RF-05 - Criar Deck**

**Story:** Como usuário autenticado, quero criar um deck, para organizar minhas palavras por tema e estudar.

**Critérios de aceitação**
- Dado que estou na tela de Decks, clico no botão de criar deck, insiro o nome e descrição do Deck e salvo, então o sistema emite uma mensagem de deck criado e o deck aparece na lista com tag de novo(tag visivel até 24h).
- Dado que eu estou na tela de Decks, clico para criar e não insiro o nome e descrição, o sistema emite uma mensagem de erro apenas para o nome.
- Dado que eu criei um deck, o sistema volta para a tela de listagem de decks com o deck criado na primeira posição.

### - **RF-06 - List Decks**

**Story:** As an authenticated user, I want to see my deck list, so that I can choose which one to study.

**Acceptance criteria**
- Given that I have created decks, when I access the decks screen, then I see each deck with its name, description, card count and whether the study session was completed today.
- Given that I have no decks, when I access the decks screen, then I see a message and a button to create my first deck.
