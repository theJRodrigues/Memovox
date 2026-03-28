# SYSTEMS DIAGRAM

```mermaid
graph TD

  A[User] -->  B1[Landing Page <br> (Astro • SSG)]
  A -->  B2[Angular SPA <br> (Angular 21)]
  
  C[Spring API <br>(REST • JWT • oAuth2 • Argon2)]
  
  B1 --> C
  B2 --> C
  
  C --> D[PostgreSQL]
  C --> E[RabbitMQ <br>(Pronounciation)] --> G[Gemini API]
  C --> F[Gemini API <br>(Context phrase)]
```
