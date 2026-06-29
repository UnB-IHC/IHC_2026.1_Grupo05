# Checklist Aplicada Portal DETRAN-DF

**URL avaliada:** https://portal.detran.df.gov.br/#/home  
**Data da avaliação:** 15–16 de junho de 2026  
**Ferramenta de apoio:** WAVE (Web Accessibility Evaluation Tool)  
**Referenciais:** WCAG 2.2 · ABNT NBR 17225 · Guia de Boas Práticas Gov.br

**Legenda de status:**

- ✅ Conforme
- ❌ Não Conforme
- ➖ Não Aplicável / Não verificável
- ⚠️ Parcialmente Conforme

---

!!! info "Auditoria de Acessibilidade"
    Esta planilha apresenta a **Matriz de Conformidade** quantitativa cobrindo 99 critérios de acessibilidade (WCAG 2.2, NBR 17225 e Boas Práticas). Para uma análise aprofundada dos problemas críticos de interação, o impacto comportamental na persona e sugestões de correção no código, consulte o nosso [Relatório de Inspeção (Achados)](introducao.md).

---

## Nível de Conformidade A

### Conteúdo Não-Textual

| #   | Critério                                                                                                                        | Status | Observação / Evidência                                                                                                                                     |
| --- | ------------------------------------------------------------------------------------------------------------------------------- | ------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1   | Imagens, botões gráficos e outros elementos não textuais possuem texto alternativo (`alt`) descritivo que explica seu propósito | ❌     | WAVE detectou 1 _Missing alternative text_, 4 _Linked image missing alternative text_. Imagens de link sem `alt` impedem compreensão por leitores de tela. Veja o [detalhamento do Achado 5.1 no Relatório](introducao.md#51-nao-conformidade-elementos-de-interface-sem-texto-alternativo-ou-vazios). |
| 2   | CAPTCHAs possuem alternativas textuais e/ou de áudio                                                                            | ➖     | Não identificado CAPTCHA na página principal.                                                                                                              |
| 3   | Elementos puramente decorativos estão implementados de forma que tecnologias assistivas possam ignorá-los                       | ⚠️     | WAVE detectou 1 _Null or empty alternative text_ (positivo para decorativas), porém demais imagens sem `alt` sugerem inconsistência no tratamento.         |

### Mídia Baseada em Tempo

| #   | Critério                                                                                                         | Status | Observação / Evidência                                      |
| --- | ---------------------------------------------------------------------------------------------------------------- | ------ | ----------------------------------------------------------- |
| 4   | Existem transcrições para conteúdos compostos apenas por áudio pré-gravado                                       | ➖     | Não identificado conteúdo de áudio puro na página avaliada. |
| 5   | Existem audiodescrições ou transcrições detalhadas para vídeos pré-gravados sem áudio                            | ➖     | Não identificado vídeo sem áudio na página principal.       |
| 6   | Existem legendas sincronizadas para todos os vídeos pré-gravados com áudio                                       | ➖     | Não identificado vídeo com áudio na página principal.       |
| 7   | Existe alternativa em texto ou audiodescrição cobrindo as informações visuais importantes de vídeos pré-gravados | ➖     | Idem.                                                       |

### Adaptável

| #   | Critério                                                                                                      | Status | Observação / Evidência                                                                                                                                                               |
| --- | ------------------------------------------------------------------------------------------------------------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 8   | A estrutura lógica da página (cabeçalhos, listas, tabelas) está corretamente marcada no HTML                  | ❌     | WAVE apontou 2 _Skipped heading level_. O portal salta de `<h1>` diretamente para `<h4>` no rodapé (Veículos, Habilitação, Agendamento, Infração), quebrando a hierarquia semântica. Veja o [detalhamento do Achado 5.4 no Relatório](introducao.md#54-nao-conformidade-quebra-na-hierarquia-semantica-de-titulos). |
| 9   | A ordem de navegação e leitura do conteúdo faz sentido lógico, acompanhando a estrutura visual                | ⚠️     | A existência de 23 manipuladores dependentes de evento de mouse compromete a ordem de navegação por teclado.                                                                         |
| 10  | Nenhuma instrução depende apenas de características sensoriais como forma, cor, tamanho ou localização visual | ⚠️     | Não foram encontradas instruções textuais explícitas dependentes de cor, mas a quantidade de erros de contraste indica que informações visuais podem não ser perceptíveis por todos. |

### Uso de Cores e Áudio

| #   | Critério                                                                                                                    | Status | Observação / Evidência                                                                                                                   |
| --- | --------------------------------------------------------------------------------------------------------------------------- | ------ | ---------------------------------------------------------------------------------------------------------------------------------------- |
| 11  | A cor nunca é o único meio para transmitir informação, indicar uma ação ou sinalizar um erro                                | ⚠️     | Não verificado diretamente nos estados de erro, mas os 39 erros de contraste indicam uso problemático de cor como veículo de informação. |
| 12  | Qualquer áudio que toque automaticamente por mais de 3 segundos tem controle visível para pausar, parar ou ajustar o volume | ➖     | Nenhum áudio automático identificado na página principal.                                                                                |

### Acessível por Teclado

| #   | Critério                                                                                        | Status | Observação / Evidência                                                                                                                                 |
| --- | ----------------------------------------------------------------------------------------------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 13  | Todas as funcionalidades do site podem ser utilizadas apenas com o teclado                      | ❌     | 23 _Device dependent event handler_ detectados. Elementos críticos de navegação e botões dependem de mouse, excluindo usuários com limitações motoras. Veja o [detalhamento do Achado 5.5 no Relatório](introducao.md#55-nao-conformidade-dependencia-de-manipuladores-de-eventos-vinculados-ao-mouse). |
| 14  | O uso do mouse é opcional e não obrigatório para concluir tarefas                               | ❌     | Idem ao item acima.                                                                                                                                    |
| 15  | É possível entrar e sair de qualquer componente usando apenas o teclado, sem armadilhas de foco | ❌     | A dependência de `onmouseover`/`onclick` sem equivalentes de teclado impede a navegação plena via Tab/Enter. Veja o [detalhamento do Achado 5.6 no Relatório](introducao.md#56-nao-conformidade-falha-de-gerenciamento-de-foco-em-menus-suspensos). |
| 16  | Componentes especiais (modais, menus, widgets) informam claramente como sair deles              | ❌     | O chatbot ("Criado por Stefanini") e os pop-ups promocionais não apresentam indicação acessível de como dispensá-los via teclado.                      |
| 17  | Atalhos compostos apenas por letras, números ou símbolos podem ser desativados ou remapeados    | ➖     | Não foram identificados atalhos de teclado de letra única implementados explicitamente.                                                                |
| 18  | Os atalhos funcionam apenas quando o componente correspondente está em foco                     | ➖     | Idem.                                                                                                                                                  |

### Tempo Suficiente

| #   | Critério                                                                                    | Status | Observação / Evidência                                                                                                                                                                  |
| --- | ------------------------------------------------------------------------------------------- | ------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 19  | O usuário pode desativar, ajustar ou estender limites de tempo sem perder progresso         | ❌     | Após o login, o portal impõe um limite de tempo de sessão fixo, sem fornecer mecanismos para o usuário estender, ajustar ou desativar a contagem antes de ser deslogado automaticamente |
| 20  | O sistema avisa antes que o tempo expire                                                    | ❌     | : O sistema encerra a sessão por inatividade de forma abrupta, sem exibir um aviso prévio acessível que permita ao usuário solicitar mais tempo.                                        |
| 21  | Conteúdos em movimento (carrosséis, banners) podem ser pausados, interrompidos ou ocultados | ❌     | O banner lateral ("Mulher Não se Cale!") e o chatbot animado não apresentam controles de pausa visíveis ou acessíveis.                                                                  |
| 22  | Informações atualizadas automaticamente podem ser pausadas ou controladas pelo usuário      | ❌     | WAVE identificou 1 _ARIA alert or live region_, sem evidência de controle do usuário sobre as atualizações.                                                                             |

### Convulsões e Reações Físicas

| #   | Critério                                                                   | Status | Observação / Evidência                                                               |
| --- | -------------------------------------------------------------------------- | ------ | ------------------------------------------------------------------------------------ |
| 23  | Não existem elements que pisquem mais de 3 vezes por segundo               | ✅     | Nenhum elemento intermitente em frequência perigosa identificado durante a inspeção. |
| 24  | Conteúdos visuais seguem os limites recomendados para flashes e contrastes | ✅     | Idem.                                                                                |

### Navegável

| #   | Critério                                                                                  | Status | Observação / Evidência                                                                                                                               |
| --- | ----------------------------------------------------------------------------------------- | ------ | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| 25  | Existe mecanismo para saltar blocos de conteúdo repetidos em várias páginas (_skip link_) | ❌     | Nenhum _skip link_ identificado no portal. Usuários de teclado/leitor de tela são forçados a percorrer todo o menu em cada página.                   |
| 26  | As páginas possuem títulos que descrevem seu tópico ou propósito                          | ⚠️     | A página principal possui `<h1>` identificado pelo WAVE, porém a hierarquia é quebrada, comprometendo a navegabilidade por cabeçalhos.               |
| 27  | Os componentes recebem foco em ordem que preserva o significado e a operabilidade         | ❌     | Os 23 manipuladores dependentes de mouse e o uso de `tabindex` artificial (WAVE detectou 4 _ARIA tabindex_) podem criar ordens de foco incoerentes.  |
| 28  | O propósito de cada link pode ser determinado pelo texto do link ou pelo seu contexto     | ❌     | 3 _Empty link_ e 4 _Linked image missing alternative text_ detectados. Links sem texto ou imagem sem `alt` são ininteligíveis para leitores de tela. |

### Modalidades de Entrada

| #   | Critério                                                                                                     | Status | Observação / Evidência                                                                              |
| --- | ------------------------------------------------------------------------------------------------------------ | ------ | --------------------------------------------------------------------------------------------------- |
| 29  | Funcionalidades com gestos multiponto podem ser operadas com ponteiro simples                                | ⚠️     | Não verificado em dispositivo móvel, mas a dependência de mouse sugere dificuldade também em touch. |
| 30  | Para funções de ponteiro único, a execução ocorre no evento de subida ou há mecanismo para abortar/desfazer  | ❌     | Os manipuladores `onmouseover`/`onclick` sem redundância não garantem essa condição.                |
| 31  | O nome acessível de componentes contém o texto apresentado visualmente                                       | ❌     | Botões e links vazios (4 _Empty button_, 3 _Empty link_) não possuem nome acessível algum.          |
| 32  | Funcionalidades operadas por movimento do dispositivo também podem ser operadas por componentes da interface | ➖     | Não foram identificadas funcionalidades ativadas por movimento de dispositivo.                      |

### Legível

| #   | Critério                                                            | Status | Observação / Evidência                                                                        |
| --- | ------------------------------------------------------------------- | ------ | --------------------------------------------------------------------------------------------- |
| 33  | O idioma principal da página pode ser determinado programaticamente | ✅     | WAVE identificou 1 _Language_ feature, indicando que o atributo `lang` está presente no HTML. |

### Previsível

| #   | Critério                                                                                  | Status | Observação / Evidência                                                                                                                     |
| --- | ----------------------------------------------------------------------------------------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------ |
| 34  | Quando um componente recebe foco, isso não inicia automaticamente uma mudança de contexto | ⚠️     | Não verificado diretamente, mas a presença de 1 _ARIA alert or live region_ e 6 _ARIA popup_ pode causar mudanças de contexto inesperadas. |
| 35  | Alterar a configuração de um componente não causa mudança de contexto sem aviso prévio    | ➖     | Não verificado em formulários desta página.                                                                                                |
| 36  | Mecanismos de ajuda repetidos em várias páginas ocorrem sempre na mesma ordem relativa    | ⚠️     | O chatbot e o menu de navegação parecem consistentes, mas o comportamento dependente de mouse impede verificação plena por teclado.        |

### Assistência de Entrada

| #   | Critério                                                                                               | Status | Observação / Evidência                                                                        |
| --- | ------------------------------------------------------------------------------------------------------ | ------ | --------------------------------------------------------------------------------------------- |
| 37  | Se um erro é detectado, o item com erro é claramente identificado e descrito em texto                  | ➖     | Não verificado — dependeria de interação com formulários.                                     |
| 38  | Rótulos (_labels_) ou instruções são fornecidos sempre que há entrada de dados pelo usuário            | ❌     | WAVE apontou 2 _Missing form label_. Campos de busca e entrada de dados sem rótulo associado. Veja o [detalhamento do Achado 5.3 no Relatório](introducao.md#53-nao-conformidade-ausencia-de-rotulos-permanentes-em-formularios). |
| 39  | Os formulários possuem mensagens de erro claras, descritivas e posicionadas próximas ao campo com erro | ➖     | Não verificado — dependeria de submissão de formulários.                                      |

### Compatível

| #   | Critério                                                                                    | Status | Observação / Evidência                                                                                                     |
| --- | ------------------------------------------------------------------------------------------- | ------ | -------------------------------------------------------------------------------------------------------------------------- |
| 40  | O código utiliza semântica HTML nativa (tags corretas para botões, links etc.)              | ❌     | Botões e links vazios, manipuladores de evento inadequados e 3 _Layout table_ sugerem uso não semântico de elementos HTML. |
| 41  | Todos os componentes de interface têm nome e função determinados programaticamente          | ❌     | 4 _Empty button_ e 3 _Empty link_ não possuem nome programático.                                                           |
| 42  | Estados, propriedades e valores definíveis pelo usuário são determináveis programaticamente | ⚠️     | 6 _ARIA_ e 2 _ARIA label_ detectados pelo WAVE indicam uso parcial de ARIA, mas insuficiente.                              |
| 43  | Mudanças nesses itens são notificadas para tecnologias assistivas                           | ⚠️     | 1 _ARIA alert or live region_ presente, mas cobertura parcial.                                                             |

---

## Nível de Conformidade AA

### Mídia Baseada em Tempo

| #   | Critério                                                                                       | Status | Observação / Evidência                                  |
| --- | ---------------------------------------------------------------------------------------------- | ------ | ------------------------------------------------------- |
| 44  | Legendas ao vivo são fornecidas para transmissões e conteúdos de áudio em tempo real           | ➖     | Não identificado conteúdo ao vivo.                      |
| 45  | Audiodescrição é fornecida para todo o conteúdo de vídeo pré-gravado                           | ➖     | Não identificado vídeo pré-gravado na página principal. |
| 46  | Foram fornecidas legendas, audiodescrição e/ou janela de Libras para arquivos de vídeo e áudio | ➖     | Idem.                                                   |

### Adaptável

| #   | Critério                                                                                               | Status | Observação / Evidência                                                                                    |
| --- | ------------------------------------------------------------------------------------------------------ | ------ | --------------------------------------------------------------------------------------------------------- |
| 47  | A página não restringe o uso em apenas uma orientação de tela (retrato ou paisagem)                    | ⚠️     | Não verificado em dispositivo móvel.                                                                      |
| 48  | O propósito de campos de formulário que coletam dados pessoais pode ser identificado programaticamente | ❌     | Campos sem `<label>` associado não permitem preenchimento automático adequado por tecnologias assistivas. |

### Contraste e Texto

| #   | Critério                                                                                             | Status | Observação / Evidência                                                                                                                                                                                                                                                                                                                            |
| --- | ---------------------------------------------------------------------------------------------------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 49  | Textos e imagens de texto possuem contraste mínimo de 4,5:1 com o fundo (ou 3:1 para textos grandes) | ❌     | 39 _Very low contrast_ detectados pelo WAVE em menus superiores (Início, Veículos, CNH, Atendimento, Infração) e textos secundários. Veja o [detalhamento do Achado 5.2 no Relatório](introducao.md#52-nao-conformidade-contraste-de-texto-insuficiente). |
| 50  | O texto pode ser ampliado em até 200% sem perda de conteúdo ou quebra de funcionalidades             | ⚠️     | Ao aplicar o zoom de 200%, o layout sofre um refluxo agressivo, gerando cards superdimensionados (como o do "Balcão Virtual") e grandes áreas vazias. Embora o conteúdo não seja textualmente perdido ou cortado, a usabilidade e a estética do design são severamente comprometidas, exigindo rolagem excessiva para interagir com os elementos. |
| 51  | Textos reais (em código) são usados no lugar de imagens com texto, exceto logotipos                  | ⚠️     | Não identificadas imagens de texto de forma sistemática, mas há imagens de links sem `alt` que podem ocultar texto informativo.                                                                                                                                                                                                                   |

### Refluxo e Espaçamento

| #   | Critério                                                                                                                                                                          | Status | Observação / Evidência                                                                                                                                                                                                                                                                                                                                             |
| --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 52  | O conteúdo se ajusta automaticamente (_reflow_) com zoom de 400% sem barra de rolagem horizontal                                                                                  | ❌     | Ao aplicar o zoom de 400%, o portal falha em realizar o refluxo responsivo, introduzindo uma barra de rolagem horizontal. A abertura do chatbot também gera sobreposição. Veja o [detalhamento do Achado 5.7 no Relatório](introducao.md#57-nao-conformidade-obstrucao-de-conteudo-por-elementos-flutuantes-em-zoom-de-400). |
| 53  | Elementos gráficos essenciais e componentes de interface possuem contraste mínimo de 3:1 em relação às cores adjacentes                                                           | ❌     | Os 39 erros de contraste incluem elementos de interface, não apenas texto corrido.                                                                                                                                                                                                                                                                                 |
| 54  | O layout não quebra se o usuário alterar espaçamento entre linhas, letras ou parágrafos                                                                                           | ⚠️     | Não testado diretamente.                                                                                                                                                                                                                                                                                                                                           |
| 55  | Conteúdos que aparecem ao passar o mouse ou focar (_tooltips_) podem ser fechados com Esc, não desaparecem ao mover o mouse para dentro deles e permanecem visíveis até interação | ❌     | Os 23 manipuladores dependentes de mouse sugerem que menus suspensos dependem exclusivamente de hover, sem alternativa por teclado ou comportamento acessível de tooltip.                                                                                                                                                                                          |

### Navegável

| #   | Critério                                                                                                     | Status | Observação / Evidência                                                                                                                                                     |
| --- | ------------------------------------------------------------------------------------------------------------ | ------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 56  | Existe mais de uma forma de localizar uma página (ex: busca, mapa do site, menus)                            | ⚠️     | Há menus de navegação e um campo de busca, mas os 2 _Missing form label_ comprometem a usabilidade da busca.                                                               |
| 57  | Cabeçalhos e rótulos descrevem o tópico ou propósito do conteúdo                                             | ❌     | A hierarquia quebrada de cabeçalhos (h1 → h4) compromete a descrição semântica das seções.                                                                                 |
| 58  | O indicador de foco do teclado é visível ao navegar pela página                                              | ❌     | Os 23 manipuladores dependentes de mouse e a dependência de hover sugerem que o indicador de foco pode não estar visível ou funcional em todos os componentes interativos. |
| 59  | Quando um componente recebe foco, ele não fica totalmente escondido por conteúdo do autor (banners, pop-ups) | ❌     | O pop-up "Mulher Não se Cale!" e o chatbot flutuante podem encobrir o foco de outros elementos.                                                                            |

### Modalidades de Entrada

| #   | Critério                                                                                                    | Status | Observação / Evidência                                                                                                                                                                                                                                                                                                                        |
| --- | ----------------------------------------------------------------------------------------------------------- | ------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 60  | Funcionalidades que utilizam arrastar podem ser realizadas com ponteiro simples sem necessidade de arrastar | ➖     | Não identificadas funcionalidades de arrastar.                                                                                                                                                                                                                                                                                                |
| 61  | As áreas de clique (botões, ícones) possuem tamanho mínimo de 24x24 pixels ou espaçamento suficiente        | ✅     | Inspeção manual confirmou que todos os elementos interativos e ícones de serviço atendem à dimensão mínima de 24x24px. Os apontamentos do WAVE sobre botões vazios no rodapé (redes sociais) configuram falsos-positivos de validação automatizada, visto que os elementos possuem área ativa adequada e executam o redirecionamento correto. |

### Legível

| #   | Critério                                                                                                           | Status | Observação / Evidência                                                          |
| --- | ------------------------------------------------------------------------------------------------------------------ | ------ | ------------------------------------------------------------------------------- |
| 62  | O idioma de cada passagem ou frase pode ser determinado programaticamente, exceto nomes próprios e termos técnicos | ✅     | Atributo `lang` identificado pelo WAVE. Conteúdo majoritariamente em português. |

### Previsível

| #   | Critério                                                                                      | Status | Observação / Evidência                                                                            |
| --- | --------------------------------------------------------------------------------------------- | ------ | ------------------------------------------------------------------------------------------------- |
| 63  | Mecanismos de navegação repetidos em múltiplas páginas ocorrem sempre na mesma ordem relativa | ⚠️     | Menu principal parece consistente visualmente, mas não foi verificado em outras páginas internas. |
| 64  | Componentes com a mesma funcionalidade são identificados de forma consistente em todo o site  | ⚠️     | Idem.                                                                                             |

### Assistência de Entrada

| #   | Critério                                                                                                                              | Status | Observação / Evidência                                                                                                                                                                                                                                                                                             |
| --- | ------------------------------------------------------------------------------------------------------------------------------------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 65  | Se um erro é detectado e existem sugestões de correção conhecidas, elas são fornecidas ao usuário                                     | ❌     | Na tela de alteração de endereço, ao falhar a validação de regras de negócio (ex: usuário com PPD), o sistema expõe uma mensagem genérica de erro de API (Http failure response... 500 OK) em vez de fornecer uma instrução clara e inteligível em texto sobre o motivo do erro e como corrigi-lo.                 |
| 66  | Em páginas com transações legais, financeiras ou exclusão de dados, a submissão é reversível, verificável ou tem etapa de confirmação | ❌     | O fluxo de "Exclusão de Conta" permite o envio imediato da solicitação destrutiva por meio de um único formulário simples contendo apenas uma caixa de texto e o botão de ação, carecendo de uma etapa explícita e destacada de revisão de dados ou confirmação em dois fatores.                                   |
| 67  | Autenticação não exige testes cognitivos sem alternativa, assistência ou reconhecimento de objetos                                    | ✅     | A tela de login utiliza o mecanismo reCAPTCHA ("Não sou um robô"), que opera de forma simplificada por clique e possui nativamente alternativa em áudio para os desafios visuais. Além disso, o portal oferece o botão "Entrar com gov.br", fornecendo um método alternativo de autenticação totalmente acessível. |

### Compatível

| #   | Critério                                                                                                           | Status | Observação / Evidência                                          |
| --- | ------------------------------------------------------------------------------------------------------------------ | ------ | --------------------------------------------------------------- |
| 68  | Mensagens de status são determinadas programaticamente e transmitidas para tecnologias assistivas sem receber foco | ⚠️     | 1 _ARIA alert or live region_ presente, mas cobertura limitada. |

---

## Nível de Conformidade AAA

### Mídia Baseada em Tempo

| #   | Critério                                                                                  | Status | Observação / Evidência                 |
| --- | ----------------------------------------------------------------------------------------- | ------ | -------------------------------------- |
| 69  | Intérprete de língua de sinais é fornecido para áudios pré-gravados                       | ➖     | Não identificado conteúdo de áudio.    |
| 70  | Alternativa em texto é fornecida para todo conteúdo de vídeo ou áudio, gravado ou ao vivo | ➖     | Não identificado conteúdo audiovisual. |

### Adaptável

| #   | Critério                                                                                                     | Status | Observação / Evidência                                                                                                            |
| --- | ------------------------------------------------------------------------------------------------------------ | ------ | --------------------------------------------------------------------------------------------------------------------------------- |
| 71  | O propósito dos componentes da interface, ícones e regiões da página pode ser identificado programaticamente | ❌     | Imagens sem `alt`, botões vazios e hierarquia de cabeçalhos quebrada impedem identificação programática do propósito das regiões. |

### Distinguível

| #   | Critério                                                                 | Status | Observação / Evidência                                                                                                                       |
| --- | ------------------------------------------------------------------------ | ------ | -------------------------------------------------------------------------------------------------------------------------------------------- |
| 72  | O texto possui contraste aprimorado de pelo menos 7:1 com o fundo        | ❌     | Com 39 pontos de _Very low contrast_, o portal não atinge sequer o 4,5:1 do nível AA. O contraste 7:1 do nível AAA está ainda mais distante. |
| 73  | A página não possui áudio de fundo, ou permite desativá-lo completamente | ✅     | Nenhum áudio de fundo identificado.                                                                                                          |

### Acessível por Teclado

| #   | Critério                                                                | Status | Observação / Evidência                                           |
| --- | ----------------------------------------------------------------------- | ------ | ---------------------------------------------------------------- |
| 74  | Todas as funcionalidades podem ser utilizadas pelo teclado sem exceções | ❌     | 23 _Device dependent event handler_. Falha crítica e recorrente. |

### Tempo Suficiente

| #   | Critério                                                          | Status | Observação / Evidência                                                                                 |
| --- | ----------------------------------------------------------------- | ------ | ------------------------------------------------------------------------------------------------------ |
| 75  | A atividade não depende de limites de tempo para ser concluída    | ➖     | Não verificado.                                                                                        |
| 76  | Interrupções não essenciais podem ser adiadas ou desativadas      | ❌     | O pop-up "Mulher Não se Cale!" e o chatbot são interrupções que não podem ser controladas via teclado. |
| 77  | O usuário pode continuar após nova autenticação sem perder dados  | ➖     | Não verificado.                                                                                        |
| 78  | O sistema informa quando a inatividade pode causar perda de dados | ➖     | Não verificado.                                                                                        |

### Convulsões e Reações Físicas

| #   | Critério                                                                               | Status | Observação / Evidência                                                                      |
| --- | -------------------------------------------------------------------------------------- | ------ | ------------------------------------------------------------------------------------------- |
| 79  | Não existem elementos que pisquem mais de 3 vezes por segundo em nenhuma circunstância | ✅     | Não identificado.                                                                           |
| 80  | Animações acionadas por interação podem ser desativadas pelo usuário                   | ❌     | O chatbot animado e os elementos de hover não oferecem controle de desativação de animação. |
| 81  | O site evita efeitos de tela inteira, parallax e animações excessivas                  | ⚠️     | O chatbot animado e o pop-up flutuante geram distração, mas não parallax severo.            |

### Navegável

| #   | Critério                                                                                                        | Status | Observação / Evidência                                                                                                |
| --- | --------------------------------------------------------------------------------------------------------------- | ------ | --------------------------------------------------------------------------------------------------------------------- |
| 82  | Informações sobre a localização do usuário dentro de um conjunto de páginas estão disponíveis                   | ❌     | Não foi identificado mecanismo de _breadcrumb_ ou indicador de localização na página principal.                       |
| 83  | O propósito de cada link pode ser identificado apenas pelo seu texto, sem contexto adicional                    | ❌     | 3 _Empty link_ e 4 _Linked image missing alternative text_ tornam vários links completamente opacos fora de contexto. |
| 84  | Cabeçalhos de seção são utilizados para organizar o conteúdo                                                    | ❌     | Hierarquia de cabeçalhos quebrada (h1 → h4) compromete a organização semântica do conteúdo.                           |
| 85  | Nenhuma parte do componente em foco é escondida por conteúdo do autor                                           | ❌     | Pop-ups e chatbot flutuante podem encobrir componentes em foco.                                                       |
| 86  | O indicador de foco possui área de contraste e tamanho suficientes (mínimo 2px de perímetro e contraste de 3:1) | ❌     | Os problemas de contraste e dependência de mouse sugerem indicador de foco inadequado.                                |

### Modalidades de Entrada

| #   | Critério                                                                           | Status | Observação / Evidência                                                                                                                                                                                                                                                                                                                               |
| --- | ---------------------------------------------------------------------------------- | ------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 87  | O tamanho do alvo para entradas de ponteiro é de pelo menos 44x44 pixels           | ⚠️     | Enquanto os blocos principais de serviços (cards) oferecem áreas de clique amplas e bem dimensionadas, diversos elementos interativos secundários — como os botões de fechar (X) de alertas/pop-ups e ícones de redes sociais — possuem áreas ativas inferiores a 44x44px, dificultando o acionamento por usuários com limitações motoras refinadas. |
| 88  | O conteúdo não restringe o uso de modalidades de entrada disponíveis na plataforma | ❌     | A dependência de mouse restringe modalidades de entrada a ponteiro, excluindo teclado e acionadores alternativos.                                                                                                                                                                                                                                    |

### Legível

| #   | Critério                                                                                  | Status | Observação / Evidência                                                                           |
| --- | ----------------------------------------------------------------------------------------- | ------ | ------------------------------------------------------------------------------------------------ |
| 89  | Há mecanismo para identificar definições de palavras usadas de forma incomum ou em jargão | ➖     | Não verificado. Termos técnicos de trânsito (CRLV-e, ATPV-e) não possuem expansão visível.       |
| 90  | Há mecanismo para identificar a forma expandida ou o significado de abreviações           | ❌     | Abreviações como "CNH", "CRLV-e", "ATPV-e" não possuem expansão programática (ex: tag `<abbr>`). |
| 91  | Quando o texto exige leitura avançada, uma versão simplificada ou suplementar é fornecida | ➖     | Não verificado.                                                                                  |
| 92  | Há mecanismo para identificar a pronúncia de palavras com significado ambíguo             | ➖     | Não aplicável ao contexto do portal.                                                             |

### Previsível

| #   | Critério                                                                                                | Status | Observação / Evidência                                                                                                                |
| --- | ------------------------------------------------------------------------------------------------------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------- |
| 93  | Mudanças de contexto são iniciadas apenas por solicitação do usuário, ou há mecanismo para desativá-las | ❌     | O pop-up "Mulher Não se Cale!" surge automaticamente sem solicitação do usuário e sem mecanismo de desativação acessível por teclado. |

### Assistência de Entrada

| #   | Critério                                                                                                             | Status | Observação / Evidência                                                                                 |
| --- | -------------------------------------------------------------------------------------------------------------------- | ------ | ------------------------------------------------------------------------------------------------------ |
| 94  | Ajuda sensível ao contexto está disponível para o usuário                                                            | ⚠️     | O chatbot oferece algum nível de ajuda, mas sua inacessibilidade por teclado compromete sua utilidade. |
| 95  | Para todas as páginas que exigem envio de informações, a submissão é reversível, verificável ou tem etapa de revisão | ➖     | Não verificado na página principal.                                                                    |

---

## Boas Práticas de Gestão e Processo

| #   | Critério                                                                                          | Status | Observação                                                                                                                                                                |
| --- | ------------------------------------------------------------------------------------------------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 96  | A acessibilidade foi incluída no escopo inicial e no orçamento do projeto                         | ❌     | O volume e a variedade dos erros encontrados (14 erros, 39 erros de contraste, 30 alertas) indicam que a acessibilidade não foi considerada desde a concepção do projeto. |
| 97  | O projeto segue o princípio do Desenho Universal (usável por todos sem adaptação prévia)          | ❌     | A exclusão de usuários com limitações motoras e visuais demonstra que o Desenho Universal não foi adotado.                                                                |
| 98  | Pessoas com deficiência estão envolvidas na equipe ou no grupo de testes                          | ➖     | Não verificável externamente, mas a quantidade de barreiras encontradas sugere ausência de testes com usuários reais com deficiência.                                     |
| 99  | As personas criadas são heterogêneas e incluem pessoas com deficiência e baixo letramento digital | ➖     | Idem.                                                                                                                                                                     |

---

## Resumo Quantitativo

| Nível      | ✅ Conforme | ❌ Não Conforme | ⚠️ Parcial | ➖ N/A |
| ---------- | ----------- | --------------- | ---------- | ------ |
| **A**      | 3           | 16              | 8          | 10     |
| **AA**     | 3           | 11              | 5          | 6      |
| **AAA**    | 2           | 12              | 4          | 9      |
| **Gestão** | 0           | 2               | 0          | 2      |
| **Total**  | **8**       | **41**          | **17**     | **27** |

> **Conclusão:** O Portal DETRAN-DF apresenta **41 não conformidades** identificadas, concentradas principalmente nos critérios de Nível A (mais críticos). As falhas em acessibilidade por teclado, contraste e texto alternativo representam barreiras de exclusão total para usuários com deficiência visual e motora.
