# Memovox

![Status](https://img.shields.io/badge/status-em%20desenvolvimento-yellow)
![License](https://img.shields.io/badge/license-MIT-green)
![Java](https://img.shields.io/badge/Java-21-orange)
![Angular](https://img.shields.io/badge/Angular-17+-red)

[📖 Requirements](./REQUIREMENTS.MD) · 
[🐛 Issues](https://github.com/TheJRodrigues/memovox/issues)

> App gratuito e open source focado em memorização de idiomas, com interface simples e feedback de pronúncia por IA — sem complexidade, sem mensalidade.

---

## O Problema

Apps populares de aprendizado de idiomas têm limitações que frustram quem estuda de forma séria:

| App | Ponto Forte | Ponto Fraco |
|-----|-------------|-------------|
| Anki | Gratuito, leve, muitas funcionalidades | Interface antiga, complexo, generalizado |
| Duolingo | Gamificação, muitos idiomas | Conteúdos genéricos, funcionalidades pagas |

**Memovox** resolve isso com uma proposta direta: flashcards focados em idiomas, repetição espaçada com o algoritmo SM-2, feedback de pronúncia via IA e uma interface moderna — sem pagar mensalidade.

---

## Para quem é

**Carlos, 28 anos** — profissional que precisa aprender inglês para uma promoção. Estuda no celular em momentos livres, em sessões curtas. Desiste de apps por serem complexos ou caros.

---

## Funcionalidades planejadas

- **Autenticação completa** — cadastro com verificação de e-mail, login, logout com invalidação de token
- **Modelo BYOK (Bring Your Own Key)** — usuário cadastra sua própria API Key do Gemini nas configurações; a key é armazenada de forma segura e exibida mascarada
- **Criação e organização de Decks** — decks temáticos com nome e descrição, listagem com tag de "novo" nas primeiras 24h
- **Modo de estudo com repetição espaçada** — algoritmo SM-2 para agendamento inteligente de revisões
- **Feedback de pronúncia via IA** — reconhecimento de voz pelo navegador + análise e feedback da IA
- **Sugestão de frases de exemplo** — IA gera frases contextuais para cada palavra do deck
- **Estatísticas de progresso** — streak de dias, taxa de acerto por sessão, palavras memorizadas, evolução de pronúncia

---

## Stack

### Back-End
- Java 21
- Spring Boot 3.3
- Spring Security + JWT (autenticação stateless)
- Spring Data JPA + Hibernate
- Flyway (migrações de banco)
- RabbitMQ (processamento assíncrono de áudio)

### Front-End
- Angular 17 (Standalone Components, Signals)
- Angular Material + Material Design 3

### Landing Page
- Astro (SSG, SEO, Islands Architecture)

### Banco de Dados
- PostgreSQL

### IA
- Google Gemini API (via API Key do próprio usuário)

### Infra
- Docker + Docker Compose
- GitHub Actions (CI/CD)

---

## Arquitetura


```mermaid
graph TD

  A[User] -->  B1[Landing Page \n (Astro | SSG)]
  A -->  B2[Angular SPA \n (Angular 21)]
  
  C[Spring API \n (REST | JWT | oAuth2 | Argon2)]
  
  B1 --> C
  B2 --> C
  
  C --> D[PostgreSQL]
  C --> E[RabbitMQ \n (Pronunciation)] --> G[Gemini API]
  C --> F[Gemini API \n (Context phrase)]
```

O processamento de áudio é assíncrono: o front-end envia o áudio, a API publica uma mensagem no RabbitMQ e um worker consome e envia para a IA — evitando bloqueio na requisição principal.

---

## Status do projeto

| Módulo | Status |
|--------|--------|
| Documentação e arquitetura | ✅ Concluído |
| Autenticação (RF-01 a RF-03) | 🔄 Em desenvolvimento |
| Gestão de API Key (RF-04) | 📋 Planejado |
| Decks (RF-05+) | 📋 Planejado |
| Modo de estudo SM-2 | 📋 Planejado |
| Feedback de pronúncia | 📋 Planejado |

---

## Como rodar (em breve)

Em breve — primeira versão funcional em desenvolvimento.
Acompanhe o progresso nas [issues](https://github.com/seu-usuario/memovox/issues).

---

## Métricas de sucesso

- Dias consecutivos de estudo (streak)
- Taxa de acerto por sessão
- Total de palavras memorizadas
- Progresso de pronúncia ao longo do tempo

---

## Licença

MIT — open source, livre para usar e contribuir.
