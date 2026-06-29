# Conteúdo — Checklist V3.0 (Integrado)

Boas práticas para textos, imagens (simples e complexas), ícones, vídeos/podcasts, hyperlinks, documentos baixáveis e linguagem inclusiva.  
Baseado em **WCAG 2.2 (AA)** , **ABNT NBR 17225:2025** e Guia Gov.br.  
> Marcação: **[NOVO]** (incluído na V3.0) • **[ATUALIZADO]** (ajustado por mudança de norma/entendimento).

---

## 1) Estrutura Geral e Navegação
- [ ] Página tem **título descritivo e único**.
- [ ] Cabeçalhos em **hierarquia lógica** (H1 → H2 → H3…), sem "pular" níveis.
- [ ] **Idioma da página** e de trechos copiados está configurado (`lang`).
- [ ] Há **mais de uma forma** de encontrar páginas (menu, busca, índice).
- [ ] **[NOVO]** Instruções **não dependem de características sensoriais** (cor, forma, posição).

!!! success "Certo"
    H1 "Guia de Tarifas 2025"; H2 "Preços"; H3 "Isenções". Trecho em inglês marcado com `lang="en"`.

!!! failure "Errado"
    H1 → H3 sem H2; instrução "clique no botão **redondo à direita**".

---

## 2) Termos e Linguagem Inclusiva
- [ ] Usar **"pessoas com deficiência (PCD)"** e especificações corretas (pessoa surda, pessoa cega etc.).
- [ ] Evitar termos capacitistas e generalizações; priorizar **pessoa antes da condição**.

!!! success "Certo"
    "Pessoas cegas podem…"; "Pessoas surdas usuárias de Libras…".

!!! failure "Errado"
    "Os deficientes…"; "O autista".

---

## 3) Textos e Legibilidade
- [ ] Texto **claro, direto**, com vocabulário conhecido; evitar jargões.
- [ ] Explicar siglas na primeira ocorrência.
- [ ] Frases curtas (≈15–20 palavras) e **ordem direta** (SVO).
- [ ] **[ATUALIZADO]** Links **descritivos** (evitar "clique aqui").
- [ ] **[NOVO]** **Espaçamento de texto** pode ser aumentado (linhas, parágrafos, letras, palavras) **sem perda** de conteúdo/funcionalidade.

!!! success "Certo"
    "Baixe o **Relatório Anual 2024**"; "Associação Brasileira de Normas Técnicas (ABNT)".

!!! failure "Errado"
    "Clique aqui"; parágrafos longos e densos sem respiro.

---

## 4) Descrição de Imagens (simples)
- [ ] Fornecer **texto alternativo** significativo: quem/o quê, onde, ação/estado.
- [ ] Imagens **decorativas** usam `alt=""`.
- [ ] Evitar **imagem de texto**; prefira texto real.

!!! success "Certo"
    `alt="Pessoa escrevendo em caderno sobre uma mesa de madeira."`

!!! failure "Errado"
    `alt="imagem123.jpg"`; banner com frase como imagem sem texto real.

---

## 5) Imagens Complexas (gráficos, mapas, infográficos)
- [ ] **Descrição longa** próxima ao gráfico, explicando **o que mostrar e os dados**.
- [ ] **Alt curto** indica onde está a descrição longa.
- [ ] Disponibilizar os **dados em tabela** quando aplicável.

!!! success "Certo"
    `alt="Gráfico de pizza do uso de navegadores; descrição detalhada na tabela a seguir."`

!!! failure "Errado"
    Apenas `alt` genérico; dados só no gráfico.

---

## 6) Ícones e Rótulos
- [ ] Função de ícones **é clara**; usar **rótulo textual visível** quando necessário.
- [ ] Ícones clicáveis têm **nome acessível** (rótulo/`aria-label`) que descreve a ação.

!!! success "Certo"
    Ícone de lupa com label "Buscar no site".

!!! failure "Errado"
    Ícone sem rótulo; `alt="lupa"` sem indicar ação.

---

## 7) Mídias de Vídeo
- [ ] **Legendas sincronizadas** (CC) para todo vídeo.
- [ ] **Audiodescrição** para conteúdo visual essencial.
- [ ] **Libras** como recurso complementar quando pertinente.
- [ ] **[ATUALIZADO]** Evitar **flash** > 3x/seg; não publicar conteúdo que possa **provocar convulsão**.

!!! success "Certo"
    CC completas, AD disponível, janela de Libras quando necessário.

!!! failure "Errado"
    Vídeo sem legendas; elementos piscando rapidamente.

---

## 8) Autodescrição (quando houver pessoas em vídeo)
- [ ] **Roteirizar** e realizar **autodescrição** dos participantes.

> Ex.: "Olá, sou Ana; mulher branca, cabelos castanhos na altura dos ombros, uso óculos pretos…"

---

## 9) Podcasts (áudio)
- [ ] **Transcrição completa** com falas, identificação de locutores e sons relevantes.
- [ ] Considerar **videocast** para facilitar Libras/legendas.
- [ ] **[NOVO]** Se houver **autoplay de áudio > 3s**, deve haver **Pausar/Parar** ou controle de **volume**.

!!! success "Certo"
    Transcrição publicada junto do episódio; player com pausar/volume.

!!! failure "Errado"
    Áudio começa automático sem controle.

---

## 10) Hashtags e Emojis
- [ ] Hashtags em **CamelCase** (`#AcessibilidadeDigital`).
- [ ] Não **abusar de emojis** e nunca usá-los como **único** meio de informação.

!!! success "Certo"
    `#GuiaDeAcessibilidade` e emojis pontuais como apoio.

!!! failure "Errado"
    Texto composto só por emojis; hashtag em minúsculas.

---

## 11) Hiperlinks (texto do link e comportamento)
- [ ] Texto do link **compreensível isoladamente**.
- [ ] **Informar** quando link **abre em nova aba/janela**.
- [ ] Evitar **URLs cruas** no texto; prefira rótulos significativos.

!!! success "Certo"
    "Leia o **Relatório (PDF, 2,5 MB)** **(abre em nova aba)**".

!!! failure "Errado"
    "[clique aqui]"; colar a URL gigante como texto.

---

## 12) Documentos para Download (PDF, DOCX etc.)
- [ ] Estrutura com **tags de títulos** e **ordem de leitura** correta.
- [ ] **Alt** nas imagens do documento.
- [ ] Indicar **tipo e tamanho** do arquivo no link.

!!! success "Certo"
    "Relatório de Vendas **(PDF, 2,5 MB)**".

!!! failure "Errado"
    "[Baixar relatório]" sem contexto.

---

## 13) Ajuda Consistente **[NOVO]**
- [ ] Se houver links/contatos de ajuda (FAQ, chat, "fale conosco"), manter **no mesmo local** em páginas similares.

!!! success "Certo"
    Link "Ajuda" persistente no cabeçalho durante o fluxo.

!!! failure "Errado"
    Mudar o link de ajuda de lugar em cada página.

---

## O que **remover/ajustar** (comparado ao pocket antigo)
- **Links genéricos "clique aqui/saiba mais"** → **[ATUALIZADO]** : usar **rótulos descritivos**.
- **Apenas cor para comunicar** → manter a regra, mas **reforçar** uso de rótulos/ícones/padrões.
- **Conteúdo piscando** → **[ATUALIZADO]** : explicitar o limite **≤3 flashes/seg**.
- **Autoplay de áudio** → **[NOVO]** : exigir **Pausar/Parar/Volume** quando > 3s.

---

### Notas rápidas de autoria
- Prefira **voz ativa**, títulos descritivos e parágrafos curtos.
- Revise com leitores beta e, quando possível, com **pessoas com deficiência** (teste de usabilidade).

---

## Referências

- **NBR 17225:2025** — Diretrizes 2.4 (Navegável) e 1.3 (Adaptável); WCAG 2.2 — 2.4.*, 2.4.4.
- **WCAG 2.2 — 3.1.1 / 3.1.2** (Idioma de página e de partes).
- **WCAG 2.2 — 1.3.3** (Características sensoriais).
- **NBR 17225:2025 — Princípio 3 (Compreensível)** ; linguagem inclusiva.
- **Guia de Boas Práticas — Gov.br (2023)** — linguagem simples, links descritivos, hashtags.
- **WCAG 2.2 — 1.4.12** (Text Spacing).
- **WCAG 2.2 — 1.1.1** (Alternativas textuais) / práticas para alt.
- **WCAG 2.2 — 1.4.5** (Imagens de texto).
- **NBR 17225:2025 — Diretriz 3.2** (Previsível) — ícones e funções claras.
- **WCAG 2.2 — 4.1.2** (Name, Role, Value) — nomes acessíveis.
- **WCAG 2.2 — 1.2.\*** (Mídia baseada em tempo) — legendas e AD; **Libras** como apoio.
- **WCAG 2.2 — 2.3.1** (Três flashes ou abaixo do limiar).
- **Princípio 1 (Perceptível)** — autodescrição (boa prática consolidada).
- **WCAG 2.2 — 1.4.2** (Controle de áudio).
- **WCAG 2.2 — 3.2.2** (Na entrada — avisar nova aba/janela).
- **WCAG 2.2 — 3.2.6** (Ajuda consistente).