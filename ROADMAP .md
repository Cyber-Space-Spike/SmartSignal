# 🗺️ Roadmap — SmartSignal

Evolução planejada do SmartSignal, do protótipo atual até um produto completo.
As fases indicam ordem de prioridade, não prazos fixos — cada uma avança com o
aprendizado da anterior.

> **Princípio que guia o projeto:** o app **nunca controla o veículo** — apenas orienta,
> de forma segura e não-intrusiva. Toda decisão de produto passa antes pela pergunta:
> *isso reduz a distração ao volante, ou aumenta?*

---

## ✅ Fase 0 — Protótipo de validação *(em andamento)*

Versão web rodando no navegador, usada para testar a lógica central na rua.

- [x] Orientação de ritmo (MANTENHA / ACELERE / NÃO ACELERA) com GPS real
- [x] Cadastro manual de semáforos pelo próprio usuário
- [x] Sincronização e recalibração de ciclo de cada farol
- [x] Visão de carro + smartwatch lado a lado
- [x] Armazenamento local no aparelho
- [ ] Validação em rota real, no dia a dia

**Objetivo:** provar que a ideia funciona e é útil na prática.

---

## 📱 Fase 1 — Aplicativo instalável (mobile + wearable)

Transformar o protótipo em um app nativo, baixável e com boa performance.

- [ ] App instalável para **Android** e **iOS**
- [ ] Versão para **smartwatch** (Wear OS e Apple Watch), sincronizada ao celular
- [ ] GPS contínuo em segundo plano, com baixo consumo de bateria
- [ ] Início e fim automáticos da sessão de direção
- [ ] Onboarding e fluxo de permissões
- [ ] Modo Carro e modo Moto

**Objetivo:** uma experiência de produto real, que funcione sem depender do navegador.

---

## 🌐 Fase 2 — Base de dados colaborativa e validável

Sair do cadastro individual para uma rede onde os semáforos são compartilhados e
validados entre usuários.

- [ ] Usuários **confirmam ou corrigem** os tempos de semáforos cadastrados por outros
- [ ] Sistema de **confiança do dado**: mais validações independentes = mais confiável
- [ ] Detecção de divergência e necessidade de recalibração coletiva
- [ ] Ajuste do ciclo conforme faixa de horário (manhã/tarde/noite)
- [ ] Sincronização com a nuvem e funcionamento offline como fallback

### 🔒 Cibersegurança *(requisito central desta fase)*
A base colaborativa exige segurança rigorosa — dados ruins podem gerar orientação
perigosa ao volante.

- [ ] Validação de integridade do dado contra injeção de informação falsa
- [ ] Proteção anti-spam e anti-bot
- [ ] Autenticação segura dos usuários
- [ ] Privacidade e conformidade com a **LGPD** (dados de localização são sensíveis)
- [ ] Criptografia dos dados em trânsito e em repouso

**Objetivo:** uma base de semáforos que se mantém atualizada com a comunidade, de forma
confiável e segura.

---

## 🎨 Fase 3 — Ergonomia, usabilidade e experiência

Refinar o uso para que o app seja seguro e agradável durante a condução real.

- [ ] Legibilidade sob sol e vibração; uso de relance
- [ ] Interface que **nunca exige interação em movimento**
- [ ] Alertas por voz, bipe e vibração configuráveis
- [ ] Modo noturno automático
- [ ] Mapa visual para cadastrar e ver os semáforos da rota
- [ ] Acessibilidade (contraste, tamanho de fonte, daltonismo)
- [ ] Resumo de viagem com dados reais

**Objetivo:** que dirigir com o app seja mais seguro e fluido do que sem ele.

---

### Como ler este roadmap
- `[x]` concluído · `[ ]` pendente
- As fases indicam ordem de prioridade, não prazos fixos
