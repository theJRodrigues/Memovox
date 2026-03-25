# Requisitos Funcionais
## General Rules
- All features require authenticated user unless stated otherwise.

## Auth

### - **RF-01 - Sign Up**

**Story:** As a guest, I want to create an account, so that I can access the Memovox to start studying languages.

**Acceptance criteria:**

- Given that I am on the create account page,
  when I fill in my name, valid email, and valid password and click on "Create",
  then the system sends a verification email.

- Given that I am on the create account page, 
  when I do not fill in any required field and click on "Create",
  then the system displays an error message.

- Given that I am on the create account page,
  when I enter an email that is already in use,
  then the system sends an alert email informing that someone attempted to create  an account using this address.

### - **RF-02 - Login**

**Story:** As a User, I want to login, so that I can access my decks and study.

**Acceptance criteria:**

- Given that I am on the login page,
  when I fill in a valid and verified email and password,
  then the system redirects to the Dashboard.

- Given that I am on the login page,
  when I fill in an invalid email or invalid password, 
  then the system displays an error message(do not specify which one is invalid).

- Given that I am on the login page,
  when I fill in an unverified email,
  then the system displays a warning to verify my email.

- Given that I am on the login page,
  when I do not fill in email or password,
  then the system displays an error message.

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

### - **RF-07 - Edit Deck**

**Story:** As an authenticated user, I want to edit my deck, so that I can update the information of the deck, like name and description.

**Acceptance criteria**
- Given that I access a deck, when I update the name or description and save, then the deck information is updated successfully.
- Given that I access a deck, when I edit and the name's blank, the system displays an error message.

### - **RF-08 - Delete Deck**

**Story:** As an authenticated user, I want to delete a deck, so that I can keep my deck list organized.

**Acceptance criteria**
- Given that I have created decks, I select the decks that I want to delete, then the system display a confirmation message and delete all the selected decks and its cards.
