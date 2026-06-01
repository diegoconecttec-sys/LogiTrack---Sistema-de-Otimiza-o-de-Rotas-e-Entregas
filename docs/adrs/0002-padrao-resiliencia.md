# ADR 0002 – Padrão de Resiliência

## Status

Aceito

## Contexto

O sistema LogiTrack depende fortemente de APIs externas para obtenção de rotas, geolocalização e informações de trânsito. A indisponibilidade desses serviços pode comprometer funcionalidades críticas como cálculo de rotas e previsão de entrega (ETA).

## Decisão

Adotar os padrões de resiliência:

* Circuit Breaker
* Retry com Backoff Exponencial
* Fallback

Esses padrões serão aplicados principalmente nas integrações com APIs externas.

## Alternativas Consideradas

### Apenas Retry

Solução simples, porém insuficiente para cenários de indisponibilidade prolongada.

### Fail Fast

Reduz consumo de recursos, porém afeta negativamente a experiência do usuário.

### Circuit Breaker + Retry + Fallback

Permite continuidade operacional mesmo em cenários de falha externa.

## Trade-offs

### Ganhos

* Maior disponibilidade do sistema
* Redução do impacto de falhas externas
* Melhor experiência para usuários

### Perdas

* Maior complexidade de implementação
* Necessidade de monitoramento adicional

## Consequências

A aplicação passa a tratar falhas como eventos esperados, aumentando a robustez da arquitetura. No futuro, poderá ser necessário complementar essa estratégia com observabilidade e monitoramento distribuído.

## Referências

* Nygard, Michael. Release It!
* Pressman, R. S. Engenharia de Software: Uma Abordagem Profissional.
