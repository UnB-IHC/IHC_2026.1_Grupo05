# O que é a WCAG 2.2?

> **Responsável pela Seção:** Colega  
> **Conteúdo:** Visão geral das Diretrizes de Acessibilidade para Conteúdo Web (WCAG) em sua versão 2.2, explicando seus princípios e níveis de conformidade.

As **Diretrizes de Acessibilidade para Conteúdo Web (WCAG)**, desenvolvidas pela W3C (World Wide Web Consortium), estabelecem padrões internacionais para tornar o conteúdo da web mais acessível a pessoas com deficiência. A versão mais recente é a **WCAG 2.2**.

---

## Os 4 Princípios da Acessibilidade (P.O.U.R.)

As diretrizes são organizadas sob quatro princípios fundamentais, que definem as bases para um site acessível:

### 1. Percebível (*Perceivable*)
A informação e os componentes da interface do usuário devem ser apresentados de maneira que possam ser percebidos pelos sentidos dos usuários.
*   **Exemplos práticos:** Texto alternativo para imagens, legendas para vídeos, transcrição de áudios, contraste adequado entre o texto e o fundo.
*   *Não pode ser invisível a todos os sentidos de um usuário.*

### 2. Operável (*Operable*)
Os componentes da interface do usuário e a navegação devem ser operáveis por diferentes meios de entrada.
*   **Exemplos práticos:** Todo o site ser utilizável usando apenas o teclado, dar tempo suficiente para leitura e interação, evitar intermitências/flashes rápidos de tela que possam causar convulsões, e facilidade de navegação (skip-links, títulos coerentes).
*   *A interface não pode exigir interações que o usuário não consiga realizar (como depender apenas de mouse).*

### 3. Compreensível (*Understandable*)
A informação e a operação da interface do usuário devem ser fáceis de entender.
*   **Exemplos práticos:** Indicar claramente o idioma da página, evitar jargões complexos sem explicação, tornar os inputs previsíveis, e oferecer mensagens de erro e ajuda de entrada claras para prevenir e corrigir erros em formulários.
*   *O usuário precisa compreender as informações e como operar a interface.*

### 4. Robusto (*Robust*)
O conteúdo deve ser robusto o suficiente para ser interpretado de forma confiável por uma ampla variedade de agentes de usuário, incluindo tecnologias assistivas (como leitores de tela).
*   **Exemplos práticos:** Código limpo e semântico (HTML correto), uso apropriado de atributos ARIA para descrever o nome, a função e o valor de componentes personalizados.
*   *O site deve continuar compatível com as tecnologias atuais e futuras.*

---

## Níveis de Conformidade

Para fins de avaliação e conformidade legal, os critérios de sucesso da WCAG são classificados em três níveis de prioridade e exigência:

| Nível | Impacto e Descrição |
|---|---|
| **Nível A** | **Crítico / Acessibilidade Básica**: Define os requisitos mínimos de acessibilidade. Sem estes critérios, partes do site ficam completamente bloqueadas para alguns grupos de usuários. Ex: Alternativa para imagens e navegação por teclado. |
| **Nível AA** | **Recomendado / Legislação Global**: É o nível padrão exigido pela maioria das regulamentações de acessibilidade no mundo (incluindo o Gov.br e a NBR 17225). Remove as barreiras mais comuns de usabilidade. Ex: Contraste mínimo de texto (4,5:1) e responsividade com refluxo. |
| **Nível AAA** | **Avançado / Alta Acessibilidade**: O nível máximo de conformidade. Exige melhorias visuais e estruturais profundas. Alguns critérios de nível AAA não podem ser aplicados em todo tipo de conteúdo. Ex: Contraste aprimorado (7:1) e alternativas completas para mídias ao vivo. |

---

## Relação com as Normas Brasileiras

*   **ABNT NBR 17225 (Web):** Adota oficialmente os critérios da WCAG 2.2 níveis A e AA para o contexto nacional.
*   **ABNT NBR 17060 (Mobile):** Trata especificamente de aplicativos móveis, incorporando os critérios de orientação, alvos de toque e acessibilidade de gestos.
