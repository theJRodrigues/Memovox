# SYSTEMS DIAGRAM

```mermaid
graph TD

  A[User] -->  B1[Landing Page \n (Astro - SSG)]
  A -->  B2[Angular SPA \n (Angular 21)]
  
  C[Spring API \n (REST - JWT - oAuth2 - Argon2)]
  
  B1 --> C
  B2 --> C
  
  C --> D[PostgreSQL]
  C --> E[RabbitMQ \n (Pronunciation)] --> G[Gemini API]
  C --> F[Gemini API \n (Context phrase)]
```
