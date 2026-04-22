# Pre Hackverse Vector

**Projet Choisi : 4. Gestion de dépenses en groupe**

Application web de gestion de depenses en groupe, avec optimisation des remboursements.

Ce depot contient :
- un backend Spring Boot (`backend/`)
- un frontend Next.js (`frontend/Pre_Hackverse_Vector_Frontend/`)

## Fonctionnalites principales

- Gestion des groupes et des membres
- Ajout de depenses avec plusieurs modes de repartition (equitable, montant exact, parts)
- Calcul et optimisation des dettes pour minimiser les transactions
- Gestion des invitations
- API documentee via Swagger

## Stack technique

- Backend : Java 17, Spring Boot 3, Maven, JPA
- Base de donnees : H2 (par defaut), PostgreSQL (possible via variables d'environnement)
- Authentification : Spring Security + JWT
- Frontend : Next.js, React, TypeScript

## Prerequis

- Java 17+
- Node.js 18+ et npm
- Maven (ou `./mvnw` si present)

## Installation et lancement

### 1) Lancer le backend

```bash
cd backend
./mvnw spring-boot:run
```

Par defaut, l'API demarre sur `http://localhost:8080`.

Documentation Swagger :
- `http://localhost:8080/swagger-ui.html`

### 2) Lancer le frontend

Dans un autre terminal :

```bash
cd frontend/Pre_Hackverse_Vector_Frontend
npm install
npm run dev
```

Le frontend est accessible sur `http://localhost:3000`.

## Configuration backend (variables utiles)

Le backend lit les variables suivantes :

- `DB_DRIVER` (defaut: `org.h2.Driver`)
- `DB_URL` (defaut: `jdbc:h2:file:./data/debtdb;AUTO_SERVER=TRUE`)
- `DB_USERNAME` (defaut: `sa`)
- `DB_PASSWORD` (defaut: vide)
- `DDL_AUTO` (defaut: `update`)
- `MAIL_USERNAME`
- `MAIL_PASSWORD`
- `FRONTEND_BASE_URL` (defaut: `http://localhost:3000`)

## Tests

Backend (depuis `backend/`) :

```bash
./mvnw test
```

Des scripts de test supplementaires existent aussi dans `backend/` (par exemple `run_tests.sh` et `test_api_flow.sh`).

## Structure du projet

```text
Hack/
├── backend/
│   ├── src/main/java/...
│   └── src/main/resources/application.properties
└── frontend/
    └── Pre_Hackverse_Vector_Frontend/
```
