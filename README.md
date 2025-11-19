👥 Integrantes da Equipe
Nome	RM
Diogo Julio - RM553837
Jonata Rafael - RM552939 	


# 📚 SkillUp API  
API desenvolvida como parte da Global Solution FIAP — Engenharia de Software.  
A aplicação simula uma plataforma de *Upskilling* para 2030, oferecendo trilhas de aprendizado e gestão de usuários com base em competências.

---

## 🚀 Tecnologias Utilizadas

- **Java 17**
- **Spring Boot 3**
- **Spring Web**
- **Spring Data JPA**
- **Spring Validation**
- **Spring Security (padrão do projeto, modo básico)**
- **H2 Database (modo arquivo)**
- **Flyway (migrations)**
- **Maven**
- **Postman (testes)**

---

## 🏗 Arquitetura do Projeto

src/main/java/com.fiap.skillup.skillup
├── controller → Controllers REST
├── domain → Entidades JPA
├── dto → Objetos de Transferência de Dados
├── exception → Exceções + Handler Global
├── repository → Interfaces JpaRepository
├── service → Regras de negócio
└── SkillupApplication.java

Banco versionado com **Flyway**:

src/main/resources/db/migration
├── V1__create_tables.sql
└── V2__insert_seeds.sql

---

## 🗄 Banco de Dados (H2)

A aplicação utiliza H2 em **modo arquivo**, portanto os dados **persistem entre execuções**.

### 🔗 Console H2
Após iniciar o projeto, acessar:

👉 http://localhost:8080/h2-console

**Configuração de conexão:**

| Campo | Valor |
|------|-------|
| JDBC URL | `jdbc:h2:./data/skillup` |
| User | `sa` |
| Password | *(vazio)* |

---

## 🧭 Endpoints da API

### 📘 Trilhas (`/trilhas`)
| Método | Endpoint | Descrição |
|--------|----------|------------|
| GET | `/trilhas` | Lista todas as trilhas |
| GET | `/trilhas/{id}` | Busca trilha por ID |
| POST | `/trilhas` | Cria nova trilha |
| PUT | `/trilhas/{id}` | Atualiza trilha |
| DELETE | `/trilhas/{id}` | Remove trilha |

**Exemplo de payload:**
```json
{
  "nome": "Trilha de Inteligência Artificial",
  "descricao": "Aprendizado focado em IA aplicada",
  "nivel": "AVANCADO"
}


👤 Usuários (/usuarios)
Método	Endpoint	Descrição
GET	/usuarios	Lista todos os usuários
GET	/usuarios/{id}	Busca usuário por ID
POST	/usuarios	Cadastra usuário
PUT	/usuarios/{id}	Atualiza usuário
DELETE	/usuarios/{id}	Remove usuário

Exemplo de payload:

{
  "nome": "Jonata Rafael",
  "email": "jonata@email.com",
  "idade": 19
}

Tratamento Global de Erros

A API possui um @RestControllerAdvice que retorna erros em JSON no padrão:

{
  "status": 400,
  "message": "Campo nome é obrigatório",
  "timestamp": "2025-11-17T19:01:46.5649706"
}
Erros tratados:

MethodArgumentNotValidException → 400

UsuarioNaoEncontradoException e TrilhaNaoEncontradaException → 404

Exceções inesperadas → 500

🧬 Seeds (dados iniciais)

Na migration V2__insert_seeds.sql, são criados:

Trilhas:

Inteligência Artificial

Ciência de Dados

Soft Skills

Programação

Usuário inicial
(com dados mínimos para testes)

▶ Como Rodar o Projeto
1️⃣ Clonar o repositório
git clone https://github.com/SEU_USUARIO/skillup.git
cd skillup

2️⃣ Rodar com Maven
mvn spring-boot:run


OU, via IntelliJ/Eclipse:
Executar a classe:

SkillupApplication.java

3️⃣ Acessar a API
http://localhost:8080

4️⃣ Acessar Console H2
http://localhost:8080/h2-console

🧪 Testes com Postman

Requisições prontas recomendadas:

GET http://localhost:8080/trilhas

POST http://localhost:8080/trilhas

Body → raw → JSON

DELETE http://localhost:8080/trilhas/1

GET http://localhost:8080/usuarios

👥 Integrantes da Equipe
Nome	RM
Diogo Julio - RM553837
Jonata Rafael - RM552939 	


🎯 Objetivo da Solução (Tema 2030)

O SkillUp é uma solução de Upskilling voltada para o futuro do trabalho até 2030.
A plataforma busca:

Desenvolver competências digitais avançadas

Facilitar aprendizado contínuo

Mapear habilidades chave

Criar trilhas personalizadas
