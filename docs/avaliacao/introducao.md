# Introdução e Metodologia da Avaliação: Portal DETRAN-DF

> **Objeto de Estudo:** Portal principal do Departamento de Trânsito do Distrito Federal (DETRAN-DF)  
> **URL:** [https://portal.detran.df.gov.br/#/home](https://portal.detran.df.gov.br/#/home)

---

## 1. Introdução

Este documento apresenta a avaliação técnica de Interface Humano-Computador (IHC) e Acessibilidade Digital realizada no portal principal do Departamento de Trânsito do Distrito Federal (DETRAN-DF).

O objetivo desta auditoria é analisar a conformidade do canal oficial do órgão com os principais referenciais normativos, garantindo o direito constitucional de acesso à informação e a autonomia do cidadão. A avaliação foi balizada por um checklist consolidado a partir do *Guia de Boas Práticas para Acessibilidade Digital* do Governo Federal brasileiro, pelas diretrizes internacionais *Web Content Accessibility Guidelines (WCAG 2.2)* da W3C e pela norma técnica nacional *ABNT NBR 17225*.

Ademais, expandindo o escopo de acessibilidade estrita para englobar a usabilidade tradicional, os problemas identificados foram mapeados segundo as *10 Heurísticas de Nielsen*, proporcionando uma visão holística sobre as barreiras de interação encontradas no portal.

---

## 2. Perfil dos Avaliadores

A equipe de avaliação é composta pelos seguintes membros do grupo:

*   Jorge Henrique Lessa — 231011570
*   Gabriela Dourado — 231026821
*   Luiz Henrique Guimarães — 222022144
*   Matheus Ribeiro — 231011749
*   Pedro Henrique Gomes — 232030041
*   Kelyton de Lucas Moraes — 241012033
*   Natan França — 241011537

---

## 3. Metodologia de Inspeção

A inspeção foi realizada de forma remota no ambiente de produção do portal. Adotou-se uma abordagem mista de auditoria:

1.  **Inspeção Automática:** Emprego da ferramenta de auditoria *WAVE (Web Accessibility Evaluation Tool)* para mapeamento de erros de código, semântica e contrastes.
2.  **Inspeção Manual (Heurística):** Simulação de navegação exclusiva via teclado para validação de foco, varredura de quebra de layout por ampliação de tela (zoom de até 400%) e análise de consistência de fluxo.

---

## 4. Conclusão

A avaliação de Interface Humano-Computador (IHC) e acessibilidade digital realizada no Portal do DETRAN-DF aponta para um cenário de **maturidade insatisfatória** no que diz respeito à inclusão digital e à facilidade de uso geral. Embora o portal consolide os principais serviços procurados pelo cidadão em formato digital, as falhas técnicas encontradas agem como severas barreiras de exclusão.

Os erros estruturais, de contraste e de responsividade apontados pela auditoria técnica demonstram que princípios básicos do Desenho Universal não foram devidamente priorizados durante a arquitetura do software. A dependência excessiva de scripts baseados em interações com o mouse, os saltos inadequados na hierarquia de cabeçalhos e a obstrução física de áreas de texto durante a ampliação de tela (refluxo) penalizam diretamente o público que mais depende do auxílio do Estado: pessoas com deficiência visual (cegas ou de baixa visão), idosos e indivíduos com limitações motoras.

Do ponto de vista de usabilidade pura, as heurísticas de *Estética e Design Minimalista*, *Consistência* e *Prevenção de Erros* são frequentemente violadas por textos apagados e formulários sem descrições perenes. Conclui-se, portanto, que para se adequar plenamente à legislação nacional e às exigências técnicas vigentes, o Portal do DETRAN-DF necessita de uma reformulação em suas folhas de estilo e em sua codificação semântica estrutural, assegurando uma experiência autônoma, digna e acessível a toda a população.

---

## 5. Referências Bibliográficas

*   **ASSOCIAÇÃO BRASILEIRA DE NORMAS TÉCNICAS.** *ABNT NBR 17225: Acessibilidade digital — Requisitos de acessibilidade para conteúdo na Web*. Rio de Janeiro: ABNT, 2024.
*   **BRASIL.** *Guia de Boas Práticas para Acessibilidade Digital*. Programa de Cooperação Reino Unido-Brasil em Acesso Digital, NIC.br, Governo Federal (gov.br), 2022.
*   **NIELSEN, Jakob.** *10 Usability Heuristics for User Interface Design*. Nielsen Norman Group, 1994. Disponível em: <https://www.nngroup.com/articles/ten-usability-heuristics/>.
*   **WORLD WIDE WEB CONSORTIUM (W3C).** *Web Content Accessibility Guidelines (WCAG) 2.2*. W3C Recommendation, 2023. Disponível em: <https://www.w3.org/TR/WCAG22/>.
