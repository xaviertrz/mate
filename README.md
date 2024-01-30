
# Requirements

```bash
Docker
Docker Composer
Node, Npm
```

### Local Development Setup

#### 1. Clone the Repository

To get started, clone the repository to your local machine:

```bash
git clone https://github.com/maximilianokaizen/mate
cd mate
```

#### 2. Install dependencies

```bash
npm i 
yarn i
```

#### 3. Build and Run the Services

```bash
docker-compose up --build -d
yarn i
```

#### 4. Create Database and run migrations

npx prisma init
npx prisma generate 
npx prisma migrate dev 

#### 5. Run mate with 

```bash
npm run dev
```

#### 6. Other commands

```bash
npm run build
npm run test
npm run lint
```


## CURL commands to test 

## Create User CURL

```bash
curl -X POST http://localhost:3030/v1/users -H "Content-Type: application/json" -d '{
"uuid": "",
"name": "John",
"userName": "johndoe123",
"lastName": "Doe",
"email": "johndoe@example.com",
"password": "P@ssw0rd123",
"active": true,
"createdAt": "2022-01-30T12:00:00Z"
}'
```

```bash
curl -X POST http://localhost:3030/v1/users -H "Content-Type: application/json" -d '{
"uuid": "",
"name": "Juan Maximiliano",
"lastName": "Rossi",
"userName": "maxirossi",
"email": "maximilianokaizen@gmail.com",
"password": "P@ssw0rd123",
"active": true,
"createdAt": ""
}'
```

## Get all users CURL

```bash
curl -X GET http://localhost:3030/v1/users
```

## Ger user by UUID

```bash
curl -X GET http://localhost:3030/v1/users/e2fbadaf-7f56-4a47-86d8-439e655369d8
```

## Delete user (soft delete)

```bash
curl -X DELETE http://localhost:3030/v1/users/e2fbadaf-7f56-4a47-86d8-439e655369d8
```

## Update User

```bash
curl -X PUT http://localhost:3030/v1/users/2e771f88-eff2-45da-8d39-090365dbc09d -H "Content-Type: application/json" -d '{
"name": "John",
"lastName": "Doe",
"password": "P@ssw0rd123",
"active": false
}'
```

## Auth User

```bash
curl -X POST http://localhost:3030/v1/users/authenticate -H "Content-Type: application/json" -d '{
"email": "maximilianokaizen@gmail.com",
"password": "P@ssw0rd123"
}'
```
