# 🚚 Sistema Logístico com IA

Sistema inteligente para otimização de rotas de entrega em tempo real utilizando Inteligência Artificial.

---

## 🎯 Objetivo

O sistema tem como objetivo aumentar a eficiência operacional de empresas de logística, reduzindo custos e melhorando o tempo de entrega através de recomendações inteligentes de rotas.

---

## 🧠 Principais Funcionalidades

* 📍 Otimização de rotas com IA
* 🚛 Rastreamento de veículos em tempo real
* ⏱ Previsão de entrega (ETA)
* 📦 Gestão de entregas
* 📊 Monitoramento da frota

---

## 🏗 Arquitetura

O sistema utiliza uma abordagem:

👉 **Monolito Modular com Arquitetura Hexagonal (Ports and Adapters)**
👉 Preparado para evolução futura para microsserviços

---

## 🧩 Estrutura da Arquitetura (Simplificada)

```text
Usuário (Web/Mobile)
        ↓
     API (Backend)
        ↓
---------------------------------
| Módulos do Sistema            |
|-------------------------------|
| Entregas                      |
| Frota                         |
| Roteamento com IA             |
| Rastreamento                  |
| Usuários                      |
---------------------------------
        ↓
Banco de Dados (PostgreSQL + PostGIS)
        ↓
APIs Externas (Mapas / Trânsito)
```

---

## 📁 Estrutura do Projeto

```text
sistema-logistico-ia/
│
├── docs/                # Documentação do projeto
├── diagrams/            # Diagramas (C4, UML)
├── adrs/                # Decisões arquiteturais
│
├── backend/
│   └── modules/
│       ├── entregas/
│       ├── frota/
│       ├── roteamento-ia/
│       ├── rastreamento/
│       └── usuarios/
│
├── frontend/
│   ├── web/
│   └── mobile/
│
├── infra/               # Infraestrutura (Docker, scripts)
├── data/                # Dados e modelos de IA
├── tests/               # Testes
│
└── README.md
```

---

## ⚙️ Tecnologias

* **Backend:** Node.js / Python
* **Banco de Dados:** PostgreSQL + PostGIS
* **IA:** Machine Learning
* **Frontend:** React / Mobile
* **Infraestrutura:** Docker (futuro Kubernetes)

---

## 📊 Diagramas

Os diagramas do sistema estão disponíveis em:

📁 `/diagrams`

---

## 📄 ADRs (Decisões Arquiteturais)

As decisões arquiteturais estão documentadas em:

📁 `/adrs`

---

## 🚀 Roadmap

* [x] Modelagem arquitetural
* [x] Definição de requisitos
* [x] ADRs
* [ ] Implementação backend
* [ ] Integração com IA
* [ ] Deploy

---

## 🎯 Estratégia Arquitetural

O projeto segue uma abordagem evolutiva:

✔ Começa simples (monolito modular)
✔ Permite crescimento sem retrabalho
✔ Preparado para microsserviços

---

## 👨‍💻 Autor

Diego Augusto
