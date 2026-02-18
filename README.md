# 📅 Sistema de Agendamento de Horários

API REST desenvolvida com Java 21 e Spring Boot para gerenciamento de agendamentos de serviços, permitindo controle completo de horários com validação de conflitos para evitar sobreposição.

Projeto focado em boas práticas de backend, separação de camadas e aplicação de regras de negócio.

---

## 🚀 Tecnologias Utilizadas

- Java 21
- Spring Boot
- Spring Data JPA
- Hibernate
- H2 Database
- Lombok
- Maven

---

## 🏗️ Arquitetura

O sistema segue o padrão:

Controller → Service → Repository → Database

- Controller → Exposição dos endpoints REST
- Service → Regras de negócio
- Repository → Acesso ao banco via JPA
- Entity → Mapeamento da tabela

---

## 📌 Funcionalidades

✔ Criar agendamentos  
✔ Buscar agendamentos por data  
✔ Alterar agendamentos  
✔ Remover agendamentos  
✔ Validação de conflito de horário  
✔ Persistência automática com JPA  

---

## 📡 Endpoints

### Criar Agendamento

POST /agendamentos

{
  "servico": "Unhas",
  "profissional": "Manicure",
  "dataHoraAgendamento": "2026-02-18T16:00:00",
  "cliente": "Ana Karine",
  "telefoneCliente": "98989898999"
}

---

### Buscar Agendamentos por Dia

GET /agendamentos?data=2026-02-18

---

### Alterar Agendamento

PUT /agendamentos?cliente=Ana Karine&dataHoraAgendamento=2026-02-18T16:00:00

---

### Deletar Agendamento

DELETE /agendamentos?cliente=Ana Karine&dataHoraAgendamento=2026-02-18T16:00:00

---

## 🗄️ Banco de Dados

Banco em memória H2 para desenvolvimento.

Console:
http://localhost:8080/h2-console

JDBC URL:
jdbc:h2:mem:agendamentos-db

Usuário:
sa

Senha:
(vazio)

---

## ▶️ Como Executar

1. git clone https://github.com/seu-usuario/agendador-horarios.git
2. cd agendador-horarios
3. ./mvnw spring-boot:run

Ou execute pela sua IDE.

---

## 📚 Regras de Negócio

- Cada agendamento possui duração padrão de 1 hora.
- Não é permitido agendar dois serviços no mesmo horário.
- A busca por dia considera o intervalo de 00:00 até 23:59:59.

---

## 👨‍💻 Autor

Marcos Felipe Sousa dos Santos
