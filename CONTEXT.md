# NeatStream — Snapshot de Contexto do Projeto (v2.3.0)
**Data do Snapshot:** 12 de Setembro de 2026  
**Status do Ecossistema:** 100% Operacional, Mídias 100% Locais, Validado (HTML5/W3C) e Portável

---

## 1. Visão Geral e Proposta de Valor (Artigo FEA-USP 2026)

O **NeatStream** nasce da convergência entre consumo inteligente de entretenimento audiovisual e gestão financeira pessoal automatizada via Open Finance. A tese central apoia-se no axioma fundamental:

> *"Quando tudo é especial, nada é verdadeiramente especial. Uma decisão limpa por vez."*

### Pilares Fundamentais:
1. **Anti-Fadiga de Catálogo:** Eliminação da paralisia de escolha através de curadoria cirúrgica (máximo de 1 destaque + 3 alternativas imediatas por tela), filtros rápidos por duração de tempo (`30m`, `45-60m`, `90-110m`, `2h30+`) e ausência de *infinite scroll* na camada de descoberta.
2. **Open Finance & Auditoria de Assinaturas:** Conexão criptografada (AES-256) com leitura restrita a cobranças de streaming, traduzindo faturas indecifráveis em cartões estruturados.
3. **Pausa por Temporada & Rotação Inteligente:** Estímulo à rotação consciente de serviços conforme temporadas de séries favoritas terminam, gerando uma **economia média comprovada de R$ 526,80 por ano**.
4. **Zero Dark Patterns:** Cancelamento e pausa em 1 toque, sem cronômetros de retenção psicológica ou fluxos labirínticos.

---

## 2. Decisões de Design e UX Alinhadas via `/grill-me`

* **Direção Estética ("Cinematic FinTech"):** Híbrido entre o refinamento de mídia rica e iluminação atmosférica (estilo *Apple TV+ / A24*) e indicadores financeiros táticos e compactos (estilo *Linear / Revolut*).
* **Mídias Oficiais Locais & Vídeos em Loop (Atualização v2.3.0):**
  - Eliminação total de imagens genéricas de bancos de fotos (Unsplash).
  - Pôsteres oficiais teatrais e de séries em proporção 2:3 (`assets/posters/`) em alta resolução para 100% do catálogo.
  - Backdrops cinematográficos panorâmicos 16:9 (`assets/backdrops/`) para trailers e modais.
  - Teasers de vídeo curtos em loop contínuo (`assets/videos/dune2_teaser.mp4` e `the_bear_teaser.mp4`) com transição suave, início automático silencioso (`muted autoplay playsinline loop`) e controles de áudio (unmute) e play/pause translúcidos em vidro.
* **Landing Page (`web/landing.html`):** 
  - Redução drástica da densidade de texto descritivo.
  - Marquee duplo horizontal com pôsteres oficiais reais de alta fidelidade e aceleração por hardware.
  - Simulador tátil de rotação com 5 serviços (Disney+, Netflix, Max, Apple TV+, Prime Video) e recálculo dinâmico animado de economia anual (**R$ 526,80/ano**).
  - Bento grid de mini-interfaces para ilustrar funcionalidades de engenharia sem paredes de texto.
* **Web Dashboard (`web/dashboard_dark.html` & `web/dashboard_light.html`):**
  - *Modo Cinema Minimalista:* Substituição de tabelas extensas por um **HUD financeiro compacto** no topo com medidor radial, slider de teto orçamentário e barras de bateria de cada streaming.
  - Billboard full-bleed em proporção 16:9 (*Duna: Parte 2*) com reprodução contínua de teaser oficial em MP4 H.264, controle de áudio flutuante e botões de ação com alta visibilidade.
  - Grade 2:3 de pôsteres verticais em alta definição com zoom elástico no hover e números de ranking transparentes com contorno iluminado.
  - Leques tridimensionais expansivos de 3 pôsteres sobrepostos para curadorias comunitárias.
* **App Mobile (`mobile/hoje.html` & `mobile/carteira_dark.html`):**
  - Feed imersivo em 2 colunas estilo *Letterboxd / MUBI*, com micro-selos nos cantos dos pôsteres (`MAX`, `DISNEY+`, `APPLE`, `NETFLIX`, `PRIME`) e notas neutras (`★ 9.1`), eliminando textos redundantes.
  - Hero vertical com teaser de alta energia de *O Urso* em vídeo contínuo com botão de som e dock flutuante em cápsula de vidro escuro fosco.
  - Carteira financeira visual com barra de alocação multicor e cartões com botão de pausa em 1 toque.
* **Tipografia Unificada (100% Modernista):**
  - **Família Única:** `Plus Jakarta Sans` (pesos 300 a 800 + itálico).
  - Eliminação total de fontes legadas (*Inter*, *Sora*, *Spectral*).
  - Numerais de moedas, notas e contadores configurados com OpenType Tabular Figures (`font-feature-settings: 'tnum' 1, 'zero' 1; font-variant-numeric: tabular-nums;`) para alinhamento vertical estrito.

---

## 3. Mapa Completo de Arquivos do Ecossistema

```
Projeto App Transformação Digital/
├── CONTEXT.md                    # Este arquivo de contexto consolidado (v2.3.0)
├── DESIGN_SYSTEM.md              # Especificação formal de tokens W3C DTCG e WCAG AAA/AA
├── README.md                     # Documentação mestre da plataforma
├── tokens.json                   # Dicionário JSON de design tokens
├── index.html                    # Master Studio Hub (Emulador Mobile/Desktop + Galeria Comparativa)
│
├── assets/                       # Mídias Oficiais Locais (Zero Dependência Externa)
│   ├── posters/                  # 12 Pôsteres Oficiais Verticais 2:3 (Dune 2, The Bear, Severance, etc.)
│   ├── backdrops/                # 12 Backdrops Cinemáticos Widescreen 16:9
│   └── videos/                   # Clipes de Teaser Otimizados (Dune 2 Web, The Bear Mobile)
│
├── web/                          # Aplicação Web (Desktop & Tablet)
│   ├── landing.html              # Landing Page cinemática com marquee duplo oficial e simulador tátil
│   ├── dashboard_dark.html       # Web Dashboard em Modo Cinema com Vídeo Billboard (Tema Escuro)
│   └── dashboard_light.html      # Web Dashboard em Modo Cinema com Vídeo Billboard (Tema Claro)
│
├── mobile/                       # Aplicação Mobile (Viewport 375-430px)
│   ├── hoje.html                 # Feed Contínuo com Vídeo Hero e Grade Letterboxd/MUBI
│   ├── carteira_dark.html        # Carteira FinTech & Econômetro com barra de alocação (Tema Escuro)
│   ├── carteira_light.html       # Carteira FinTech & Econômetro (Tema Claro)
│   ├── onboarding.html           # Fluxo de conexão de contas bancárias com pôsteres 3D
│   └── celebracao.html           # Tela de celebração de economia após cancelamento
│
├── screenshots/                  # Registros visuais em alta resolução de todas as telas
└── references/                   # Referências de design e material de pesquisa
```

---

## 4. Diretrizes de Portabilidade e Execução

* **Zero Caminhos Absolutos:** Todas as ligações internas entre arquivos usam caminhos relativos (ex.: `href="web/dashboard_dark.html"` ou `src="../assets/posters/dune2.jpg"`). A pasta pode ser movida, renomeada ou clonada em qualquer computador (Windows, macOS, Linux).
* **Mídias 100% Locais:** Não há dependência de CDN de imagens externa (Unsplash removido integralmente). Todos os pôsteres, backdrops e clipes de vídeo residem fisicamente dentro do repositório (`assets/`).
* **Dependências via CDN Global:**
  - Tailwind CSS: `<script src="https://cdn.tailwindcss.com"></script>`
  - Tipografia: Google Fonts (`family=Plus Jakarta Sans`)
* **Como Executar:**
  - **Direto:** Duplo clique no arquivo `index.html` ou em qualquer arquivo HTML em qualquer navegador moderno.
  - **Servidor Local (Recomendado):** Extensão *Live Server* do VS Code ou comando `python -m http.server 8000`.

---

## 5. Histórico de Verificações Técnicas

* **Auditoria de Mídias e Links:** 100% das referências de imagem e vídeo apontam para arquivos locais existentes em disco (0 links quebrados, 0 placeholders, 0 ocorrências de `unsplash`).
* **Validação Sintática HTML5:** Todos os arquivos HTML possuem exatamente **0 tags não-fechadas** e passam na validação W3C/HTMLParser.
* **Acessibilidade & Contraste:** Todos os pares de cores do Modo Escuro e Modo Claro foram auditados e aprovados nos padrões **WCAG AAA e AA**.
* **Integridade Tipográfica:** 100% das telas utilizam exclusivamente a família `Plus Jakarta Sans` com `tnum` em valores numéricos.
