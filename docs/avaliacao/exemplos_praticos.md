# Exemplos Práticos: Resultados e Achados da Avaliação do DETRAN-DF

> **Conteúdo:** Mapeamento detalhado dos problemas encontrados no portal, correlacionando-os com os critérios de acessibilidade (WCAG 2.2 e ABNT NBR 17225) e as 10 Heurísticas de Nielsen.

---

## Resultados da Avaliação (Achados de IHC & Acessibilidade)

Abaixo estão detalhados os principais pontos de falha identificados no portal principal do DETRAN-DF.

### [Achado 1] — Elementos de Interface sem Texto Alternativo ou Vazios
*   **Descrição:** A ferramenta WAVE identificou falhas graves de conteúdo não-textual, incluindo imagens vinculadas a links sem texto alternativo descritivo (*Missing alternative text* e *Linked image missing alternative text*), além de botões e links totalmente vazios (*Empty button* e *Empty link*), como o elemento localizado no card promocional lateral "Mulher Não se Cale!".
*   **Análise Técnico-Comportamental (Falso Positivo Visual):** Durante os testes manuais práticos, constatou-se que, sob a perspectiva de um usuário que utiliza o mouse, os botões e links secundários de serviços funcionam perfeitamente para disparar suas respectivas ações. Contudo, a auditoria automatizada acusa corretamente a existência de "elementos vazios" porque as tags de código correspondentes carecem por completo de textos internos reais ou de atributos de acessibilidade como `aria-label`. Visualmente, os botões exibem apenas imagens ou ícones ilustrativos, o que atende à usabilidade tradicional com mouse, mas falha na arquitetura técnica de acessibilidade. Sem uma descrição programática associada, os leitores de tela não conseguem identificar o propósito do link, anunciando apenas as palavras genéricas "botão" ou "link" para usuários cegos.
*   **Critério Violado:**
    *   **WCAG 2.2 / ABNT NBR 17225:** Critério de Sucesso 1.1.1 (Conteúdo Não-Textual — Nível A) e Critério de Sucesso 4.1.2 (Nome, Função, Valor — Nível A).
    *   **Guia do Gov.br:** Seção de Imagens e Componentes Semânticos Nativos.
*   **Heurística de Nielsen Violada:** Visibilidade do Status do Sistema / Flexibilidade e Eficiência de Uso.
*   **Gravidade:** Alta (Impede completamente a compreensão da ação ou imagem por usuários dependentes de leitores de tela).
*   **Sugestão de Correção:** Adicionar atributos `alt` descritivos em todas as imagens informativas e garantir que os botões e links possuam textos internos descritivos ou atributos `aria-label` explicitando sua função para tecnologias assistivas.

---

### [Achado 2] — Contraste de Texto Insuficiente
*   **Descrição:** Foram mapeados 39 pontos de baixíssimo contraste (*Very low contrast*) distribuídos pela interface, afetando menus superiores (Início, Veículos, CNH, Atendimento, Infração) e textos secundários do portal. A proporção de cor entre o texto e o fundo não atinge o limite mínimo exigido para legibilidade confortável.
*   **Critério Violado:**
    *   **WCAG 2.2 / ABNT NBR 17225:** Critério de Sucesso 1.4.3 (Contraste Mínimo — Nível AA).
    *   **Guia do Gov.br:** Diretrizes de Identidade Visual e Legibilidade de Cores.
*   **Heurística de Nielsen Violada:** Estética e Design Minimalista.
*   **Gravidade:** Alta (Prejudica severamente a leitura por usuários com baixa visão, catarata ou sob condições de iluminação natural externa).
*   **Sugestão de Correção:** Modificar os valores hexadecimais no arquivo de estilos CSS para paletas de cores mais escuras no texto em primeiro plano, forçando uma proporção de contraste mínima de 4,5:1.

---

### [Achado 3] — Ausência de Rótulos Permanentes em Formulários
*   **Descrição:** O WAVE apontou a existência de campos de entrada de dados que carecem de rótulos associados (*Missing form label*), como mecanismos de busca ou inputs de coleta de dados.
*   **Critério Violado:**
    *   **WCAG 2.2 / ABNT NBR 17225:** Critério de Sucesso 3.3.2 (Rótulos ou Instruções — Nível A).
    *   **Guia do Gov.br:** Seção de Formulários e Acessibilidade de Entrada de Dados.
*   **Heurística de Nielsen Violada:** Prevenção de Erros / Reconhecimento em vez de Recordação.
*   **Gravidade:** Média.
*   **Sugestão de Correção:** Implementar o uso explícito da tag HTML `<label>` programaticamente vinculada através do atributo `for` ao respectivo ID do campo de texto, garantindo que leitores de tela identifiquem o propósito do campo de forma inequívoca.

---

### [Achado 4] — Quebra na Hierarquia Semântica de Títulos
*   **Descrição:** A análise estrutural do WAVE expôs que o portal pula níveis lógicos na organização de seus cabeçalhos (*Skipped heading level*). O site transita de forma direta de um título principal `<h1>` para subtítulos de nível `<h4>` (como nos títulos "Veículos", "Habilitação", "Agendamento" e "Infração" do rodapé) sem passar sequencialmente pelos níveis `<h2>` ou `<h3>`.
*   **Critério Violado:**
    *   **WCAG 2.2 / ABNT NBR 17225:** Critério de Sucesso 1.3.1 (Informações e Relações — Nível A) e Critério de Sucesso 2.4.10 (Cabeçalhos de Seção — Nível AAA).
    *   **Guia do Gov.br:** Estruturação Lógica de Páginas e Navegabilidade.
*   **Heurística de Nielsen Violada:** Consistência e Padrões.
*   **Gravidade:** Média (Desorienta usuários cegos ou com limitação visual severa que utilizam os atalhos de teclado do leitor de tela para saltar de bloco em bloco de conteúdo).
*   **Sugestão de Correção:** Reestruturar semanticamente as tags do documento HTML, definindo uma árvore lógica coerente onde as seções principais abaixo do `<h1>` sejam marcadas obrigatoriamente como `<h2>`, seguidas por seus respectivos subitens como `<h3>` e `<h4>`.

---

### [Achado 5] — Dependência de Manipuladores de Eventos Vinculados ao Mouse
*   **Descrição:** Foram encontrados 23 pontos críticos no código em que ações e interações cruciais dependem estritamente de interações físicas atreladas a um ponteiro de mouse (*Device dependent event handler*). Elementos de navegação e botões utilizam gatilhos puramente lógicos de ponteiro sem fornecer equivalência em comandos de teclado.
*   **Critério Violado:**
    *   **WCAG 2.2 / ABNT NBR 17225:** Critério de Sucesso 2.1.1 (Teclado — Nível A).
    *   **Guia do Gov.br:** Princípios de Independência de Dispositivo de Entrada.
*   **Heurística de Nielsen Violada:** Flexibilidade e Eficiência de Uso / Controle e Liberdade do Usuário.
*   **Gravidade:** Alta/Gravíssima (Exclui por completo cidadãos com limitações motoras severas que operam computadores exclusivamente por teclados ou acionadores).
*   **Sugestão de Correção:** Configurar os scripts JavaScript de modo que, para cada manipulador de evento baseado em ponteiro (como `onmouseover` ou `onclick`), exista um manipulador de evento de teclado redundante correspondente (como `onfocus` ou `onkeydown`).

---

### [Achado 6] — Falha de Gerenciamento de Foco em Menus Suspensos
*   **Descrição:** Durante a validação manual de navegabilidade, observou-se que os itens do menu superior (como "Veículos", "CNH", "Atendimento" e "Infração") podem receber foco por meio da tecla `Tab`. Ao receberem foco, os respectivos submenus são exibidos visualmente na interface. Entretanto, ao continuar a navegação pelo teclado, o foco não percorre as opções internas desses submenus, sendo direcionado para outros elementos da página. Como consequência, a navegação pela barra principal torna-se inconsistente para usuários que dependem exclusivamente do teclado.
*   **Evidência do Teste Manual (Validação Prática):** Durante a inspeção heurística, verificou-se que o foco alcança os itens principais da barra de navegação superior, porém não é transferido para os links contidos nos submenus expandidos. Tentativas de interação utilizando as teclas `Tab`, `Enter` e `Espaço` não permitiram acessar as opções internas. Em alguns casos, a tecla `Espaço` provocou apenas a rolagem da página (*page scroll*), indicando que os componentes não foram implementados com suporte adequado.
*   **Critério Violado:**
    *   **WCAG 2.2 / ABNT NBR 17225:** Critério de Sucesso 2.1.1 (Teclado – Nível A) e Critério de Sucesso 2.4.3 (Ordem do Foco – Nível A).
    *   **Guia do Gov.br:** Seção de Menus de Navegação e Componentes Complexos.
*   **Heurística de Nielsen Violada:** Flexibilidade e Eficiência de Uso / Consistência e Padrões.
*   **Gravidade:** Alta a Gravíssima (Usuários que dependem exclusivamente do teclado não conseguem acessar serviços importantes disponibilizados apenas nos submenus).
*   **Sugestão de Correção:** Implementar o padrão de menus acessíveis recomendado pela WAI-ARIA, garantindo que os links internos dos submenus sejam incluídos na sequência de foco do teclado. O usuário deve conseguir navegar pelas opções internas utilizando `Tab` ou as teclas direcionais (`↑` e `↓`).

---

### [Achado 7] — Obstrução de Conteúdo por Elementos Flutuantes sob Ampliação de Tela (Zoom de 400%)
*   **Descrição:** Ao realizar o teste manual de ampliação de tela simulando a necessidade de usuários com baixa visão (zoom de até 400%), constatou-se que o portal aciona layouts responsivos. Contudo, elementos flutuantes fixos na interface — especificamente o widget do chatbot de atendimento e o card promocional lateral "Mulher Não se Cale!" — não acompanham o refluxo correto da página. Esses componentes se sobrepõem diretamente ao texto institucional e aos blocos de títulos principais, gerando oclusão.
*   **Critério Violado:**
    *   **WCAG 2.2 / ABNT NBR 17225:** Critério de Sucesso 1.4.10 (Refluxo - Nível AA) e Critério de Sucesso 2.4.11 (Foco Não Oculto - Nível AA).
    *   **Guia do Gov.br:** Diretrizes de Responsividade e Flexibilidade de Layout.
*   **Heurística de Nielsen Violada:** Estética e Design Minimalista / Flexibilidade e Eficiência de Uso.
*   **Gravidade:** Alta (Inviabiliza a leitura e a navegação em seções primárias da interface para usuários que dependem exclusivamente de ampliação de tela).
*   **Sugestão de Correção:** Configurar regras de mídia CSS (*Media Queries*) específicas para que elementos flutuantes e sobreposições decorativas ou de suporte (como chatbots e banners fixos) sejam movidos para o fluxo regular do rodapé ou fiquem ocultos de forma controlada quando a viewport atingir larguras equivalentes ao zoom de 400%, liberando a área de leitura principal.
