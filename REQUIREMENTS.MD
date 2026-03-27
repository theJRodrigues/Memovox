# Functional Requirements
## General Rules
- All features require authenticated user unless stated otherwise.

## Auth

### **RF-01 - Sign Up**

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

### **RF-02 - Login**

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

- Given that I am on the login page,
  when I click on "Sign in with Google" and authorize access,
  then the system authenticates me and redirects me to the dashboard.

### **RF-03 - Logout**

**Story:** As a user, I want to log out, so that I can end my session.

**Acceptance criteria:**

- Given that I am on any page,  
  when I click on the "Logout" button,  
  then the system redirects me to the landing page and clears cookies and invalidates all tokens.  

- Given that I am logged out,  
  when I try to access a protected page,  
  then the system redirects me to the login page.  

### **RF-04 - AI API KEY**

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
  

### **RF-05 - Create Deck**

**Story:** As a user, I want to create a deck so that I can organize my words by theme for studying.

**Acceptance criteria:**
- Given that I am on the decks page,  
  when I click on "Create", enter the deck name and description, and click on "Save",  
  then the system displays the new deck at the top of the list with a "New" tag (for 24 hours).  

- Given that I am on the decks page,  
  when I click on "Create" and do not enter the required deck name,  
  then the system displays an error message.  

### **RF-06 - List Decks**

**Story:** As a user, I want to see my deck list so that I can choose which one to study.

**Acceptance criteria:**

- Given that I have created decks,  
  when I access the decks page,  
  then I see each deck with its name, description, card count, and whether the study session was completed today.  

- Given that I have no decks,  
  when I access the decks page,  
  then I see a message and a button to create my first deck.  

### **RF-07 - Edit Deck**

**Story:** As a user, I want to edit my deck so that I can update its information.

**Acceptance criteria:**

- Given that I access a deck,  
  when I update the name or description and save,  
  then the deck information is updated successfully.  

- Given that I access a deck,  
  when I leave the name field empty and try to save,  
  then the system displays an error message.  

### **RF-08 - Delete Deck**

**Story:** As a user, I want to delete a deck so that I can keep my deck list organized.

**Acceptance criteria:**
- Given that I have created decks,  
  when I select one or more decks and confirm deletion,  
  then the system deletes the selected decks and all their cards.  

### **RF-09 - Create Card**

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

### **RF-10 - Edit Card**

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

### **RF-11 - Delete Card**

**Story:** As a user, I want to delete a card, so that I can keep my cards organized.

**Acceptance criteria:**

- Given that I am in a deck,  
  when I select one or more cards and confirm deletion,  
  then the system delete the selected cards.  

- Given that I am in a deck,  
  when I select one or more cards and cancel deletion,  
  then the system does not delete any cards.  

- Given that I am in a deck,  
  when I try to delete without selecting any card,  
  then the system displays an error message.  

### **RF-12 - Start Study Session**

**Story:** As a user, I want to start a study session, so that I can practice.

**Acceptance criteria:**

- Given that I am in a deck,  
  when I click on "Start Session",  
  then the system redirect me to the study page.  

- Given that I am in an empty deck,  
  when I click on "Start Session",  
  then the system displays a message instructing me to create a card.  

### **RF-13 - Check Translation**

**Story:** As a user, I want to verify if my translation is correct, so that I can learn the correct translation.

**Acceptance criteria:**

- Given that I am in a study session,  
  when I click on "Show Translation",  
  then the system displays the translation.  

### **RF-14 - Record and Check Pronunciation**

**Story:** As a user with an API Key configured, I want to record my pronunciation to verify if it is correct.

**Acceptance criteria:**

- Given that I am in a study session an API Key configured,  
  when I record my pronunciation and click on "Check Pronunciation",  
  then the system displays whether the pronunciation is correct or not.  

- Given that I do not have an API Key configured,  
  when I try to check pronunciation,  
  then the system displays an error message.  

- Given that I am a study session,    
  when I try to check pronunciation without recording audio,  
  then the system displays an error message.  

### **RF-15 - Rate Card Difficulty**

**Story:** As a user, I want to rate the difficulty of a card so that I can train the spaced repetition algorithm.

**Acceptance criteria:**

- Given that I am in a study session,  
  when I rate the card difficulty (e.g., Easy, Medium, Hard),  
  then system store the difficulty and update the next review time.  

- Given that I am in a study session,  
  when I do not rate the card and try to proceed,  
  then the system should not allow me to continue.  

### **RF-16 - Displays Basic Deck Statistics**

**Story:** As a user, I want to see the decks statistics when I access a deck so that I can track my learning progress.

**Acceptance criteria:**

- Given that I access a deck,  
  then the system should display the deck statistics at the top of the page.

- Given that I access a deck,  
  then the system should display information such as total cards, studied cards, and accuracy rate.

- Given that I access a deck without study data,  
  then the system should display a message indicating that there is no data available.
  
### **RF-17 - Displays Detailed Deck Statistics**
  
  **Story:** As a user, I want to see the detailed deck statistics when I acccess a deck, so that I can track my learning progress.
  
  **Acceptance criteria:**
  
  - Given that I am in a deck,  
    when I click on "View Detailed Statistics",  
    then the system should display detailed statistics about my study activity.  
  
  - Given that I am viewing the detailed statistics,  
    then the system should display my progress over time (e.g., cards studied per day and accuracy rate).
  
  - Given that I am viewing the detailed statistics,  
    then the system should display performance metrics such as total correct answers, total incorrect answers, and overall accuracy.
  
  - Given that I am viewing the detailed statistics,  
    then the system should display the distribution of card difficulty (e.g., Easy, Good, Hard).
  
  - Given that I am viewing the detailed statistics,  
    then the system should display the number of cards due for review.
  
  - Given that I am viewing the detailed statistics without study data,  
    then the system should display a message indicating that there is no data available.


# Non-Functional Requirement

### **RNF-01 - Performance**

- API responses must not exceed 3 seconds under normal load.    
- The application must support up to 30 requests per second. 
- The system must support at least 50 simultaneous users.  
- The application must remain available 24/7.  
- Deck list must support pagination of up to 15 items per page.  
- The page loading must not exceed 2 seconds under normal load.  

### **RNF-02 - Security**

- API Key must be encrypted using AES-256
- JWT fot stateless authentication
- OAuth2 must be supported for social loggin (Google).
- Password must be hashed using Argon2
- All comunication must use HTTPS

### **RNF-03 - Usability**

- The front-end must be responsive and support mobile and desktop screen sizes.
- The Application must be accessible exclusively via web browser, with no native mobile app.
- The application must follow WCAG 2.1 AA accessibility guidelines, including support for screen readers.

### **RNF-04 - Availability**

- When the Gemini API is unavailable, the system must display an informational message and disable AI features.
- When the user has no API key configured, the system must disable AI features and display a message explaining how to configure one.
- When an internal error occurs, the system must display a friendly error message without exposing technical details.


# Business Rules

### **RN-01 - Deck**

- The decks name is required and must have a maximum of 150 characters.
- The "New" tag must be visible for 24 hours after deck creation.
- Each user must have a maximum of 30 decks.
- If the user misses a study day, the deck must display a visual indicator in the deck encouraging the user to resume.

### **RN-02 - User**

- Email must be unique.
- Email must be valid and a maximum of 150 characters.
- Password must have a minimum of 8 characters, and a maximum of 30 characters with special characters and uppercase letters.

### **RN-03 - Study sessions**

- A deck must have at least 1 card to start a study session.
- User must give a feedback for difficulty.
- User must have an API Key configured to use the AI features.
- The pronunciation recording must have a maximum of 30 seconds.
- User must have a maximum of 3 study sessions in each deck per day.
- The study session must have a maximum of 50 cards.
- The user's streak increases by 1 for each day they complete at least one study session.
- If the user misses a day, the streak resets to zero.

### **RN-04 - Cards**

- Each deck must have a maximum of 1000 cards per deck.
- The "front" and "back" field must have a maximum of 256 characters.
- The "front" and "back" field must be required.
