# SmartSignal — Protótipo Web (validação)

App que orienta o motorista sobre o ritmo de velocidade ideal para chegar ao próximo
semáforo no momento em que ele estiver **verde** — evitando aceleração desnecessária,
economizando combustível e reduzindo tempo parado no farol.

> **Regra inviolável:** o app **nunca controla o veículo**. Apenas sugere, de forma
> visual/sonora não-intrusiva, e **nunca** sugere velocidade acima do limite.

Esta é a **versão web de validação** — um único arquivo `index.html` que roda no
navegador do seu Android com **GPS real** e usa os **semáforos que você cadastrar**.
Depois de validada, migra para app baixável (React Native + Expo).

## Como usar no celular

1. Suba este repositório no GitHub e ative o **GitHub Pages** (Settings → Pages →
   Branch `main` / root). O GPS só funciona em **HTTPS**, e o Pages serve nisso.
2. Abra o link `https://SEU-USUARIO.github.io/smartsignal/` no **Chrome do Android**.
3. Aba **Semáforos**: pare perto de um farol, informe os tempos de verde/vermelho,
   marque a cor atual e toque em **Salvar semáforo aqui**.
4. Aba **Direção**: toque em **Iniciar GPS**, coloque o celular no suporte e dirija.
   O banner mostra **MANTENHA / ACELERE / NÃO ACELERA** e o relógio espelha a mesma cor.
5. Sem sair de casa? Use **Modo demonstração** para ver a lógica funcionando.

## Estrutura

- `index.html` — app completo (HTML + CSS + JS, sem dependências de build)
- Dados ficam só no aparelho (localStorage). Nada vai para servidores.

## Lógica de decisão

A cada ~200ms: calcula distância até o farol mais próximo (≤600m), a fase atual do
ciclo (verde/vermelho) e o tempo até a troca, e o tempo de chegada mantendo a velocidade.
Daí decide manter, acelerar (dentro do limite) ou aliviar para chegar no verde.

## Roadmap

- [ ] Mapa visual para cadastrar/ver semáforos (Mapbox + OSM)
- [ ] Onboarding Carro/Moto e tela de permissões
- [ ] Wear OS nativo + sync BLE
- [ ] Fonte de dados de semáforo (feeds municipais / crowdsource)
- [ ] Migração para React Native + Expo
