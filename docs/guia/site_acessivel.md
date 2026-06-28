# O que um site precisa para ser acessível?

> **Conteúdo:** Guia prático dos pilares e elementos essenciais que devem estar presentes em qualquer website para garantir conformidade básica de acessibilidade (WCAG 2.2 nível AA e NBR 17225).

Para que um site seja considerado acessível, ele deve contemplar, no mínimo, as seguintes implementações:

---

## 1. Alternativas de Texto (Conteúdo Não-Textual)

- **Imagens descritivas:** Todas as imagens que transmitem informação devem ter o atributo `alt` preenchido com uma descrição clara e objetiva do seu conteúdo.
- **Imagens decorativas:** Imagens puramente decorativas (como bordas ou ícones de fundo que não agregam informação) devem usar `alt=""` (vazio) ou `aria-hidden="true"`, para serem ignoradas pelos leitores de tela.
- **Elementos vazios:** Links ou botões representados apenas por ícones gráficos (ex: um ícone de lupa para pesquisa ou ícone de redes sociais) devem conter o atributo `aria-label` especificando a sua ação.

---

## 2. Navegabilidade Completa via Teclado

- **Independência de mouse:** Qualquer ação que possa ser realizada pelo mouse (clicar em botões, abrir submenus, navegar em carrosséis, fechar modais) deve poder ser executada apenas usando as teclas `Tab`, `Enter`, `Espaço` e as direcionais (`Arrows`).
- **Indicador de foco visível:** O indicador de foco (aquela borda que aparece ao redor de links e botões selecionados) nunca deve ser ocultado por CSS (`outline: none` é proibido). Ele deve ter espessura e contraste suficientes para ser percebido por usuários de teclado.
- **Ordem lógica de foco:** A navegação pelo teclado deve seguir uma ordem lógica de leitura (de cima para baixo, da esquerda para direita).
- **Atalho para o conteúdo (Skip Link):** Um link invisível no topo da página que aparece ao receber o foco do teclado, permitindo ao usuário "pular" o menu de navegação e ir direto para o conteúdo principal.
- **Evitar "tab traps":** Garantir que o foco não fique preso em componentes como modais e menus, permitindo que o usuário sempre consiga navegar para frente e para trás.

---

## 3. Uso Correto e Inclusivo de Cores

- **Contraste suficiente:**
  - Textos comuns: proporção de contraste de pelo menos **4.5:1** em relação ao fundo.
  - Textos grandes (acima de 18px ou 14px em negrito) e elementos de interface ativos: contraste mínimo **3:1**.
- **Não depender apenas de cores:** Cores nunca devem ser o único meio de transmitir informação. Por exemplo, mensagens de erro em formulários não devem ser indicadas apenas pela borda vermelha do campo; deve-se incluir:
  - Texto descritivo adicional
  - Ícones (ex: `⚠️`)
  - Padrões ou texturas (especialmente em gráficos e visualizações de dados)

---

## 4. Estrutura e Semântica do Código

- **Hierarquia de títulos:** Títulos de seção devem seguir uma ordem semântica clara utilizando as tags `<h1>` (título principal da página, apenas um por página), `<h2>` (seções secundárias), `<h3>` (subtópicos), etc., sem pular níveis (ex: saltar de `<h1>` para `<h4>`).
- **Tags HTML nativas:** Usar elementos nativos adequados (ex: usar `<button>` para ações que rodam scripts e `<a>` para navegação/redirecionamento), evitando criar componentes complexos usando apenas `<div>` sem a semântica adequada.
- **Rótulos em formulários:** Cada campo de entrada de dados (`<input>`) deve ter uma tag `<label>` explicitamente associada a ele pelo atributo `for`, permitindo que leitores de tela leiam o nome do campo ao focar nele.
- **Listas e tabelas:**
  - Utilizar `<ul>` e `<ol>` para listas de itens, garantindo que leitores de tela identifiquem corretamente a estrutura.
  - Em tabelas de dados, usar `<th scope="col">` ou `scope="row"` para associar cabeçalhos às células correspondentes.

---

## 5. Responsividade e Refluxo (Reflow)

- **Suporte a zoom:** O site deve continuar totalmente utilizável quando ampliado com zoom de até **200%** (sem quebrar texto ou esconder partes importantes).
- **Refluxo em 320px:** Em largura equivalente a **320 CSS pixels**, o conteúdo deve ser reorganizado em coluna única, sem introduzir rolagem horizontal dupla (WCAG 2.2 critério 1.4.10).
- **Evitar oclusão:** Elementos flutuantes (como barras fixas de chat ou pop-ups) não devem encobrir outros componentes ou dificultar a leitura do conteúdo central em visualizações com zoom.

---

## 6. Controle pelo Usuário

- **Mídia controlável:** Qualquer vídeo ou áudio que toque de forma automática por mais de 3 segundos deve possuir um botão visível e acessível para pausar, parar ou silenciar.
- **Carrosséis e animações:** Slideshows automáticos devem permitir que o usuário pause o movimento a qualquer momento.

---

## 7. Links e Mensagens Claras

- **Links descritivos:** Evitar textos genéricos como "clique aqui". Os links devem conter descrições claras do destino ou ação (ex: "Baixar o relatório anual" em vez de "Clique aqui para baixar").
- **Mensagens de erro em formulários:** Indicar claramente quais campos estão inválidos, descrever o erro cometido e fornecer orientações sobre como corrigi-lo, utilizando texto descritivo além de indicações visuais como cores ou ícones.

---

## 8. Gerenciamento de Tempo

- **Sessões com timeout:** Alertar o usuário antes que uma sessão expire e oferecer a opção de estender o tempo de forma simples e acessível, evitando perda de dados ou interrupções bruscas.

---

> **Lembrete:** Este guia cobre os requisitos mínimos para conformidade básica. Testes com usuários reais, incluindo pessoas com deficiência, e auditorias especializadas são complementos essenciais para uma acessibilidade plena.