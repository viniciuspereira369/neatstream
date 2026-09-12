# NeatStream — Hub Unificado de Streaming & Gestão Financeira Inteligente

> **Documentação Completa da Plataforma, Design System & Ecossistema de Telas (Padrão 2026)**  
> *Ecossistema Completo de Interfaces: Web Landing, Dashboards de Gestão, Aplicativo Mobile e Design System Proprietário.*

---

## 1. Visão Geral da Plataforma

O **NeatStream** é uma plataforma concebida para transformar a forma como as pessoas consomem entretenimento audiovisual e gerenciam suas finanças de streaming. O produto atua em quatro frentes complementares:

1. **Gestão e Cancelamento Assistido de Assinaturas:** Mapeamento unificado de todos os serviços contratados (Netflix, Max, Disney+, Apple TV+, Prime Video etc.), identificação imediata de serviços ociosos ou pouco utilizados e cancelamento em 1 clique, sem labirintos ou formulários exaustivos.
2. **Detecção Inteligente de Assinaturas em Tempo Real:** Conexão via Open Finance convertendo faturas indecifráveis (`DISNEYPLUS R8K29...`) em cartões estruturados com logotipo oficial e identificação clara de consumo.
3. **Controle Financeiro & IA Orçamentária (NeatStream Intelligence):** Ferramenta visual que responde *"Para onde vai meu dinheiro?"*, categoriza gastos por gênero e disponibiliza o assistente *NeatStream Intelligence* para consultas orçamentárias em linguagem natural.
4. **Curadoria Cinematográfica Neutra & Hubs de Franquias:** Sistema de curadoria limpa e orgânica com pílulas de franquias consagradas (HBO, Max Originals, DC Universe, Harry Potter), tags táticas de alto contraste (`🔥 Intenso`, `✨ Aclamado`) e a **Roleta de Escolha** para eliminar a fadiga de decisão.

---

## 2. Personas Atendidas

* **Otimizador Financeiro:** Busca eliminar desperdícios financeiros decorrentes de assinaturas esquecidas no cartão de crédito. Deseja visualizar claramente quanto gasta, quais serviços não estão dando retorno proporcional e economizar centenas de reais por ano.
* **Consumidor Multiplataforma:** Possui múltiplas contas simultâneas e sofre com a fragmentação de catálogos e a perda de tempo procurando onde determinado filme ou série está disponível.
* **Entusiasta de Cinema e Séries:** Valoriza recomendações autênticas da comunidade (reações emocionais como *Intenso*, *Inspirador*, *Épico*) e conexão social sem algoritmos comerciais empurrando produções irrelevantes.

---

## 3. Design System & Identidade Visual 2026 (v2.2.0)

A linguagem visual do NeatStream segue as especificações do **W3C DTCG** e a estética *"Cinematic FinTech"* (Apple TV+/A24 rich media + Linear/Revolut compact indicators):

### 3.1. Tipografia Oficial (100% Modernista — Plus Jakarta Sans)
* **Família Única e Unificada:** `Plus Jakarta Sans` (pesos 300, 400, 500, 600, 700, 800 + itálico).
* **Headlines & Display:** `Plus Jakarta Sans` ExtraBold (700, 800) com tracking negativo (`tracking-tight` / `-0.03em`) para títulos de alto impacto.
* **Corpo de Texto & UI:** `Plus Jakarta Sans` Regular / Medium (400, 500) com altura de linha relaxada para máxima legibilidade.
* **Métricas Financeiras & Badges:** `Plus Jakarta Sans` SemiBold / Bold com OpenType Tabular Figures (`font-feature-settings: 'tnum' 1, 'zero' 1; font-variant-numeric: tabular-nums;`) garantindo alinhamento vertical estrito para valores monetários (`R$ 142,60`), economia anual e notas.
* **Manifestos & Citações:** `Plus Jakarta Sans` em itálico suave, eliminando a ruptura visual de serifas heterogêneas.

### 3.2. Paleta Cromática & Resolução de Conflitos
* **Fundo Base:** Obsidian `#080C0A` (grafite ultra-profundo que evita a dureza do preto puro `#000000`) no tema escuro e Canvas `#FAFBFC` no tema claro.
* **Superfícies & Cards:** Obsidian Card `#111714` e Obsidian Surface `#161F1B`, com micro-bordas translúcidas de precisão `rgba(255, 255, 255, 0.08)`.
* **Acento Primário:** Electric Mint `#00E599` / Mint Light `#34F5B2` no dark; Mint Text `#0E7C5B` (ratio 5:1 WCAG AA) no light.
* **Acento Alerta (Desambiguado):** Laranja Quente `#FF9838` (dark) / `#B45309` (light) — visualmente separado do Gold e sempre acompanhado do ícone de triângulo de aviso.
* **Acento Gamificação (Gold):** `#F5B84C` (dark) / `#A16207` (light) — acompanhado de ícones de estrela/troféu para selos e conquistas.
* **Acento Comunidade (Lavender):** `#8B9BFF` (dark) / `#4F46E5` (light) — para notas neutras de filmes e séries.

### 3.3. Componentes Assinatura & Modo Cinema
1. **Marquee Duplo Contínuo (Landing Page):** Trilhos horizontais opostos com posters verticais 2:3 oficiais em alta definição (`assets/posters/`) e aceleração suave por hardware.
2. **Simulador Tátil de Rotação de Streaming:** Controle interativo de ativação/pausa com recálculo animado de economia média anual (**R$ 526,80/ano**).
3. **Billboard Cinemático 16:9 Full-Bleed com Vídeo:** Experiência imersiva no Dashboard com reprodução em loop contínuo de teaser oficial (`assets/videos/dune2_teaser.mp4`), iluminação atmosférica, fallback estático e controles táteis de áudio (unmute) e play/pause.
4. **Player de Vídeo Mobile Nativo:** Hero imersivo no app mobile com loop de teaser de série (`assets/videos/the_bear_teaser.mp4`) e controle flutuante de mute/unmute.
5. **HUD Orçamentário Compacto:** Medidor radial e slider de limite mensal com barras de bateria visual para cada streaming conectado.
6. **Feed Mobile Estilo Letterboxd / MUBI:** Grade contínua em 2 colunas com micro-selos nos cantos dos posters (`MAX`, `DISNEY+`, `APPLE`, `NETFLIX`, `PRIME`), notas (`★ 9.1`) e posters oficiais 2:3.
7. **Leques 3D de Posters Sobrepostos:** Curadorias comunitárias apresentadas em leques tridimensionais expansivos com posters oficiais de catálogo.
8. **Floating Capsule Dock:** Barra de navegação inferior flutuante em vidro fosco (`backdrop-blur-xl`).
9. **SubscriptionCard com Pausa em 1 Toque:** Gestão visual de ciclo de cobrança e celebração de economia anual.

---

## 4. Estrutura do Ecossistema e Telas Produzidas

```
Projeto App Transformação Digital/
├── index.html                    # Master Studio Hub (Emulador Mobile/Desktop + Galeria Comparativa)
├── tokens.json                   # Especificações JSON de tokens de design
├── DESIGN_SYSTEM.md              # Manual de diretrizes de design e identidade visual (v2.1.0)
├── README.md                     # Documentação completa da plataforma (este arquivo)
│
├── assets/                       # Mídias Oficiais Locais (Zero Dependência Externa)
│   ├── posters/                  # 12 Pôsteres Oficiais Verticais 2:3 em Alta Definição (TMDB Key-Art)
│   │   ├── dune2.jpg, the_bear.jpg, severance.jpg, shogun.jpg, oppenheimer.jpg, arcane.jpg
│   │   └── succession.jpg, stranger_things.jpg, fallout.jpg, blade_runner_2049.jpg, the_last_of_us.jpg, anatomy_of_a_fall.jpg
│   ├── backdrops/                # 12 Backdrops Cinemáticos 16:9 Widescreen para Billboard e Modais
│   │   └── dune2_backdrop.jpg, the_bear_backdrop.jpg, severance_backdrop.jpg ...
│   └── videos/                   # Teasers de Vídeo em Loop Otimizados para Web (H.264 / AAC +faststart)
│       ├── dune2_teaser.mp4      # Teaser de Duna: Parte 2 (Billboard Web, 720p 20s)
│       └── the_bear_teaser.mp4   # Teaser de O Urso (Hero Mobile, 720p 18s)
│
├── mobile/                       # Aplicação Mobile
│   ├── carteira_dark.html        # Carteira & Econômetro (Modo Escuro com Gráfico de 6 Meses e Sincronização)
│   ├── carteira_light.html       # Carteira & Econômetro (Variação Modo Claro)
│   ├── hoje.html                 # Descoberta Cinematográfica, Hero com Vídeo, Feed 2 Colunas Letterboxd
│   ├── celebracao.html           # Fluxo de Cancelamento Assistido em 1 Toque com Economia Anual
│   └── onboarding.html           # Onboarding Seguro com Pôsteres Oficiais 3D e Rede de 45.000+ Bancos
│
├── web/                          # Aplicação Web Desktop
│   ├── landing.html              # Landing Page Comercial com Marquee Oficial, Detecção Inteligente e Simulador
│   ├── dashboard_dark.html       # Painel Web de Gestão, Billboard com Vídeo e Catálogo Top 10 (Modo Escuro)
│   └── dashboard_light.html      # Painel Web de Gestão com Billboard de Vídeo (Modo Claro)
│
├── references/                   # As 7 Referências Visuais de Inspiração
│   ├── ref1_sports_app.png       # Referência 1: Sports Gaming App (Floating Dock)
│   ├── ref2_mintro_web.png       # Referência 2: Mintro Web (Cartão Virtual & Ambient Glow)
│   ├── ref3_nytasco_bento.png    # Referência 3: Nytasco Bento Grid
│   ├── ref4_plant_iot.png        # Referência 4: Plant IoT Scanner (Cards de Dados Escuros)
│   ├── ref5_fintech_portfolio.png# Referência 5: Fintech Portfolio 2026 (Gráfico Minimalista)
│   ├── ref6_inox_art.png         # Referência 6: iNox Movie Streaming App (Dribbble / Kretya)
│   └── ref7_social_movie_art.png # Referência 7: Social Movie App (Dribbble / Artspire)
│
└── screenshots/                  # Prints em Alta Definição Capturados
    ├── mobbin_collection.png     # Captura da Coleção Mobbin (12 Telas HBO Max/Paramount/Riot)
    ├── master_index.png          # Print Geral do Master Hub
    ├── mobile_carteira_dark.png  # Print da Carteira & Econômetro
    ├── mobile_hoje.png           # Print da Descoberta Hoje
    ├── mobile_celebracao.png     # Print da Celebração de Cancelamento
    ├── mobile_onboarding.png     # Print do Onboarding Seguro
    ├── web_landing.png           # Print da Landing Page
    └── web_dashboard_dark.png    # Print do Dashboard Web
```

---

## 5. Mapeamento e Análise Frente às Referências

| Comparativo | Referência de Inspiração | Elementos-Chave Incorporados | Tela do NeatStream | Status de Adequação |
| :--- | :--- | :--- | :--- | :--- |
| **1. Gestão Financeira** | **Ref 5: Fintech Portfolio 2026** (`uixalamin.co`) + **Ref 1: Sports App** | Gráfico minimalista de 6 barras verticais com rounded tops; destaque em Electric Mint no mês atual; seletor de períodos em pílula (`1M`, `3M`, `6M`, `Ano`); barra de alocação segmentada; Floating Capsule Dock com aba ativa destacada. | `mobile/carteira_dark.html` | **100% Conforme** |
| **2. Descoberta & Curadoria** | **Ref 1: Sports Gaming** + **Ref 4: Plant IoT Scanner** | Fundo grafite profundo com iluminação ambiente difusa; pôster cinematográfico principal em destaque único; badges em pílula com vidro fosco; dados objetivos sem sobrecarga. | `mobile/hoje.html` | **100% Conforme** |
| **3. Landing Page Comercial** | **Ref 2: Mintro Web** + **Ref 3: Nytasco Bento** | Headline direta de alto impacto; ambient glow central verde esmeralda; cartão virtual de controle em perspectiva "NeatStream Pass" com chip e indicador pulsante do Econômetro; Bento Grid modular. | `web/landing.html` | **100% Conforme** |
| **4. Alívio de Cancelamento** | **Princípios Comerciais de Conversão** | Exibição destacada da economia anual gerada (`R$ 526,80 / ano`); redução visual do gasto mensal no Econômetro; confirmação de vigência contratual transparente sem atrito. | `mobile/celebracao.html` | **100% Conforme** |
| **5. Catálogo & Streaming** | **Ref 6: iNox Streaming App** (*Kretya / Dribbble*) | Pílulas de categorias horizontais no topo (`[Todos] [Séries] [Filmes] [Em Alta] [Mais Votados]`); hero cinematográfico imersivo com radial vignette suave; paginação por pontos; pôsteres angulados em 3D no onboarding. | `mobile/hoje.html` e `mobile/onboarding.html` | **100% Conforme** |
| **6. Comunidade & Decisão** | **Ref 7: Social Movie App** (*Artspire / Dribbble*) | Dock 2x2 "Onde Assistir Agora" com logos dos serviços e botão de abertura direta; tags emocionais da comunidade (`🔥 Intenso`, `✨ Aclamado`, `🧠 Psicológico`); badge de amigos recomendando; modal interativo de Roleta de Escolha Rápida. | `mobile/hoje.html` | **100% Conforme** |
| **7. Enriquecimento & Orçamento** | **Padrões de Alta Performance** | Detecção inteligente de assinaturas, abas sem burocracia e assistente NeatStream Intelligence; tipografia editorial de alto luxo. | `web/landing.html`, `web/dashboard_dark.html`, `mobile/carteira_dark.html` | **100% Conforme** |
| **8. Hubs de Franquias & Tags** | **Mobbin Collection (HBO Max, Paramount+, Riot)** | Hubs de franquias consagradas (HBO, DC, Harry Potter); chips táticos luminescentes com microglow; faixa de marcas agregadas. | `mobile/hoje.html`, `web/landing.html` | **100% Conforme** |
| **9. Master Hub Central** | **Apresentação Executiva & Interativa** | Emulador com chassis de smartphone realista (Dynamic Island, relógio ao vivo, status bar) e galeria comparativa completa lado a lado com todas as referências e prints reais. | `index.html` | **100% Conforme** |

---

## 6. Como Executar e Navegar no Projeto

A plataforma é totalmente estática e roda nativamente no navegador através de qualquer servidor HTTP local:

### 6.1. Iniciar Servidor Local
No terminal, na pasta raiz do projeto:
```bash
python -m http.server 8000
```

### 6.2. URLs de Acesso Rápido
* **Master Studio Hub (Emulador & Galeria):** [http://localhost:8000/index.html](http://localhost:8000/index.html)
* **Carteira & Econômetro Mobile:** [http://localhost:8000/mobile/carteira_dark.html](http://localhost:8000/mobile/carteira_dark.html)
* **Descoberta "Hoje" Mobile:** [http://localhost:8000/mobile/hoje.html](http://localhost:8000/mobile/hoje.html)
* **Cancelamento Assistido Mobile:** [http://localhost:8000/mobile/celebracao.html](http://localhost:8000/mobile/celebracao.html)
* **Onboarding Seguro Mobile:** [http://localhost:8000/mobile/onboarding.html](http://localhost:8000/mobile/onboarding.html)
* **Landing Page Web Desktop:** [http://localhost:8000/web/landing.html](http://localhost:8000/web/landing.html)
* **Dashboard Web Desktop:** [http://localhost:8000/web/dashboard_dark.html](http://localhost:8000/web/dashboard_dark.html)

---

## 7. Diretrizes de Copy Comercial

Todas as telas do NeatStream adotam uma comunicação estritamente comercial, amigável e voltada a valor:
* **Sem Jargões Burocráticos:** Foram eliminadas menções a normas, termos regulatórios ou nomenclaturas de conformidade interna. Em substituição, foram adotadas expressões simples como *"Conexão 100% Segura"*, *"Privacidade Garantida"* e *"Controle Total do seu Dinheiro"*.
* **Sem Metalinguagem Acadêmica:** Textos de apresentação focam nas dores reais do consumidor: *"Todas as Suas Assinaturas em Um Só Lugar"*, *"Economia sugerida no Disney+"*, *"Sugestões para Você"*.
* **Empatia e Transparência no Cancelamento:** O cancelamento é tratado como uma conquista do usuário de retorno financeiro, informando claramente a economia gerada e mantendo a data de vigência do período já pago.
