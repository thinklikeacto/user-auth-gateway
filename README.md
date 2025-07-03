# user-auth-gateway

`user-auth-gateway` is the core service of the open-source microservices-based architecture project **Swaraj**. It combines **user management**, **authentication**, and **API gateway functionality** into a single modular NestJS application, with a clean separation of concerns so it can be split into standalone services in the future.

## 🚀 Features

### 🧑‍💼 User Management
- Create and manage user accounts
- Update user profiles
- Role-based access control (RBAC)

### 🔐 Authentication
- JWT-based login/signup
- Token validation and refreshing
- Password encryption and verification

### 🚪 API Gateway
- Routing layer for incoming requests
- Rate limiting and basic throttling
- Entry point to route traffic to other microservices (planned)

## 📁 Folder Structure

```
user-auth-gateway/
├── src/
│   ├── main.ts
│   ├── app.module.ts
│
│   ├── api/
│   │   └── v1/
│   │       ├── auth/
│   │       │   ├── auth.controller.ts
│   │       │   └── auth.routes.module.ts
│   │       ├── user/
│   │       │   ├── user.controller.ts
│   │       │   └── user.routes.module.ts
│   │       └── gateway/
│   │           └── gateway.controller.ts
│
│   ├── models/
│   │   ├── auth/
│   │   │   ├── login.dto.ts
│   │   │   ├── signup.dto.ts
│   │   │   └── auth-payload.interface.ts
│   │   ├── user/
│   │   │   ├── create-user.dto.ts
│   │   │   ├── update-profile.dto.ts
│   │   │   └── user.entity.ts
│   │   └── gateway/
│           └── gateway.config.ts
│
│   ├── repositories/
│   │   ├── auth/
│   │   │   └── auth.repository.ts
│   │   ├── user/
│   │   │   └── user.repository.ts
│   │   └── gateway/
│           └── gateway.repository.ts
│
│   ├── services/
│   │   ├── auth/
│   │   │   ├── auth.service.ts
│   │   │   ├── jwt.service.ts
│   │   │   └── password.service.ts
│   │   ├── user/
│   │   │   ├── user.service.ts
│   │   │   └── profile.service.ts
│   │   └── gateway/
│           └── gateway.service.ts
│
│   ├── middleware/
│   │   ├── auth.guard.ts
│   │   ├── roles.guard.ts
│   │   └── rate-limit.guard.ts
│
│   ├── utils/
│   │   ├── jwt.util.ts
│   │   └── constants.ts
│
│   ├── config/
│   │   ├── config.module.ts
│   │   ├── config.service.ts
│   │   └── env.validation.ts
│
├── test/
├── .env
├── tsconfig.json
├── package.json
└── README.md


```

This layout mirrors the Python microservice structure from Swaraj for consistency across services.

## 🛠️ Tech Stack

- [NestJS](https://nestjs.com/) with TypeScript
- JWT for authentication
- PostgreSQL/MongoDB (pluggable)
- `express-rate-limit` (or equivalent) for rate limiting

## 🧩 Modular Design
Each module (`user`, `auth`, `gateway`) follows its own subfolder structure under:
- `models/`
- `services/`
- `repositories/`
- `api/v1/`

This allows easy **future decoupling** into independent microservices when required.

## 📌 Getting Started

```bash
# Install dependencies
yarn install

# Run development server
yarn start:dev

# Environment configuration
cp .env.example .env
```

## 📦 Planned Enhancements
- Email/OTP verification
- Refresh token rotation
- API gateway routing to other services (notifications, ML, agentic-AI)
- Swagger/OpenAPI docs

## 🤝 Contributing
This service is part of the **Swaraj** open-source ecosystem. Contributions are welcome to improve the structure, features, and developer experience.

## 📄 License
MIT
