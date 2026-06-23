# 🗺️ Roadmap — SmartSignal

Este documento descreve a evolução planejada do SmartSignal, do protótipo de validação
até um produto consolidado no mercado. As fases são sequenciais em prioridade, mas podem
se sobrepor conforme aprendizados de cada etapa.

> **Princípio que guia todas as fases:** o app **nunca controla o veículo** — apenas
> orienta, de forma segura e não-intrusiva. Cada decisão de produto é avaliada por
> *reduz distração ou aumenta?* antes de ser implementada.

---

## ✅ Fase 0 — Protótipo de validação *(concluída / em andamento)*

Versão web rodando via GitHub Pages, usada para testar a lógica central na rua.

- [x] Orientação de ritmo (MANTENHA / ACELERE / NÃO ACELERA) com GPS real
- [x] Cadastro manual de semáforos pelo próprio usuário
- [x] Sincronização e recalibração de ciclo de cada farol
- [x] Visão de carro + smartwatch lado a lado
- [x] Armazenamento local no aparelho
- [ ] **Validação em rota real, no dia a dia** — coletar a percepção de uso e medir se a
      orientação acerta o verde de forma consistente

**Objetivo da fase:** provar que a ideia funciona e é útil na prática, antes de investir
em desenvolvimento nativo.

---

## 📱 Fase 1 — Aplicativo instalável (mobile + wearable)

Transformar o protótipo validado em um app nativo, baixável e com boa performance.

- [ ] Migração para **React Native + Expo** (base de código única para iOS e Android)
- [ ] App instalável na **Google Play** e **App Store**
- [ ] GPS contínuo em segundo plano, com baixo consumo de bateria
- [ ] Versão para **smartwatch** (Wear OS e Apple Watch), com sincronização ao celular
- [ ] Início e fim automáticos da sessão de direção (entra ao detectar movimento, sai ao parar)
- [ ] Onboarding e fluxo de permissões (GPS, notificações, movimento)
- [ ] Modo Carro e modo Moto, com interface otimizada para cada um

**Objetivo da fase:** entregar uma experiência de produto real, instalável, que funcione
sem depender do navegador.

---

## 🌐 Fase 2 — Base de dados colaborativa e validável

O maior diferencial e também o maior desafio técnico: sair do cadastro individual para
uma rede onde os semáforos são **compartilhados e validados entre usuários**.

### Lógica de validação coletiva
- [ ] Um usuário cadastra um semáforo; outros que passam pelo mesmo ponto **confirmam ou corrigem** os tempos
- [ ] Sistema de **confiança/reputação** do dado: quanto mais validações independentes, mais confiável o semáforo é considerado
- [ ] Detecção de divergência: se vários usuários reportam tempos diferentes, o app sinaliza que o farol precisa de recalibração coletiva
- [ ] Atualização do ciclo conforme **faixa de horário** (manhã/tarde/noite costumam ter tempos diferentes)

### Infraestrutura
- [ ] Backend com **Supabase + PostGIS** (banco geográfico para consultas do tipo "semáforos próximos a esta coordenada")
- [ ] Sincronização do dado local com a nuvem, com funcionamento offline como fallback

### 🔒 Cibersegurança *(tópico crítico desta fase)*
A base colaborativa abre superfície para abuso, e dados ruins podem gerar orientação
perigosa ao volante. A segurança não é um item à parte — é requisito de toda a Fase 2.

- [ ] **Validação de integridade do dado**: impedir que um usuário mal-intencionado injete tempos falsos que prejudiquem outros motoristas
- [ ] **Anti-spam / anti-bot**: evitar cadastros em massa automatizados que poluam a base
- [ ] **Autenticação segura** dos usuários e proteção de credenciais
- [ ] **Privacidade e LGPD**: dados de localização são sensíveis — definir o que é coletado, anonimização de trajetos, e consentimento claro
- [ ] **Rate limiting e auditoria**: limitar frequência de escrita e manter rastro de quem alterou cada dado
- [ ] **Criptografia** dos dados em trânsito e em repouso

**Objetivo da fase:** uma base de semáforos que se mantém atualizada sozinha, com a
comunidade, de forma confiável e segura — sem depender só de dados oficiais que muitas
cidades ainda não disponibilizam.

---

## 🎨 Fase 3 — Ergonomia, usabilidade e experiência

Refinar o uso para que o app seja seguro e agradável durante a condução real.

- [ ] Estudo de usabilidade ao volante (legibilidade sob sol, vibração, uso de relance)
- [ ] Alvos de toque grandes e interface que **nunca exige interação em movimento**
- [ ] Alertas por voz, bipe e vibração configuráveis separadamente
- [ ] Modo noturno automático
- [ ] Mapa visual para cadastrar e visualizar os semáforos da rota
- [ ] Acessibilidade (contraste, tamanho de fonte, daltonismo)
- [ ] Resumo de viagem com dados reais (economia, faróis verdes pegos, tempo poupado)

**Objetivo da fase:** que dirigir com o app seja mais seguro e fluido do que sem ele —
nunca o contrário.

---

## 🚦 Fase 4 — Dados oficiais e parcerias

Complementar (ou superar) a base colaborativa com dados em tempo real das cidades.

- [ ] Integração com feeds municipais de semáforos onde existirem (ex.: padrão **SPAT/MAP — SAE J2735** de V2I)
- [ ] Conversas com autoridades de trânsito (ex.: **CET-SP**, Curitiba)
- [ ] Avaliação de integração com plataformas de navegação (Google Maps Platform, Waze)
- [ ] Programas de apoio: **Waze for Cities**, **Google for Startups**

**Objetivo da fase:** precisão máxima onde houver infraestrutura, mantendo a base
colaborativa onde não houver.

---

## 📈 Fase 5 — Sustentabilidade e proteção do negócio

Garantir que o projeto se sustente e esteja protegido.

- [ ] Registro de software (**e-Software / INPI**) e registro de **marca**
- [ ] Definição do modelo de monetização (freemium, parcerias, B2G com prefeituras)
- [ ] Métricas de impacto comprovado (economia de combustível, redução de CO₂) como argumento de valor

**Objetivo da fase:** transformar o protótipo validado em um negócio viável e defensável.

---

### Como ler este roadmap
- `[x]` concluído · `[ ]` pendente
- As fases indicam **ordem de prioridade**, não prazos fixos
- Cada fase só avança com aprendizado da anterior — evitar construir o que ainda não foi validado
