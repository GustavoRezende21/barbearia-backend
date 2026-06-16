# Barbearia API - Sistema de Agendamentos

Projeto desenvolvido em Java + Spring Boot para demonstrar o gerenciamento e agendamento de serviços de barbearias, contém níveis de segurança via tokens JWT. A Regra de Negócio é capaz de demonstrar o fluxo completo de agendamento de horários entre clientes e profissionais, validações de disponibilidade da agenda e controle de permissões de acesso com inicialização automática de dados (Usuário Administrador).

---

## Tecnologias Utilizadas

### Aplicação Backend
* **Java 17**
* **Spring Boot** (Spring Data JPA, Spring Web, Spring Boot DevTools, Spring Security)
* **Validation** Usada Principalmente nos DTOs para Validação dos Dados
* **Banco de Dados Postgres** - Driver do Banco de Dados Postgres
* **Springdoc OpenAPI (Swagger UI)** (Documentação de API)

### Dependências de Testes
* **JUnit Jupiter** - Framework para a Base dos Testes
* **RestAssured** - Validação e Testes Automatizados de Endpoints HTTP (API REST)
* **Hamcrest** - Biblioteca de matchers declarativos para asserções mais legíveis

---

## Regras de Negócio & Funcionalidades

### 1. Autenticação e Controle de Acesso
* O sistema possui controle de acessos baseado no perfil do usuário (Administrador, Barbeiro ou Cliente)
* O sistema utiliza um filtro de segurança que intercepta as requisições HTTP para validar o token contido no cabeçalho
* O sistema garante a criação automática de um usuário administrador padrão (admin@barbearia.com) logo na inicialização da aplicação

### 2. Catálogo de Serviços
* Cadastro, alteração e listagem dos serviços oferecidos pela barbearia.
* Controle de disponibilidade de serviços (Ativação ou Desativação)

### 3. Fluxo de Agendamento de Horários
* Permite o agendamento de horários associando de forma consistente um Cliente, Profissional e o Servico desejado
* O sistema bloqueia agendamentos duplicados para o mesmo profissional ou para o mesmo cliente no mesmo horário
* Tráfego de dados otimizado entre as camadas através de padrões **DTO (Data Transfer Objects)**

---

## Estrutura de Testes Implementados

### 1. Testes de Unidade
* Isola as camadas de serviço, testando puramente as regras de negócio e validações lógicas.

### 2. Testes de Endpoints HTTP (`TestEndpoint...`)
* Simula requisições reais HTTP para validar as respostas de cada controller

## Requisitos do Sistema

* Java 17 instalado e configurado na sua máquina
* IntelliJ Community (Recomendação de IDE para rodar o Projeto)
