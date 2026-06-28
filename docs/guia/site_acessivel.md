# O que um site precisa para ser acessível?

> **Conteúdo:** Guia prático dos pilares e elementos essenciais que devem estar presentes em qualquer website para garantir conformidade básica de acessibilidade.

Para que um site seja considerado acessível e atenda aos requisitos legais e técnicos (como os níveis A e AA da WCAG e da NBR 17225), ele deve conter, no mínimo, as seguintes implementações:

---

## 1. Alternativas de Texto (Conteúdo Não-Textual)
*   **Imagens Descritivas:** Todas as imagens que transmitem informação devem ter o atributo `alt` preenchido com uma descrição clara e objetiva do seu conteúdo.
*   **Imagens Decorativas:** Imagens puramente decorativas (como bordas ou ícones de fundo que não agregam informação) devem usar `alt=""` (vazio) ou `aria-hidden="true"`, para serem ignoradas pelos leitores de tela.
*   **Elementos Vazios:** Links ou botões representados apenas por ícones gráficos (ex: um ícone de lupa para pesquisa ou ícone de redes sociais) devem conter o atributo `aria-label` especificando a sua ação.

---

## 2. Navegabilidade Completa via Teclado
*   **Independência de Mouse:** Qualquer ação que possa ser realizada pelo mouse (clicar em botões, abrir submenus, navegar em carrosséis, fechar modais) deve poder ser executada apenas usando as teclas `Tab`, `Enter`, `Espaço` e as direcionais (`Arrows`).
*   **Indicador de Foco Visível:** O indicador de foco (aquela borda que aparece ao redor de links e botões selecionados) nunca deve ser ocultado por CSS (`outline: none` é proibido). Ele deve ter espessura e contraste suficientes para ser percebido por usuários de teclado.
*   **Ordem Lógica de Foco:** A navegação pelo teclado deve seguir uma ordem lógica de leitura (de cima para baixo, da esquerda para direita).
*   **Atalho para o Conteúdo (Skip Link):** Um link invisível no topo da página que aparece ao receber o foco do teclado, permitindo ao usuário "pular" o menu de navegação e ir direto para o conteúdo principal.

---

## 3. Uso Correto e Inclusivo de Cores
*   **Contraste Suficiente:** Textos comuns devem ter uma proporção de contraste de pelo menos **4.5:1** em relação ao fundo. Para textos grandes ou elementos de interface ativos, o contraste mínimo é **3:1**.
*   **Não depender apenas de cores:** Cores nunca devem ser o único meio de transmitir informação. Por exemplo, mensagens de erro em formulários não devem ser indicadas apenas pela borda vermelha do campo; deve-se incluir texto descritivo e, idealmente, um ícone (ex: `⚠️`).

---

## 4. Estrutura e Semântica do Código
*   **Hierarquia de Títulos:** Títulos de seção devem seguir uma ordem semântica clara utilizando as tags `<h1>` (título principal da página, apenas um por página), `<h2>` (seções secundárias), `<h3>` (subtópicos), etc., sem pular níveis (ex: saltar de `<h1>` para `<h4>`).
*   **Tags HTML Nativas:** Usar elementos nativos adequados (ex: usar `<button>` para ações que rodam scripts e `<a>` para navegação/redirecionamento), evitando criar componentes complexos usando apenas `<div>` sem a semântica adequada.
*   **Rótulos em Formulários:** Cada campo de entrada de dados (`<input>`) deve ter uma tag `<label>` explicitamente associada a ele pelo atributo `for`, permitindo que leitores de tela leiam o nome do campo ao focar nele.

---

## 5. Responsividade e Refluxo (Reflow)
*   **Suporte a Zoom:** O site deve continuar totalmente utilizável quando ampliado com zoom de até **200%** (sem quebrar texto ou esconder partes importantes) e até **400%** de refluxo (onde o site reorganiza as colunas em uma única coluna sem introduzir rolagem horizontal dupla).
*   **Evitar Oclusão:** Elementos flutuantes (como barras fixas de chat ou pop-ups) não devem encobrir outros componentes ou dificultar a leitura do conteúdo central em visualizações com zoom.

---

## 6. Controle pelo Usuário
*   **Mídia Controlável:** Qualquer vídeo ou áudio que toque de forma automática por mais de 3 segundos deve possuir um botão visível e acessível para pausar, parar ou silenciar.
*   **Carrosséis e Animações:** Slideshows automáticos devem permitir que o usuário pause o movimento a qualquer momento.
