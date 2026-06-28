## Público-alvo

Este material foi criado para atender diferentes profissionais que atuam em equipes de produtos digitais:

- **Pessoas Desenvolvedoras**  
  Para verificar rapidamente se **componentes, páginas e fluxos** estão em conformidade com os requisitos mínimos de acessibilidade antes de colocá-los em produção.

- **Pessoas de UX/UI e Design**  
  Durante a **criação de protótipos**, para assegurar contraste adequado, indicadores de foco visíveis, hierarquia clara de informações e interações acessíveis (toque, teclado, animações, etc.).

- **Pessoas de Conteúdo**  
  Ao produzir **textos, imagens, vídeos e documentos**, contando com orientações para escrever de forma clara e simples, elaborar descrições para imagens e organizar links e anexos de maneira acessível.

- **Pessoas de Gestão e Coordenação**  
  Ao definir **prioridades, metas e critérios de pronto (DoD)**, garantindo que a acessibilidade seja tratada como exigência de qualidade e não como um item secundário.

- **Profissionais de Qualidade e Testes (QA)**  
  Para planejar cenários de teste que considerem tanto aspectos funcionais quanto não funcionais, utilizando os checklists e ferramentas sugeridos para validar a acessibilidade.

---

## Glossário resumido

Principais termos utilizados ao longo do guia:

- **A11y**  
  Forma abreviada de *accessibility*, onde as 11 letras entre "a" e "y" são substituídas pelo número. É um jeito comum de se referir à acessibilidade digital.

- **WCAG**  
  *Web Content Accessibility Guidelines* — diretrizes internacionais do W3C para tornar o conteúdo da web mais acessível. Este guia está alinhado com a **versão 2.2, nível AA**.

- **SC (Critério de Sucesso)**  
  Cada requisito específico da WCAG, como contraste mínimo (1.4.3), navegação por teclado (2.1.1) e assistência na autenticação (3.3.7).

- **ARIA / WAI-ARIA**  
  Conjunto de atributos que melhoram a acessibilidade de componentes interativos complexos (como menus, janelas modais e carrosséis), especialmente para leitores de tela. Devem ser usados como **complemento** ao HTML semântico, nunca como substituto.

- **APG (Guia de Práticas de Autoria)**  
  Documento do W3C que descreve **padrões de comportamento recomendados** para a construção de componentes acessíveis, como menus, diálogos e acordeões.

- **DoD (*Definition of Done*)**  
  Conjunto de condições que uma tarefa deve atender para ser considerada concluída. Incluir acessibilidade no DoD faz com que ela se torne parte integrante da qualidade do produto.

- **NBR 17225 / NBR 17060**  
  Normas da ABNT que tratam da acessibilidade em **serviços web** (17225) e **aplicativos móveis** (17060). Este guia baseia-se tanto nessas normas quanto na WCAG 2.2.

---

## Alcance e restrições deste guia

Embora tenha sido elaborado para ser objetivo e alinhado com as principais referências, este material **não abrange todos os aspectos** da acessibilidade. Destacam-se as seguintes limitações:

- **Foco em produtos digitais**  
  O conteúdo é voltado para **interfaces e serviços web e mobile**. Questões relacionadas à acessibilidade **física, arquitetônica, sinalização viária, transportes e mobiliário** não são tratadas aqui.

- **Não substitui testes com usuários reais**  
  As listas de verificação e ferramentas apresentadas ajudam a identificar grande parte dos problemas, mas **não dispensam a realização de testes com pessoas com deficiência** e outros perfis variados de usuários.

- **Não tem valor de laudo ou certificação**  
  Este guia serve como apoio para a equipe melhorar a acessibilidade do produto, mas **não substitui uma auditoria formal** nem atesta conformidade plena. Para processos oficiais, pode ser necessária a contratação de **especialistas externos**.

- **Conteúdo sujeito a atualizações**  
  As normas e diretrizes (WCAG, NBR, etc.) passam por revisões periódicas. Este material reflete o estado atual do conhecimento e pode exigir ajustes futuros para acompanhar novas versões.

> Mesmo com essas limitações, a aplicação consistente deste guia já representa um avanço expressivo na construção de produtos digitais mais inclusivos e com maior qualidade.