# 🎮 FIAP Cloud Games - Infraestrutura e Orquestração

Repositório central responsável pela orquestração, configuração de contêineres e deploy no Kubernetes para o ecossistema de microsserviços da FIAP Cloud Games.

## 🏗️ Arquitetura

O ecossistema é composto por quatro microsserviços independentes, orquestrados via eventos:
* **UsersAPI:** Cadastro e Autenticação (JWT).
* **CatalogAPI:** Gestão de jogos e iniciação de compras (CQRS com EF Core + Dapper).
* **PaymentsAPI:** Processamento de pagamentos.
* **NotificationsAPI:** Envio de e-mails assíncronos.

**Stack de Infraestrutura:**
* **Mensageria:** RabbitMQ (ou Kafka) para comunicação assíncrona.
* **Cache:** Redis distribuído para alta performance.
* **Banco de Dados:** SQL Server (Abordagem híbrida / CQRS).
* **Orquestração:** Docker Compose (Local) e Kubernetes (Produção/Cluster Local).
