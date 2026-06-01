# Software Architecture Document (SAD) – Fase 3

# LogiTrack – Sistema de Otimização de Rotas e Entregas

## 1. Visão Geral

O LogiTrack é um sistema de logística inteligente desenvolvido para otimizar rotas de entrega em tempo real, monitorar frotas e fornecer previsões de chegada (ETA) utilizando dados geolocalizados e algoritmos de recomendação.

O sistema busca reduzir custos operacionais, melhorar a eficiência logística e aumentar a satisfação dos clientes por meio de decisões baseadas em dados.

---

# 2. Objetivos de Negócio

* Reduzir o tempo médio de entrega.
* Otimizar a utilização da frota.
* Melhorar a previsibilidade das entregas.
* Fornecer rastreamento em tempo real.
* Permitir crescimento gradual da operação sem retrabalho arquitetural.

---

# 3. Requisitos Arquiteturais

## Requisitos Funcionais

* Cadastro de usuários.
* Cadastro de veículos.
* Cadastro de entregas.
* Otimização de rotas.
* Rastreamento em tempo real.
* Atualização de status.
* Previsão de entrega (ETA).
* Notificações.
* Relatórios gerenciais.

## Requisitos Não Funcionais

* Performance.
* Escalabilidade.
* Resiliência.
* Confiabilidade.
* Segurança.

---

# 4. Estilo Arquitetural

## Arquitetura Principal

Monolito Modular com Arquitetura Hexagonal (Ports and Adapters).

A arquitetura foi projetada para permitir evolução gradual para microsserviços sem necessidade de retrabalho significativo.

### Benefícios

* Baixa complexidade inicial.
* Alto desempenho.
* Facilidade de manutenção.
* Evolução incremental.

### Limitações

* Escalabilidade limitada por módulo.
* Deploy único da aplicação.

---

# 5. Visão de Containers (C4 Nível 2)

## Frontend Web/Mobile

Responsável pela interação dos usuários com o sistema.

Tecnologias previstas:

* React
* React Native

---

## Backend API

Responsável por autenticação, autorização e orquestração das regras de negócio.

Tecnologias previstas:

* Node.js
* Python (IA)

---

## Módulo de Entregas

Gerenciamento do ciclo de vida das entregas.

---

## Módulo de Frota

Controle operacional dos veículos.

---

## Módulo de Roteamento com IA

Processamento de rotas e cálculo de ETA.

---

## Módulo de Rastreamento

Recebimento de coordenadas GPS e atualização de localização.

---

## Banco de Dados

PostgreSQL + PostGIS

Responsável pelo armazenamento transacional e geoespacial.

---

## Sistemas Externos

### API de Mapas

* Google Maps
* OpenStreetMap

### Serviço de Notificações

* SMS
* Push Notification

---

# 6. Estratégia de Cloud

## Modelo Escolhido

PaaS Gerenciado

### Serviços

* Railway ou Heroku
* Supabase (PostgreSQL Gerenciado)

### Motivações

* Menor custo operacional.
* Implantação rápida.
* Escalabilidade automática.
* Adequado para MVP.

### Escalabilidade

Inicialmente vertical e automática pela plataforma.

Evolução futura:

* Docker
* Kubernetes
* Microsserviços

---

# 7. Estratégia de Resiliência

Para garantir disponibilidade e tolerância a falhas serão utilizados:

## Circuit Breaker

Proteção contra indisponibilidade de APIs externas.

## Retry com Backoff Exponencial

Nova tentativa automática em falhas transitórias.

## Fallback

Uso de dados previamente armazenados quando serviços externos estiverem indisponíveis.

---

# 8. Modelo de Comunicação

## Atual

Comunicação síncrona via HTTPS/REST.

Fluxo:

Frontend → API → Módulos Internos → Banco

## Futuro

Comunicação orientada a eventos utilizando Kafka.

Casos previstos:

* Rastreamento em tempo real.
* Notificações.
* Atualização de status.

---

# 9. Segurança

O sistema implementará:

* Autenticação JWT.
* Controle de acesso por perfil.
* Criptografia HTTPS/TLS.
* Proteção contra acesso não autorizado.
* Armazenamento seguro de credenciais.

---

# 10. Roadmap Arquitetural

## Fase Atual

* Monolito Modular
* PostgreSQL + PostGIS
* APIs REST
* PaaS Gerenciado

## Próxima Evolução

* Docker
* Mensageria Kafka
* Observabilidade

## Longo Prazo

* Microsserviços
* Kubernetes (EKS)
* Escalabilidade horizontal avançada

---

# 11. Conclusão

A arquitetura proposta para o LogiTrack equilibra simplicidade operacional, desempenho e capacidade de evolução. A combinação de Monolito Modular, Arquitetura Hexagonal e implantação em PaaS permite rápida entrega do produto e reduz custos iniciais, mantendo o sistema preparado para crescimento futuro e adoção gradual de microsserviços.
