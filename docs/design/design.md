# Design — Checklist V2.0 (Integrado)

Este checklist cobre contraste, tipografia, foco, alvos de toque, movimento, reflow, feedback visual e drag & drop.  
Baseado em **WCAG 2.2 (AA)** , **ABNT NBR 17225:2025** e boas práticas Gov.br.  
> Marcação: **[NOVO]** (incluído na V2.0) • **[ATUALIZADO]** (ajustado por mudança de norma/entendimento).

---

## 1) Contraste de Texto e Elementos Não Textuais
- [ ] Texto normal com **contraste ≥ 4.5:1**; texto grande (≥ 18 pt regular ou 14 pt bold) **≥ 3:1**.
- [ ] **[ATUALIZADO]** Componentes de interface (bordas, ícones essenciais, controles) e **estados** (hover, focus, selected) com **contraste ≥ 3:1**.
- [ ] Informação **não depende só de cor** (use rótulo, padrão, ícone).

!!! success "Certo"
    Botão primário com texto 4.8:1; campo com borda e label legíveis; estado "erro" com ícone + texto.

!!! failure "Errado"
    Placeholder 2:1; ícone de ação sem contraste; status "vermelho/verde" sem texto.

---

## 2) Tipografia e Hierarquia Visual
- [ ] Títulos seguem hierarquia (`h1` → `h2` → `h3`) sem saltos artificiais.
- [ ] Tamanho base legível (~16px) e **line-height** adequado (1.4–1.6).
- [ ] Links distinguíveis (não apenas cor; sublinhado/estilo consistente).
- [ ] Espaçamento e alinhamento favorecem leitura e escaneabilidade.

!!! success "Certo"
    h1/h2/h3 em ordem; links sublinhados; parágrafos 16–18px com 1.5 de altura de linha.

!!! failure "Errado"
    h3 direto após h1; link apenas levemente azulado; blocos densos sem respiro.

- [ ] **[NOVO]** Evitar **texto justificado**; usar alinhamento à esquerda para blocos longos.
- [ ] **[NOVO]** Evitar **maiúsculas contínuas** e **fontes muito condensadas** em textos longos.
- [ ] **[NOVO]** O usuário pode **ajustar espaçamentos** (linhas, parágrafos, palavras, letras) **sem perda** de funcionalidade/leitura.

!!! success "Certo"
    Texto alinhado à esquerda, com espaçamento ajustável mantendo a legibilidade.

!!! failure "Errado"
    Parágrafos justificados criando "rios" de espaços; título todo em CAIXA ALTA.

---

## 3) Foco Visível e **Não Obscurecido**
- [ ] **[ATUALIZADO]** **Foco sempre visível**, com indicador perceptível (espessura/contraste).
- [ ] **[NOVO]** Foco **não fica atrás** de cabeçalhos/banners "sticky" (use `scroll-margin-top`/offset).

!!! success "Certo"
    Outline espesso e contrastado; ao usar "Ir para conteúdo", o h1 não fica sob o header fixo.

!!! failure "Errado"
    Foco 1px cinza quase invisível; foco escondido atrás do cabeçalho.

> *Plus (recomendado):* **Aparência do foco AAA** (2.4.13) — indicador amplo e evidente.

---

## 4) Alvos de Toque e Espaçamento
- [ ] **[NOVO]** Considera **2.5.8 Tamanho do alvo (AA)** , mantendo **área útil + espaçamento**.
- [ ] **[ATUALIZADO]** Alvos tocáveis têm **área confortável** e **espaçamento** seguro (ex.: referência prática de **24×24px CSS** quando aplicável).

!!! success "Certo"
    Ícones/botões com área generosa e espaço entre si; listas clicáveis com padding vertical.

!!! failure "Errado"
    Links minúsculos colados; ícones de 12px sem área clicável extra.

---

## 5) Animações, Movimento e Preferências do Usuário
- [ ] Respeita **`prefers-reduced-motion`** para reduzir/evitar animações intensas.
- [ ] **[NOVO]** Respeita **`prefers-contrast`** e **`color-scheme`** (claro/escuro) do sistema.
- [ ] Evita efeitos que causem desconforto; se usar, disponibiliza **controle** e redução.

!!! success "Certo"
    Transições suaves são reduzidas com `prefers-reduced-motion`; tema acompanha o SO.

!!! failure "Errado"
    Animações incessantes sem opção; "modo alto contraste" isolado que conflita com preferências do usuário.

---

## 6) Movimento, Flash e Atualizações Automáticas
- [ ] **[NOVO]** Evitar conteúdo que **pisca mais de 3 vezes por segundo** (ou garantir que fique abaixo do limite seguro).
- [ ] **[NOVO]** Conteúdos que **movem/rolam/atualizam automaticamente** oferecem **Pausar / Parar / Ocultar**.

!!! success "Certo"
    Carrossel com botões de pausar/anterior/próximo; ticker com opção de parar.

!!! failure "Errado"
    Carrossel automático sem controle; banner piscando repetidamente.

---

## 7) Layout Responsivo e Reflow
- [ ] Reflow sem perda de conteúdo/funcionalidade (zoom + responsividade).
- [ ] Tabelas e cards mantêm leitura (colunas colapsáveis ou scroll acessível).
- [ ] Evita rolagem **bidimensional** desnecessária.

!!! success "Certo"
    Grid responsivo; tabelas com colunas colapsáveis; conteúdo não salta ao focar.

!!! failure "Errado"
    Texto "vaza" da tela; truncamento crítico sem alternativa.

---

## 8) Estados, Mensagens e Feedback Visuais
- [ ] Estados (hover/focus/active/disabled/error/success) têm **diferença perceptível** (não só cor).
- [ ] Erros/ajuda são **claros** e próximos ao componente; ícones com rótulo/ou ajuda.

!!! success "Certo"
    Campo com erro exibe texto "CPF inválido" + ícone; hover muda cor e sublinhado.

!!! failure "Errado"
    Apenas borda vermelha sem texto; ícone "info" sem contexto.

---

## 9) Instruções e Conteúdo Ativado por Hover/Foco
- [ ] **[NOVO]** Instruções **não dependem** de características sensoriais (forma, cor, posição).
- [ ] **[NOVO]** Conteúdo que aparece em **hover/foco** pode ser **dispensado**, não obscurece outros elementos e permanece enquanto o foco estiver sobre ele.
- [ ] **[NOVO]** Evitar esconder informações relevantes de tecnologias assistivas com `display:none`/`visibility:hidden` de forma indevida.

!!! success "Certo"
    "Selecione o botão **Avançar**" (texto claro); tooltip que pode ser dispensada sem cobrir o campo.

!!! failure "Errado"
    "Clique no **botão redondo à direita**"; tooltip que cobre o formulário e some ao tentar interagir.

---

## 10) Drag & Drop com Alternativa
- [ ] **[NOVO]** Toda interação de **arrastar e soltar** tem **alternativa por clique/teclado**.

!!! success "Certo"
    Lista ordenável com botões "mover para cima/baixo"; upload com "Escolher arquivo".

!!! failure "Errado"
    Única forma de reordenar é arrastando.

---

## 11) Componentes Padrão e Semântica Visual
- [ ] Preferir **componentes nativos/semânticos** estilizados (botão, link, input).
- [ ] Ícones/textos de ação com propósito evidente; tooltip como apoio (não substitui rótulo quando necessário).

!!! success "Certo"
    `<button>` estilizado para ação; `<a>` para navegação; ícone com label claro.

!!! failure "Errado"
    `div` com `onclick` fazendo papel de botão sem estilos/estados.

---

## O que **remover/ajustar** (comparado ao pocket antigo)
- **Accesskey** como recomendação geral → **[ATUALIZADO]** : preferir **skip-link + landmarks + headings**; se usar, documente e evite conflitos com atalhos do navegador/SO.
- [ ] **[ATUALIZADO]** Em vez de um "modo" isolado, o site **respeita `prefers-contrast` e `color-scheme`** (claro/escuro) e já nasce com **contraste adequado** por padrão.
- **SC 4.1.1 (Parsing)** tratado como critério normativo → **[ATUALIZADO]** : considerar apenas **boa prática** (validar HTML/CSS); o SC foi removido na **WCAG 2.2**.

---

### Notas rápidas de implementação
- Indicador de foco: outline perceptível (espessura/contraste).
- Cabeçalho fixo: `scroll-margin-top` nos alvos de âncora/elementos focáveis.
- Tokens de design: padronizar cores/estados/espaçamentos para garantir contraste e consistência.

---

## Referências
- WCAG 2.2 — SC 1.4.3 (Contraste mínimo – texto)
- WCAG 2.2 — SC 1.4.11 (Contraste não textual)
- WCAG 2.2 — Uso de cor / Links distinguíveis / 3.3.* Mensagens (WAI – boas práticas)
- WCAG 2.2 — 2.4.* (Navegabilidade/Hierarquia), boas práticas de legibilidade (WAI)
- Guia Gov.br de Boas Práticas de Acessibilidade (conteúdo, links, comunicação clara)
- WCAG 2.2 — SC 2.4.7 (Foco visível)
- WCAG 2.2 — SC 2.4.11 / 2.4.12 (Foco não obscurecido)
- WCAG 2.2 — SC 2.4.13 (Aparência do foco – AAA, recomendado)
- NBR 17225:2025 — Diretrizes visuais/UX; princípios de ergonomia e usabilidade
- WCAG 2.2 — SC 2.5.8 (Tamanho do alvo – AA)
- WCAG 2.2 — 2.3.* (Animação/movimento); `prefers-reduced-motion`
- WAI / CSS Media Queries — `prefers-contrast` e `color-scheme` (tema claro/escuro)
- WCAG 2.2 — SC 1.4.10 (Reflow) e 1.4.4 (Resize text)
- WCAG 2.2 — SC 2.5.7 (Movimentos de arrastar – alternativa por clique/teclado)
- WAI-ARIA Authoring Practices — semântica e padrões de interação acessível
- Mudanças da WCAG 2.2 — remoção do SC 4.1.1 (Parsing)
- Itens práticos da página "Design" do Grupo 05 (2025.2) (estrutura e exemplos de tipografia/contraste/alvos).
- WCAG 2.2 — SC 1.4.12 (Text Spacing).
- WCAG 2.2 — SC 1.3.3 (Sensory Characteristics).
- WCAG 2.2 — SC 1.4.13 (Content on Hover or Focus).
- WAI-ARIA / Boas práticas — visibilidade e disponibilidade de informação para TA.
- WCAG 2.2 — SC 2.3.1 (Three Flashes or Below Threshold).
- WCAG 2.2 — SC 2.2.2 (Pause, Stop, Hide).