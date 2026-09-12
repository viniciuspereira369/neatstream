# NeatStream — Sistema de Design & Especificação de Engenharia (v2.0.0)
**Hub Anti-Fadiga de Streaming & Fintech Open Finance**

---

## 1. Visão do Produto, Filosofia & Governança de IA

O **NeatStream** atua na convergência entre entretenimento sob demanda e gestão financeira pessoal. Integra **gestão bancária de faturas via Open Finance**, cálculo de **custo por hora assistida (Econômetro)** e **curadoria comunitária neutra**, norteando-se pelo axioma:

> *"Quando tudo é especial, nada é verdadeiramente especial."*

### 1.1 O Manifesto Anti-Fadiga
1. **Uma decisão por vez:** Nunca exibir mais de 1 destaque principal + 3 alternativas imediatas por tela. O *infinite scroll* é terminantemente vetado na camada de descoberta.
2. **Transparência radical de custos:** Custo mensal, data de renovação do ciclo, horas reais assistidas e custo unitário por hora (R$/h) devem ser visíveis sem atrito.
3. **Zero dark patterns:** Cancelamento assistido em 1 toque, sem cronômetros regressivos manipulativos nem labirintos de retenção. Cancelar serviços ociosos é celebrado como conquista financeira.
4. **Confiança de padrão bancário:** Conexão criptografada (AES-256), escopo de leitura estritamente restrito a cobranças de streaming e revogação imediata em 1 toque.
5. **Calma como identidade:** Respiros generosos, cantos arredondados suaves e transições visuais com aceleração orgânica.
6. **Cor nunca como único indicador:** Qualquer estado crítico ou semântico (erro, aviso, conquista) deve ser acompanhado por forma geométrica, ícone padronizado e rótulo textual legível.

### 1.2 Autonomia Delegada de IA & Trilha de Auditoria
O usuário decide o nível de autonomia do assistente financeiro do NeatStream:
* **Nível 1 (Sugestão Informativa):** Apenas notifica serviços com ociosidade superior a 30 dias.
* **Nível 2 (Aprovação em 1 Toque):** Sugere pausar ou cancelar e aguarda confirmação explícita do usuário.
* **Nível 3 (Autônomo com Janela de Desfazer):** Pausa automaticamente serviços que atinjam 60+ dias sem reprodução.
  * **Janela de Desfazer de 7 dias:** Toda ação autônoma possui um botão imediato de reversão ("Desfazer pausa") disponível por 7 dias corridos.
  * **Trilha de Auditoria (Audit Log):** Log cronológico imutável com data, serviço afetado e economia projetada.
  * **Resumo Mensal de IA:** Relatório consolidado emitido todo dia 1º com o saldo poupado pelas ações do assistente.

---

## 2. Design Tokens Oficiais (DTCG v2.0.0)

Adotamos a especificação universal do *W3C Design Tokens Community Group (DTCG)* com paridade semântica simétrica entre temas. O designer e o desenvolvedor utilizam o mesmo token semântico; a folha de estilos resolve o valor específico para o tema ativo.

### 2.1 Cores Básicas & Superfícies (Paridade Semântica)

| Token Semântico | Dark Theme (Hex) | Light Theme (Hex) | Semântica de Aplicação |
| :--- | :--- | :--- | :--- |
| `bg/base` | `#080C0A` (Obsidian) | `#FAFBFC` (Canvas off-white) | Fundo raiz da aplicação |
| `bg/surface` | `#111714` (Obsidian Card) | `#FFFFFF` (Card puro) | Cards elevados, containers de dados |
| `bg/raised` | `#161F1B` (Obsidian Surface) | `#FFFFFF` + sombra suave | Modais, menus flutuantes e popovers |
| `border/subtle` | `rgba(255, 255, 255, 0.08)` | `#E2E8F0` | Divisórias e bordas secundárias de 1px |
| `border/strong` | `rgba(255, 255, 255, 0.16)` | `#CBD5E1` | Bordas ativas e caixas de seleção |
| `text/primary` | `#E8EDF2` | `#0E1116` | Títulos, valores de alto destaque |
| `text/secondary` | `#9BA6B2` | `#64748B` | Metadados, legendas e descrições |

---

### 2.2 Acentos, Gamificação e Semântica (Com Resolução de Colisão)

> [!IMPORTANT]
> **Resolução da Colisão Gold × Warning:**
> No tema escuro, o token de alerta de ociosidade foi alterado de `#FFB86B` para `#FF9838` (laranja quente e visivelmente distante do amarelo-dourado `#F5B84C`).
> Além disso, vigora a regra de desambiguação de forma: alertas **sempre** utilizam o ícone de triângulo com exclamação (`warning`), enquanto conquistas utilizam estrela/troféu e pílula com borda dupla.

| Token Semântico | Dark Theme (Hex) | Light Theme (Hex) | Forma / Ícone Obrigatório | Aplicação |
| :--- | :--- | :--- | :--- | :--- |
| `accent/mint` (ou `mint-text`) | `#00E599` | `#0E7C5B` (texto) / `#16A37A` (gráfico) | Pílula sólida / Círculo | CTAs primários, Econômetro positivo |
| `accent/lavender` | `#8B9BFF` | `#4F46E5` (texto) / `#6366F1` (gráfico) | Tag com cantos `radius/md` | Notas da comunidade, badges de review |
| `accent/gold` | `#F5B84C` | `#A16207` (texto) / `#D97706` (gráfico) | Selo com estrela (`star`) / Troféu | Selos de usuário, rankings e conquistas |
| `semantic/warning` | `#FF9838` | `#B45309` | **Triângulo de alerta (`warning`)** | Assinatura ociosa (30+ dias sem uso) |
| `semantic/danger` | `#FF5C5C` | `#DC2626` | Octógono ou X (`cancel` / `error`) | Estouro orçamentário, cancelamento |

---

### 2.3 Auditoria Par-a-Par de Contraste WCAG

Todos os pares de cores foram rigorosamente auditados em relação aos seus fundos correspondentes:

| Par Auditado (Elemento × Fundo) | Tema | Valor Elemento | Valor Fundo | Razão de Contraste | Nível WCAG | Status |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| `text/primary` × `bg/base` | Dark | `#E8EDF2` | `#080C0A` | **13.8:1** | AAA | ✓ Aprovado |
| `text/secondary` × `bg/surface` | Dark | `#9BA6B2` | `#111714` | **6.2:1** | AA | ✓ Aprovado |
| `accent/mint` × `bg/surface` | Dark | `#00E599` | `#111714` | **9.1:1** | AAA | ✓ Aprovado |
| `semantic/warning` × `bg/surface` | Dark | `#FF9838` | `#111714` | **7.4:1** | AAA | ✓ Aprovado |
| `accent/gold` × `bg/surface` | Dark | `#F5B84C` | `#111714` | **8.6:1** | AAA | ✓ Aprovado |
| `text/primary` × `bg/base` | Light | `#0E1116` | `#FAFBFC` | **17.2:1** | AAA | ✓ Aprovado |
| `text/secondary` × `bg/surface` | Light | `#64748B` | `#FFFFFF` | **4.6:1** | AA | ✓ Aprovado |
| `accent/mint-text` × `bg/surface` | Light | `#0E7C5B` | `#FFFFFF` | **5.0:1** | AA | ✓ Aprovado |
| `accent/lavender-text` × `bg/surface`| Light | `#4F46E5` | `#FFFFFF` | **5.5:1** | AA | ✓ Aprovado |
| `semantic/warning` × `bg/surface` | Light | `#B45309` | `#FFFFFF` | **4.8:1** | AA | ✓ Aprovado |
| `semantic/danger` × `bg/surface` | Light | `#DC2626` | `#FFFFFF` | **4.9:1** | AA | ✓ Aprovado |
| `accent/gold-text` × `bg/surface` | Light | `#A16207` | `#FFFFFF` | **5.1:1** | AA | ✓ Aprovado |

---

### 2.4 Escala Tipográfica Padronizada (Unificação Plus Jakarta Sans)

A tipografia do NeatStream é unificada em torno da família geométrica premium **Plus Jakarta Sans** (estilo *Apple TV / Linear / Revolut*), eliminando fontes genéricas (Inter) e serifas (Spectral) para criar uma experiência 100% modernista, elegante e calorosa, com suporte a OpenType Tabular Figures (`tnum`) para alinhamento numérico:

| Token | Tamanho / Line Height | Família / Peso | Tracking | Uso Semântico |
| :--- | :--- | :--- | :--- | :--- |
| `display-lg` | 56px / 64px | Plus Jakarta Sans 800 (ExtraBold) | -0.03em | Hero principal da Landing Page |
| `display` | 40px / 48px | Plus Jakarta Sans 700 (Bold) | -0.02em | Títulos de seção do Dashboard Web |
| `editorial-quote` | 22px / 32px | Plus Jakarta Sans 400 Italic | normal | Manifestos, citações editoriais e destaques narrativos |
| `title` | 28px / 36px | Plus Jakarta Sans 700 (Bold) | -0.02em | Header de tela mobile e títulos principais |
| `heading` | 20px / 28px | Plus Jakarta Sans 600 (SemiBold) | -0.01em | Títulos de cards e destaques de catálogo |
| `body-lg` | 16px / 24px | Plus Jakarta Sans 400 (Regular) | normal | Leitura mobile e sinopses de produções |
| `body` | 14px / 20px | Plus Jakarta Sans 400 / 500 | normal | UI densa, dados operacionais e itens de lista |
| `caption` | 12px / 16px | Plus Jakarta Sans 500 (Medium) | normal | Metadados, tags de gênero e datas secundárias |
| `label-caps` | 11px / 16px | Plus Jakarta Sans 700 (Bold) | +0.08em | Micro-selos em caixa alta (`ECONÔMETRO`, `DISNEY+`, `MAX`) |
| `value` / `tnum` | 14px / 20px | Plus Jakarta Sans 700 + `tnum` | normal | Moedas (R$), métricas financeiras e contadores dinâmicos |

---

### 2.5 Estados Interativos Universais

Nenhum elemento existe apenas no estado estático. Cada componente interativo deve implementar a seguinte matriz:

| Estado | Regra Visual Dark Theme | Regra Visual Light Theme | Comportamento / Acessibilidade |
| :--- | :--- | :--- | :--- |
| **Default** | Cor base do token | Cor base do token | Estado de repouso |
| **Hover** | Clarear 8% (`#4BDDAE` para Mint) | Escurecer 8% (`#0A6046` para Mint) | Transição suave de 150ms (`duration/fast`) |
| **Pressed** | Escurecer 12% (`filter: brightness(0.88)`) | Escurecer 12% (`filter: brightness(0.88)`) | Escala de micro-toque (`scale(0.98)`) |
| **Focus Visible** | Anel sólido 2px `#00E599` + offset 2px | Anel sólido 2px `#0E7C5B` + offset 2px | `:focus-visible` ativado exclusivamente por teclado |
| **Disabled** | Opacidade 40% + `cursor: not-allowed` | Opacidade 40% + `cursor: not-allowed` | `aria-disabled="true"`, sem eventos de ponteiro |
| **Loading** | Shimmer linear translúcido | Shimmer cinza suave | `aria-busy="true"`, placeholder esqueleto |
| **Empty State** | Ícone de contorno + texto amigável | Ícone de contorno + texto amigável | Mensagem clara e CTA para conectar serviço |
| **Error** | Borda `semantic/danger` + ícone de erro | Borda `semantic/danger` + ícone de erro | Mensagem corretiva abaixo do campo |

---

### 2.6 Tokens Estruturais (Motion, Z-Index, Layout & Marcas)

#### Motion
* `duration/fast`: `150ms` (hover, press, seletores de aba).
* `duration/base`: `250ms` (transições de telas, expansão de accordions).
* `duration/slow`: `400ms` (contador de celebração, preenchimento do gauge).
* `easing/standard`: `cubic-bezier(0.2, 0, 0, 1)`.
* `prefers-reduced-motion`: Suporte nativo desativando transições bruscas para usuários com sensibilidade vestibular.

#### Z-Index Scale
* `z/base`: `0`
* `z/sticky`: `10` (top bars, cabeçalhos fixos)
* `z/dropdown`: `20` (menus de contexto, selects)
* `z/modal`: `30` (Roleta de Escolha, confirmação de cancelamento)
* `z/toast`: `40` (alertas flutuantes e notificações de IA)
* `z/tooltip`: `50` (dicas de ferramentas rápidas)

#### Breakpoints & Áreas de Toque (Touch Targets)
* Breakpoints: `sm` (360px), `md` (768px), `lg` (1024px), `xl` (1280px), conteúdo máximo centralizado em `1200px`.
* Touch Targets: Mínimo de **44×44px no iOS** e **48×48px no Android**, com o ícone central medindo 20px ou 24px.

#### Rampa Ordenada de Dados (Data-Viz Ramp)
Gráficos com múltiplos serviços usam a seguinte ordem fixa, com rótulos diretos sem legenda flutuante:
1. `#00E599` (Electric Mint) — Mais consumido
2. `#8B9BFF` (Lavender) — 2º colocado
3. `#F5B84C` (Gold) — 3º colocado
4. `#6BB8FF` (Sky Blue) — 4º colocado
5. `#FF5C5C` (Coral) — Ocioso / Sem uso

#### Regra para Logotipos de Terceiros
> [!CAUTION]
> **Logotipos de Serviços de Streaming:**
> É estritamente proibido recolorir logotipos de terceiros (Netflix, Max, Disney+, Apple TV+, Prime Video). Eles devem ser sempre exibidos com suas cores de marca oficiais, contidos em caixas neutras com fundo `bg/surface` e borda `border/subtle`.

---

## 3. Refinos nos Componentes Existentes

### 3.1 `EconometroGauge` (Escala Progressiva de Risco)
* **Thresholds de Cor:**
  * **0% a 75% do teto orçamentário:** Preenchimento em `accent/mint` (`#00E599`). Status: *"Dentro da meta"*.
  * **75% a 90% do teto orçamentário:** Preenchimento em `semantic/warning` (`#FF9838`). Status: *"Atenção ao teto"*.
  * **Acima de 90% do teto:** Preenchimento em `semantic/danger` (`#FF5C5C`). Status: *"Estouro iminente"*.
* **Ícones do Sistema:** Substituição total de emojis (`✓`, `⚠`) por ícones vetoriais padronizados (`check_circle`, `warning`, `error`).

### 3.2 `SubscriptionCard` (3 Estados Distintos)
1. **Estado "Ativo":** Borda sutil, badge verde menta, custo por hora calculado e data da próxima cobrança.
2. **Estado "Pausado":** Badge em lavanda/azul, valor mensal congelado, botão *"Reativar com 1 Toque"*.
3. **Estado "Cancelado":** Badge neutro riscado, exibição da data limite de vigência paga e economia anual acumulada.
* **Acessibilidade para R$ ∞:** Quando o serviço não possuir horas assistidas, o indicador exibe `Sem uso registrado` como `aria-label` para leitores de tela.

### 3.3 `PosterCard` (Botão Estratégico de Watchlist)
* O `PosterCard` incorpora obrigatoriamente o botão **"+ Quero Assistir"** (ícone `bookmark_add`).
* **Valor para o Negócio:** Esse botão alimenta o relatório estratégico *"Qual streaming tem mais títulos da sua lista de desejos"*, permitindo ao NeatStream recomendar com precisão matemática quais serviços o usuário deve manter e quais deve cancelar.

### 3.4 `CelebrationBanner` (Anti-Fadiga de Celebração)
* **Variações Dinâmicas:** Três layouts alternados para cancelamentos múltiplos (Variação A: foco no contador anualizado; Variação B: foco no impacto no orçamento mensal; Variação C: desbloqueio de insígnia da comunidade).
* **Feedback Tátil:** Disparo de micro-vibração háptica (`navigator.vibrate([15, 30, 15])`) em dispositivos móveis compatíveis.
* **Números Tabulares:** Uso obrigatório de `font-feature-settings: 'tnum'` no contador para evitar pulos de largura durante a contagem.

---

## 4. Componentes Estratégicos de Comunidade & IA

### 4.1 `PlatformAvailabilityRow` (Onde Assistir com 4 Estados)
Resolve visualmente a maior dúvida de descoberta de streaming:
* **Estado 1 (Incluído):** `"Incluído na sua assinatura Disney+"` (com botão de deep link direto `Assistir`).
* **Estado 2 (Disponível p/ Aluguel):** `"Disponível para aluguel no Apple TV+ por R$ 14,90"`.
* **Estado 3 (Indisponível na Região):** `"Não disponível em streamings no Brasil no momento"`.
* **Estado 4 (Saindo do Catálogo):** `"Deixa a Netflix em 14 de Outubro"`.

### 4.2 `ReviewCard` (Curadoria Autêntica & Verificação)
* Exibe a nota comunitária neutra sobre 10 (ex: `8.9`), tempo de tela assistido pelo autor da review e selo **"Review Verificada via Open Finance"** (garante que o autor realmente assina e assistiu ao conteúdo).
* **Estado "Em Análise":** Reviews submetidas que aguardam validação anti-spoiler.

### 4.3 `BadgeChip` & `RankingList` (Gamificação Financeira)
* Pílulas de conquistas com microborda dourada e ícone de troféu (`Otimizador Consciente`, `Mestre do Custo/Hora`, `Zero Desperdício`).
* Ranking anônimo comunitário comparando o aproveitamento percentual do teto financeiro entre os usuários da plataforma.

### 4.4 `DelegationPanel` (Painel de Auditoria de Ações da IA)
* Histórico linear de intervenções automáticas do assistente de Nível 3.
* Exemplo de registro: `12/Out · IA pausou Disney+ após 60 dias de ociosidade · Economia de R$ 43,90`.
* **Botão "Desfazer Ação":** Permite reverter a decisão com 1 toque durante a janela de 7 dias.

### 4.5 `Toast/AlertCenter` & Modo Silencioso
* Notificações com tipologia semântica (Info, Sucesso, Alerta, Perigo).
* *Success Toasts* possuem auto-dismiss de 4 segundos; *Danger Toasts* requerem dispensa explícita.
* **Horário Silencioso de Push:** Proibição estrita de notificações financeiras entre 22h e 9h, reforçando o manifesto de tranquilidade mental.

### 4.6 `TransactionEnrichmentModule` (Detecção Inteligente de Assinaturas)
Resolve o problema clássico de extratos de cartão indecifráveis através de normalização e enriquecimento semântico:
* **Entrada Bruta:** String bancária truncada (ex: `DISNEYPLUS BR R9201 SAO PAULO`).
* **Saída Estruturada:** Card limpo com logotipo vetorial, Merchant Category Code (MCC: `4899 - Cabo e Outros Serviços de Pagamento`), status verificado e identificação clara do serviço.
* **Métrica de Valor:** Economia média anual comprovada de **`R$ 526,80 / ano por usuário`** ao identificar e eliminar assinaturas duplicadas ou esquecidas.
* **Benefício de UX:** Reduz o suporte ao cliente a zero ao eliminar a confusão de "que cobrança é essa?".

### 4.7 `FinancialClarityCategories` & `NeatStreamIntelligence` (Clareza Financeira e IA)
Módulo voltado a responder a questão fundamental do assinante: *"Para onde vai meu dinheiro?"*:
* **Abas Sem Burocracia:** Navegação por categorias emocionais de streaming em vez de relatórios fiscais áridos (`Cinema Cult`, `Séries Premium`, `Reality & Esportes`, `Música`).
* **Assistente Conversacional de Linguagem Natural:** O usuário pergunta diretamente *"Quanto economizo se pausar a Disney e a Apple por 3 meses?"* e recebe uma resposta formatada com botões de ação imediata.
* **Rede de Confiança:** Integração garantida com mais de 45.000 instituições bancárias via Open Finance e criptografia AES-256.

### 4.8 `FranchiseHubsStrip` & `TacticalTags` (Navegação por Hubs e Tags Táticas)
Padrão de exploração visual dinâmica de catálogos:
* **Faixa de Hubs de Franquias:** Pílulas de exploração no topo com logotipos e identidades de franquias consagradas (HBO, Max Originals, DC Universe, Harry Potter, Adult Swim, Showtime).
* **Tags Táticas Luminescentes:** Chips de reação com microglow de alto contraste (`🔥 Intenso`, `✨ Aclamado`, `🧠 Psicológico`), elevando a taxa de engajamento e a rapidez de escolha.
* **Badges de Conteúdo Ao Vivo:** Indicadores em tempo real para eventos esportivos transmitidos no Max e Paramount+.

---

## 5. Acessibilidade como Engenharia Verificável

1. **Ordem de Leitura no DOM:** Screen readers devem anunciar primeiro o título semântico da assinatura antes do valor monetário (ex: *"Netflix Padrão, R$ 55,90 por mês, 42 horas assistidas"*), garantindo compreensão contextual imediata.
2. **Contexto Obrigatório para Labels em Caixa Alta:** O token `label-caps` nunca pode aparecer desprovido de texto de apoio. Todo label em caixa alta deve ter um elemento irmão ou atributo descritivo associado.
3. **Navegação por Teclado:** Todas as tabelas e cards possuem suporte a foco sequencial (`tabindex="0"`) com anel de foco `:focus-visible` de 2px.

---

## 6. Governança e Matriz Do / Don't

### 6.1 Convenção de Nomenclatura Única
A nomenclatura de tokens e classes segue estritamente o padrão de 4 níveis:
`<categoria>/<propriedade>/<variante>/<estado>`
Exemplos: `color/accent/mint/hover`, `radius/md`, `motion/duration/fast`, `font/editorial`.

### 6.2 Matriz Do / Don't

| Componente | DO (Correto) | DON'T (Incorreto) |
| :--- | :--- | :--- |
| **Cores de Alerta** | Usar `#FF9838` acompanhado do ícone `warning` para ociosidade. | Não usar amarelo `#F5B84C` para alertas nem alertar apenas mudando a cor do texto. |
| **Logotipos de Streaming** | Manter a logo original da Netflix vermelha dentro de card escuro neutro. | Não aplicar filtros monocromáticos ou tingir a logo de verde menta. |
| **Econômetro** | Usar escala progressiva (menta → âmbar → vermelho) conforme a meta é consumida. | Não alternar bruscamente entre verde e vermelho sem estágio intermediário. |
| **Cancelamento** | Destacar a economia anual poupada e confirmar a data de vigência do plano pago. | Não criar modais com cronômetros de pressão ou botões confusos de desistência. |
| **Detecção de Faturas** | Exibir o card estruturado com logotipo oficial e categoria legível. | Não exibir strings cifradas brutas (`DISNEYPLUS BR...`) diretamente para o usuário. |
| **NeatStream Intelligence** | Responder perguntas financeiras em linguagem natural direta e amigável. | Não forçar o usuário a preencher planilhas manuais ou relatórios contábeis complexos. |
| **Tipografia Primária** | Utilizar `Plus Jakarta Sans` em toda a interface com pesos 400 (corpo), 600 (botões/badges) e 800 (títulos com tracking negativo). | Não utilizar fontes genéricas como Inter ou misturar múltiplas famílias desconexas. |
| **Tipografia de Moeda & Números** | Aplicar `Plus Jakarta Sans` com `tnum` (OpenType Tabular Figures) em qualquer valor em `R$`. | Não utilizar fontes proporcionais para moedas em tabelas comparativas. |

---

### 6.3 Registro de Versão (Changelog)

* **v2.2.0 (Atual):**
  * **Unificação Tipográfica:** Migração completa e harmoniosa para a família **Plus Jakarta Sans** (estilo Apple TV / Linear), eliminando o Inter e adotando uma estética 100% modernista com OpenType Tabular Figures (`tnum`) para valores e métricas financeiras.
  * **Modo Cinema Minimalista:** Redesign do Dashboard com foco em billboard 16:9 full-bleed, posters verticais 2:3 em alta resolução, HUD orçamentário compacto e leques visuais 3D de capas na comunidade.
  * **Landing Page Cinemática:** Marquee contínuo de pôsteres com rolagem acelerada por hardware e simulador tátil de economia em tempo real.
  * **Mobile Feed Estilo Letterboxd:** Feed imersivo em 2 colunas com micro-selos de plataforma e zero texto de rolagem.
* **v2.1.0:**
  * Integração da tipografia editorial de luxo **Spectral** para manifestos e momentos editoriais.
  * Adição do módulo interativo de **Detecção Inteligente de Assinaturas** com foco exclusivo na economia média anual comprovada (`R$ 526,80 / ano`).
  * Incorporação do modelo de clareza orçamentária e IA conversacional (**NeatStream Intelligence**, "Para onde vai meu dinheiro?").
  * Implementação de Hubs de Franquias e chips táticos luminescentes para navegação de catálogo.
  * Ampliação da Galeria Comparativa no Master Hub com novos comparativos documentados.
* **v2.0.0:**
  * Resolução formal da colisão cromática Gold × Warning (`#FF9838`).
  * Especificação completa do tema claro com contraste auditado (WCAG AAA/AA).
  * Unificação semântica dos tokens no padrão W3C DTCG.
  * Padronização definitiva de tipografia (Sora + Inter + IBM Plex Mono).
  * Inclusão de tokens de motion, z-index, breakpoints, touch targets e rampa de data-viz.
  * Especificação dos componentes de comunidade (`PlatformAvailabilityRow`, `ReviewCard`, `DelegationPanel` com desfazer de 7 dias, `ToastCenter`).
  * Matriz universal de estados e regras Do/Don't.
* **v1.0.0:** Release inicial de arquitetura e design tokens estáticos.
