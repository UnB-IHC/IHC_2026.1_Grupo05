# Desenvolvimento Web — Checklist V3.0 (Integrado)

Práticas de implementação para HTML, ARIA, formulários, navegação por teclado, foco, autenticação e padrões de interação.  
Baseado em **WCAG 2.2 (AA)** , **ABNT NBR 17225:2025** e WAI-ARIA Authoring Practices.  
> Marcação: **[NOVO]** (incluído na V3.0) • **[ATUALIZADO]** (ajustado por mudança de norma/entendimento).

<div class="checklist-progress" data-checklist-progress></div>

---

## 1) Semântica, Estrutura e Navegação
- [ ] Documento tem **um `<h1>`** descritivo e hierarquia correta (`h2`/`h3`...).
- [ ] Uso de **landmarks**: `<header>`, `<nav>`, `<main>`, `<aside>`, `<footer>` (um `<main>` por página).
- [ ] **Links** são `<a>` (navegação) e **ações** são `<button>` (evento).
- [ ] Elementos interativos **não são** `div/span` com `onclick` sem papéis/teclado.

!!! success "Certo"
    Navegação com `<nav>` e links; botão de abrir modal em `<button>` com `aria-expanded`.

!!! failure "Errado"
    `div` com `onclick` para navegar; múltiplos `<main>`; títulos pulando níveis.

- [ ] **[NOVO]** Em **tabelas de dados**, usar `<th>` e `scope` apropriado (col/row); quando útil, fornecer `<caption>` descritivo.
- [ ] **[NOVO]** **Links que abrem em nova aba/janela** informam claramente o usuário no texto ou por rótulo acessível.

!!! success "Certo"
    `<th scope="col">Preço</th>`; `<caption>Tabela de tarifas 2025</caption>`  
    "Relatório Anual **(abre em nova aba)**"

!!! failure "Errado"
    Tabela só com `<td>`; link que abre nova aba sem aviso.

---

## 2) Teclado, Ordens e Armadilhas
- [ ] Toda funcionalidade é **operável por teclado** (Tab/Shift+Tab/Enter/Espaço/Setas).
- [ ] **Sem armadilha de teclado** (é possível sair de modais/menus por Tab/ESC).
- [ ] **Ordem de foco** segue a ordem visual e lógica do conteúdo.
- [ ] **Skip link** para "Ir ao conteúdo principal" no topo.

!!! success "Certo"
    Modal prende foco dentro e devolve ao botão que o abriu ao fechar.

!!! failure "Errado"
    Componente acessível só por mouse; foco some atrás de cabeçalho fixo.

---

## 3) Formulários: Rótulos, Ajuda e Erros
- [ ] Todo **input** tem **`<label>` visível** ou nome acessível (`aria-label/aria-labelledby`).
- [ ] Mensagens de erro são **próximas** ao campo, com **texto claro** e relação por `aria-describedby`.
- [ ] **Sugestões** (SC 3.3.3) e **prevenção de erro** (3.3.4) em transações importantes (financeiras/legais).
- [ ] **Propósito de entrada** (autocompletes) para dados pessoais/conta (SC 1.3.5).
- [ ] **[NOVO]** **Agrupar campos relacionados** (ex.: múltiplos checkboxes/radios) com `<fieldset>` e `<legend>` para indicar relação semântica.

!!! success "Certo"
    `<label for="cpf">CPF</label>` + erro "CPF inválido" ligado ao input via `aria-describedby="cpf-erro"`.

!!! failure "Errado"
    Placeholder como "label"; erro só com borda vermelha sem texto.

---

## 4) Mensagens de Status e Live Regions
- [ ] Mudanças dinâmicas relevantes usam **ARIA live** (`role="status"`, `aria-live="polite/assertive"`).
- [ ] Mensagens não movem foco **sem necessidade** e são anunciadas por leitores de tela.

!!! success "Certo"
    "Item adicionado ao carrinho" em `role="status"`.

!!! failure "Errado"
    Snackbar surge fora de foco e não é lido; atualização silenciosa de erro.

- [ ] **[NOVO]** **Áudio automático** com duração > 3 s oferece **pausar/parar** ou controle de **volume**.

!!! success "Certo"
    Player com botão de pausar; controle de volume disponível.

!!! failure "Errado"
    Áudio que toca sozinho sem controle algum.

---

## 5) Autenticação Acessível **[NOVO]**
- [ ] Permite **colar** senhas/códigos; funciona com **gerenciadores de senha**.
- [ ] Oferece alternativa a **desafios cognitivos** (link mágico, gestor do SO/biometria quando aplicável).
- [ ] Não exige **memorização** como única via de login.

!!! success "Certo"
    2FA por app/código; "Entrar por e-mail (link mágico)".

!!! failure "Errado"
    Bloquear "colar" no input; CAPTCHA sem alternativa acessível.

---

## 6) Entrada Redundante **[NOVO]**
- [ ] Não **repetir** dados já informados; **pré-preencher** quando possível e seguro.

!!! success "Certo"
    Endereço digitado na etapa 1 já aparece na etapa 2 para conferência.

!!! failure "Errado"
    Exigir redigitar CPF/endereço sem motivo.

- [ ] **[NOVO]** **Orientação do dispositivo** (retrato/paisagem) **não é requisito** para usar o conteúdo; não "travar" layout em uma única orientação sem justificativa funcional.

---

## 7) Drag & Drop com Alternativa **[NOVO]**
- [ ] Toda interação de **arrastar e soltar** tem **alternativa por clique/teclado** (ordenar, mover, anexar).

!!! success "Certo"
    Botões "mover para cima/baixo" em listas ordenáveis; upload com botão "Escolher arquivo".

!!! failure "Errado"
    Reordenar só por arrastar.

---

## 8) Padrões de Ponteiro e Gestos
- [ ] **Gestos complexos** (arrastar, pinçar, multi-toque) têm **alternativa** de **toque único/clique**.
- [ ] **Cancelamento por ponteiro**: ações por toque/click podem ser **abortadas** (não "dispara ao pressionar").

!!! success "Certo"
    Slide carrega com botões anterior/próximo; ação só conclui ao soltar/clicar.

!!! failure "Errado"
    "Pressionar" já executa sem chance de cancelar; só gestos complexos.

---

## 9) Conteúdo Dinâmico: Hover/Foco e Movimento
- [ ] Conteúdo que aparece em **hover/foco** pode ser **dispensado**, não obscurece e persiste enquanto houver foco.
- [ ] Conteúdos que **movem/rolam/atualizam** oferecem **Pausar / Parar / Ocultar**.
- [ ] Evitar **flash** acima de 3 vezes/seg (ou manter abaixo do limiar seguro).

!!! success "Certo"
    Tooltip dispensável; carrossel com pausar/anterior/próximo.

!!! failure "Errado"
    Banner piscando; tooltip que cobre formulário e some ao tentar interagir.

---

## 10) Idioma, Títulos e Metadados
- [ ] **Idioma da página** (`<html lang="pt-BR">`) e **partes** com idioma distinto (`lang`).
- [ ] **Título de página** é único e descreve o conteúdo principal.
- [ ] Metadados de **viewport** e zoom não bloqueado; não usar `user-scalable=no`.

!!! success "Certo"
    `<html lang="pt-BR">` e citação em inglês marcada com `lang="en"`.

!!! failure "Errado"
    Página em PT sem `lang`; zoom bloqueado em mobile.

---

## 11) Nomes, Papéis e Estados (Name, Role, Value)
- [ ] Componentes custom têm **nome acessível**, **papel** e **estado/valor** expostos (ARIA conforme APG).
- [ ] **Evitar ARIA desnecessária** quando o elemento nativo atende.

!!! success "Certo"
    Componente "switch" custom segue APG: `role="switch"`, `aria-checked`, teclado com Espaço/Enter.

!!! failure "Errado"
    `div role="button"` sem responder ao teclado; `aria-*` conflitando com nativo.

---

## 12) Tempo e Sessão
- [ ] Informar **tempo limite** e oferecer forma de **estender** a sessão antes de expirar.
- [ ] Processos longos indicam **progresso** e preservam dados em caso de expiração.

!!! success "Certo"
    Aviso "Sua sessão expira em 2 min. Deseja estender?" com botão "Estender".

!!! failure "Errado"
    Sessão expira sem alerta e perde o formulário.

---

## O que **remover/ajustar** (comparado ao pocket antigo)
- **SC 4.1.1 (Parsing)** tratado como critério normativo → **[ATUALIZADO]** : considerar só como **boa prática** (validar HTML/CSS); o SC foi removido na **WCAG 2.2**.
- **Accesskey** como recomendação geral → **[ATUALIZADO]** : preferir **skip-link + landmarks + headings**; se usar, documente e evite conflitos com atalhos do navegador/SO.

---

### Notas rápidas de implementação
- Use elementos nativos sempre que possível; complemente com ARIA **apenas** quando necessário.
- Garanta testes com teclado, NVDA/Firefox, JAWS/Chrome, VoiceOver/Safari e TalkBack/Chrome.
- Validação automática ajuda, mas **não substitui** testes manuais com TA e usuários.

---

## Referências
- WCAG 2.2 — 2.4.* (Títulos e navegação)
- WCAG 2.2 — Landmarks / Padrões de navegação; skip link
- WAI-ARIA Authoring Practices (APG) — uso de elementos nativos vs. ARIA
- WCAG 2.2 — 2.1.1 (Teclado)
- WCAG 2.2 — 2.1.2 (Sem armadilha de teclado)
- WCAG 2.2 — 2.4.3 (Ordem de foco)
- WCAG 2.2 — 3.3.2 (Rótulos ou instruções)
- WCAG 2.2 — 3.3.1 / 3.3.3 (Erros: identificação e sugestões)
- WCAG 2.2 — 3.3.4 (Prevenção de erro — financeiro/legais)
- WCAG 2.2 — 1.3.5 (Purpose of Input — autocompletes)
- WCAG 2.