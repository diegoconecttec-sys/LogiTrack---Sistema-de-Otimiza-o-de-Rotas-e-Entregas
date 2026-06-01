# ADR 0003 – Modelo de Comunicação

## Status

Aceito

## Contexto

O sistema LogiTrack foi projetado como um Monolito Modular com Arquitetura Hexagonal. Neste estágio do projeto, a comunicação entre módulos ocorre internamente e de forma síncrona. Entretanto, existe a necessidade futura de suportar processamento assíncrono para eventos de rastreamento e atualização de entregas.

## Decisão

Adotar comunicação síncrona via HTTPS/REST na versão inicial do sistema, mantendo a arquitetura preparada para evolução futura para comunicação orientada a eventos utilizando Kafka.

## Alternativas Consideradas

### Comunicação Assíncrona desde o Início

Maior desacoplamento, porém aumenta significativamente a complexidade operacional.

### Comunicação Síncrona REST

Mais simples de implementar e manter no contexto atual do projeto.

### Comunicação Híbrida

Combina REST e eventos, porém adiciona complexidade prematura.

## Trade-offs

### Ganhos

* Simplicidade arquitetural
* Facilidade de implementação
* Menor custo operacional
* Facilidade de testes

### Perdas

* Menor desacoplamento
* Dependência direta entre componentes

## Consequências

A arquitetura permanecerá simples durante a fase inicial do projeto. Conforme o crescimento da aplicação, eventos relacionados a rastreamento, notificações e atualização de entregas poderão ser migrados para mensageria baseada em Kafka.

## Referências

* Martin, Robert C. Clean Architecture.
* Richards, M.; Ford, N. Fundamentals of Software Architecture.
* Pressman, R. S. Engenharia de Software: Uma Abordagem Profissional.
