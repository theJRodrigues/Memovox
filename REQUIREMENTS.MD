# Requisitos Funcionais
## General Rules
- All features require authenticated user unless stated otherwise.

## Auth

### - **RF-01 - Sign Up**

**Story:** As a guest, I want to create an account, so that I can access Memovox to start studying languages.

**Acceptance criteria:**

- Given that I am on the create account page,  
  when I fill in my name, a valid email, and a valid password and click on "Create",  
  then the system sends a verification email.  

- Given that I am on the create account page,  
  when I do not fill in any required field and click on "Create",  
  then the system displays an error message.  

- Given that I am on the create account page,  
  when I enter an email that is already in use,  
  then the system sends a security alert email notifying that a signup attempt was made using this address.  

### - **RF-02 - Login**

**Story:** As a user, I want to log in so that I can access my decks and study.

**Acceptance criteria:**

- Given that I am on the login page,  
  when I enter a valid and verified email and password,  
  then the system redirects me to the dashboard.  

- Given that I am on the login page,  
  when I enter an invalid email or password,  
  then the system displays a generic error message (without specifying which field is incorrect).  

- Given that I am on the login page,  
  when I enter an unverified email,  
  then the system displays a warning asking me to verify my email.  

- Given that I am on the login page,  
  when I do not enter an email or password,  
  then the system displays an error message.  

### - **RF-03 - Logout**

**Story:** As a user, I want to log out, so that I can end my session.

**Acceptance criteria:**

- Given that I am on any page,  
  when I click on the "Logout" button,  
  then the system redirects me to the landing page and clears cookies and invalidates all tokens.  

- Given that I am logged out,  
  when I try to access a protected page,  
  then the system redirects me to the login page.  

### - **RF-04 - AI API KEY**

**Story:** As a user, I want to configure my API Key, so that I can use Memovox AI features.

**Acceptance criteria**

- Given that I am on the AI settings page in my profile,  
  when I enter a valid Gemini API key and click on "Save",  
  then the system validates the key, stores it securely, and displays a success message.  

- Given that I am on the AI settings page in my profile,  
  when I enter an invalid API key and click on "Save",  
  then the system displays an error message indicating that the key is invalid.  
 
- Given that I have a saved API key,  
  when I view the API key settings,  
  then the system displays the key in a masked format (e.g., AIza-******).  

- Given that I have a saved API key,  
  when I click on "Remove",  
  then the system displays a confirmation message,  
  and when I confirm, the system deletes the key and clears the field.  
  

### - **RF-05 - Create Deck**

**Story:** As a user, I want to create a deck so that I can organize my words by theme for studying.

**Accpetance criteria**
- Given that I am on the decks page,  
  when I click on "Create", enter the deck name and description, and click on "Save",  
  then the system displays the new deck at the top of the list with a "New" tag (for 24 hours).  

- Given that I am on the decks page,  
  when I click on "Create" and do not enter the required deck name,  
  then the system displays an error message.  

### - **RF-06 - List Decks**

**Story:** As a user, I want to see my deck list so that I can choose which one to study.

**Acceptance criteria**

- Given that I have created decks,  
  when I access the decks page,  
  then I see each deck with its name, description, card count, and whether the study session was completed today.  

- Given that I have no decks,  
  when I access the decks page,  
  then I see a message and a button to create my first deck.  

### - **RF-07 - Edit Deck**

**Story:** As a user, I want to edit my deck so that I can update its information.

**Acceptance criteria**

- Given that I access a deck,  
  when I update the name or description and save,  
  then the deck information is updated successfully.  

- Given that I access a deck,  
  when I leave the name field empty and try to save,  
  then the system displays an error message.  

### - **RF-08 - Delete Deck**

**Story:** As a user, I want to delete a deck so that I can keep my deck list organized.

**Acceptance criteria**
- Given that I have created decks,  
  when I select one or more decks and confirm deletion,  
  then the system deletes the selected decks and all their cards.  

### - **RF-09 - Create Card**

**Story:** As a user, I want to create a card in a deck so that I can study words.

**Acceptance criteria:**
- Given that I am in a deck and have an API key,  
  when I enter a word and its translation,  
  then the system creates the card and automatically generates a contextual sentence.  

- Given that I am in a deck and do not have an API key,  
  when I create a card, enter a value ,  
  then the system creates the card without generating a contextual sentence.  

- Given that I am in a creation card,  
  when I do not enter the word or its translation,  
  then the system displays an error message.

### - **RF-10 - Edit Card**

**Story:** As a user, I want to edit a card, so that I can keep my cards updated.

**Acceptance criteria:**
- Given that I am editing a card,
  when I update only the "front" or only the "back" field and click on "Save",
  then the system updates the card successfully.

- Given that I am editing a card,
  when I click on "Edit Card", do not enter a value in the front or back field and click on "Save",
  then the system displays an error message.

- Given that I am editing a card,
  when I click on "Cancel",
  then the system discards the changes.

### - **RF-11 - Delete Card**

**Story:** As a user, I want to delete a card, so that I can keep my cards organized.

- Given that I am in a deck,
  when I select one or more cards and confirm deletion,
  then the system delete the selected cards.

- Given that I am in a deck,
  when I select one or more cards and cancel deletion,
  then the system not delete any cards.

- Given that I am in a deck,
  when I try to delete without selecting any card,
  then the system displays an error message.

### - **RF12 - Start Study Session**

**Story:** As a user, I want to start a study session, so that I can practice.

- Given that I am in a deck,
  when I click on "Start Session",
  then the system redirect me to the study page.

- Given that I am in an empty deck,
  when I click on "Start Session",
  then the system displays a message instructing me to create a card.
