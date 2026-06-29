# Gestão e Governança — Checklist V3.0

Este checklist apoia lideranças, coordenadores e gestores de produto a incluir acessibilidade como critério de qualidade desde o planejamento estratégico até a entrega contínua.

Baseado em **WCAG 2.2 (AA)** , **ABNT NBR 17225:2025**, **Lei Brasileira de Inclusão (LBI)** e boas práticas de governança em acessibilidade digital.

---

## 1) Planejamento Estratégico e Escopo

- [ ] A acessibilidade foi incluída no **escopo inicial** do projeto (não como item futuro ou melhoria opcional).
- [ ] O orçamento prevê recursos para:
  - [ ] Contratação de **especialistas em acessibilidade** (consultoria, auditoria).
  - [ ] **Testes com pessoas com deficiência** (remuneração justa aos participantes).
  - [ ] **Ferramentas de teste** (leitores de tela, validadores, simuladores).
  - [ ] **Capacitação da equipe** (treinamentos e workshops).
- [ ] O cronograma inclui tempo dedicado para **implementação e correção de itens de acessibilidade**.
- [ ] O projeto segue o princípio do **Desenho Universal** (usável por todas as pessoas, sem necessidade de adaptação prévia).
- [ ] A acessibilidade é tratada como **requisito não funcional**, com critérios de aceite claros.

!!! success "Certo"
    Projeto com verba para testes com usuários com deficiência, consultoria especializada e treinamento da equipe em acessibilidade.

!!! failure "Errado"
    "Acessibilidade será tratada depois do lançamento" ou "não temos orçamento para isso agora".

---

## 2) Equipe e Envolvimento

- [ ] Pessoas com deficiência estão envolvidas na equipe ou no **grupo de testes**.
- [ ] Há pelo menos uma pessoa com **conhecimento técnico em acessibilidade** na equipe (ou consultoria contratada).
- [ ] A equipe recebeu **treinamento básico** sobre acessibilidade digital e WCAG.
- [ ] As **personas** são heterogêneas e incluem:
  - [ ] Pessoas com deficiência visual (cegueira, baixa visão)
  - [ ] Pessoas com deficiência auditiva (surdez, baixa audição)
  - [ ] Pessoas com deficiência motora (dificuldade de locomoção, uso limitado de mouse)
  - [ ] Pessoas com deficiência cognitiva (dislexia, TDAH, baixo letramento digital)
  - [ ] Pessoas com múltiplas deficiências
  - [ ] Pessoas idosas e com baixo letramento digital

!!! success "Certo"
    Personas incluem "Ana, 45 anos, baixa visão, usa leitor de tela" e "Carlos, 70 anos, baixo letramento digital".

!!! failure "Errado"
    Todas as personas são jovens, sem deficiência e com alto domínio tecnológico.

---

## 3) Processo de Design e Desenvolvimento

- [ ] A acessibilidade é considerada em **todas as etapas do ciclo de vida** do produto (descoberta, design, desenvolvimento, testes, lançamento, manutenção).
- [ ] Existe um **guia de estilo/design system** que inclui tokens de acessibilidade (cores, tipografia, espaçamentos, estados).
- [ ] Os checklists de **conteúdo, design e desenvolvimento** são aplicados antes do deploy.
- [ ] Há revisão de **código com foco em acessibilidade** (code review com checklist específico).
- [ ] Ferramentas de **validação automática** (axe, Lighthouse, WAVE) são integradas ao pipeline de CI/CD.

!!! success "Certo"
    Pipeline de CI/CD inclui validação automática de acessibilidade; design system com tokens de contraste e foco.

!!! failure "Errado"
    Acessibilidade só é verificada no final do projeto, quando as correções são mais caras.

---

## 4) Definition of Done (DoD)

- [ ] A acessibilidade é um critério de **pronto (DoD)** para todas as tarefas.
- [ ] Cada entregável deve passar pelos checklists de:
  - [ ] **Conteúdo** (textos, imagens, vídeos, links, documentos)
  - [ ] **Design** (contraste, tipografia, foco, alvos de toque, movimento)
  - [ ] **Desenvolvimento** (semântica, teclado, formulários, ARIA, autenticação)
- [ ] Nenhuma tarefa é considerada concluída sem atender aos critérios mínimos de acessibilidade (nível AA).

!!! success "Certo"
    "DoD: tarefa concluída, revisada e com checklists de acessibilidade aprovados."

!!! failure "Errado"
    "Fazemos acessibilidade depois" ou "não temos tempo para isso agora".

---

## 5) Testes e Validação

- [ ] A equipe realiza **testes manuais** regulares com:
  - [ ] Navegação por teclado (Tab, Enter, Espaço, Setas)
  - [ ] Leitores de tela (NVDA, JAWS, VoiceOver, TalkBack)
  - [ ] Zoom e ampliação (até 200% e 400%)
  - [ ] Alto contraste e temas escuros
- [ ] Testes com **pessoas com deficiência** são realizados em diferentes fases do projeto.
- [ ] Os resultados dos testes são **documentados** e priorizados para correção.
- [ ] Há um processo para **coleta de feedback** de usuários com deficiência em produção.

!!! success "Certo"
    Testes mensais com usuários com deficiência; backlog de acessibilidade priorizado por severidade.

!!! failure "Errado"
    Nenhum teste com usuários reais; feedback de acessibilidade ignorado.

---

## 6) Monitoramento e Manutenção Contínua

- [ ] Há um **plano de manutenção** para garantir que novas funcionalidades não quebrem acessibilidade existente.
- [ ] A acessibilidade é verificada em **cada novo release** (regressão de acessibilidade).
- [ ] O time monitora **métricas de acessibilidade** (ex: erros de contraste, ausência de `alt`, problemas de foco).
- [ ] Há um **processo de resposta a incidentes** de acessibilidade (ex: usuários reportam barreiras).
- [ ] O time se mantém atualizado sobre **novas versões da WCAG** e mudanças nas normas brasileiras.

!!! success "Certo"
    Release notes incluem "manutenção de acessibilidade"; monitoramento contínuo com ferramentas.

!!! failure "Errado"
    Depois do lançamento, ninguém mais verifica acessibilidade até a próxima grande reformulação.

---

## 7) Conformidade Legal e Normativa

- [ ] O produto atende aos critérios **nível AA da WCAG 2.2**.
- [ ] O site/aplicativo está em conformidade com a **ABNT NBR 17225 (Web)** e/ou **ABNT NBR 17060 (Mobile)**.
- [ ] O produto respeita a **Lei Brasileira de Inclusão (LBI - Lei 13.146/2015)**.
- [ ] Para sites governamentais, segue o **eMAG (Modelo de Acessibilidade em Governo Eletrônico)**.
- [ ] A política de privacidade e termos de uso incluem **compromisso com acessibilidade**.

!!! success "Certo"
    Declaração de acessibilidade pública no rodapé do site; selo de conformidade com a LBI.

!!! failure "Errado"
    Nenhum documento formal sobre acessibilidade; site não declara conformidade com a WCAG.

---

## 8) Comunicação e Transparência

- [ ] O site possui uma **declaração de acessibilidade** pública, com:
  - [ ] Nível de conformidade (ex: WCAG 2.2 AA)
  - [ ] Data da última avaliação
  - [ ] Canais para reportar barreiras de acessibilidade
  - [ ] Compromisso com a melhoria contínua
- [ ] A equipe se comunica de forma **transparente** sobre o status da acessibilidade do produto.
- [ ] Feedbacks de usuários com deficiência são **respondidos e priorizados**.

!!! success "Certo"
    Página "Acessibilidade" no site com declaração de conformidade, data da última avaliação e e-mail para contato.

!!! failure "Errado"
    Nenhuma menção à acessibilidade em canais oficiais; feedbacks ignorados.

---

## 9) Capacitação e Cultura

- [ ] A equipe participa de **treinamentos periódicos** sobre acessibilidade digital.
- [ ] A acessibilidade é incluída no **onboarding de novos colaboradores**.
- [ ] A cultura da equipe valoriza a **inclusão e diversidade**.
- [ ] Há **liderança engajada** e que promove acessibilidade como prioridade estratégica.

!!! success "Certo"
    Treinamento anual de acessibilidade para todos os times; acessibilidade é tema recorrente em retrospectivas.

!!! failure "Errado"
    Apenas uma pessoa na equipe sabe sobre acessibilidade; ninguém mais se sente responsável.

---

## O que **remover/ajustar** (comparado ao pocket antigo)

- **Acessibilidade como "extra"** → **[NOVO]** : acessibilidade é parte do **critério de qualidade mínimo**.
- **Projetos sem testes com usuários** → **[NOVO]** : testes com pessoas com deficiência são **obrigatórios**.
- **Ausência de plano de manutenção** → **[NOVO]** : acessibilidade deve ser **monitorada continuamente** após o lançamento.

---

### Notas rápidas para gestão

- Incluir acessibilidade no **orçamento e cronograma** desde o início reduz custos futuros.
- **Testes com usuários reais** são insubstituíveis para identificar barreiras não previstas em checklists.
- A acessibilidade é um **processo contínuo**, não um destino final.
- Produtos acessíveis alcançam **mais pessoas** e melhoram a experiência de **todos os usuários**.

---

## Referências

- **WCAG 2.2** — Diretrizes completas de acessibilidade
- **ABNT NBR 17225:2025** — Acessibilidade em serviços digitais web
- **ABNT NBR 17060** — Acessibilidade em aplicativos móveis
- **Lei Brasileira de Inclusão (LBI - Lei 13.146/2015)** — Marco legal da acessibilidade no Brasil
- **eMAG** — Modelo de Acessibilidade em Governo Eletrônico
- **Guia de Boas Práticas Gov.br** — Recomendações para sites governamentais
- **Desenho Universal** — Princípios de design inclusivo
- **WAI - W3C Web Accessibility Initiative** — Recursos e boas práticas internacionais