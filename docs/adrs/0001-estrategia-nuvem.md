# ADR 0001 – Estratégia de Nuvem e Escalabilidade

## Status

Aceito

## Contexto

O projeto LogiTrack encontra-se em fase inicial (MVP), possui equipe reduzida e orçamento limitado para infraestrutura. O sistema precisa suportar rastreamento em tempo real, integração com APIs externas de mapas e crescimento gradual da base de usuários. Além disso, o time possui experiência intermediária em desenvolvimento, mas limitada em operação de clusters Kubernetes e infraestrutura distribuída.

## Decisão

Adotar uma estratégia baseada em **PaaS Gerenciado**, utilizando Railway ou Heroku para hospedagem da aplicação e Supabase para banco de dados PostgreSQL gerenciado.

A escalabilidade inicial será realizada por meio dos recursos nativos da plataforma, permitindo crescimento sem gerenciamento manual de infraestrutura.

## Alternativas Consideradas

### Opção A – PaaS Gerenciado

* Menor custo operacional
* Implantação rápida
* Escalabilidade automática

### Opção B – IaaS + Docker

* Maior controle da infraestrutura
* Maior esforço operacional
* Escalabilidade manual

### Opção C – Kubernetes (EKS)

* Escalabilidade avançada
* Alto custo financeiro
* Complexidade incompatível com o estágio atual do projeto

## Trade-offs

### Ganhos

* Redução da complexidade operacional
* Menor tempo de implantação
* Menor necessidade de equipe DevOps
* Escalabilidade automática inicial

### Perdas

* Menor controle sobre infraestrutura
* Dependência da plataforma escolhida

## Consequências

A arquitetura permanece simples e alinhada ao modelo de Monolito Modular Evolutivo. Caso a demanda cresça significativamente, será necessário reavaliar a adoção de containers e Kubernetes para permitir escalabilidade mais granular.

## Referências

* Pressman, R. S. Engenharia de Software: Uma Abordagem Profissional.
* Richards, M.; Ford, N. Fundamentals of Software Architecture.

