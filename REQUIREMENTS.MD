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

**Story:** As a user, I want to log out, so that I can end my session.

**Critérios de aceitação:**

- Given that I am on any page,
  when I click on the "Logout" button,
  then the system redirects me to the lading page (clear the cookies and invalidates all tokens).

- Given that I am logged out, 
  when I try to access any protected page,
  then the system redirects me to the login page.

### - **RF-04 - AI API KEY**

**Story:** As a user, I want to configure my API Key, so that I can use Memovox AI features.

**Critérios de aceitação**

- Given that I am on the AI settings page in my profile,
  when I enter a valid Gemini API key and click on "Save",
  then the system validate the key, stores IT securely, and displays a success message. 

-Given that I am on the AI settings page in my profile,
 when I enter a invalid API Key and click on "Save",
 then the system displays an error message indicating that the key is invalid.
 
- Given that I have a saved API key,
  when I view the API Key settings,
  then the system display the key in a maskared formar(e.g., sk-******).

- Given that I have a saved API key,
  when I click on "Remove",
  then the system displays a confirmation message, and when i confirm, the system deletes the key and clears the field.
  

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

### - **RF-09 - Create Card**

**Story:** As a User, I want to create a card in the deck, so that I can study the words.

**Acceptance criteria:**
- Given that I am in the deck and have an API key,
  when I fill in the word and translation, 
  then the system creates the card and generates a context phrase automatically.

- Given that I am in the deck and have no API key,
  when I fill in the word and translation,
  then the system creates the card and do not generates a context phrase.

- Given that I am in the deck,
  when I do not fill in the word and translation,
  then the system displays an error message.
