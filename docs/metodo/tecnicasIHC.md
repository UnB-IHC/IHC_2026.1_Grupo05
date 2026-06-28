# Guia de Bolso: Técnicas de IHC

Este guia reúne as principais **técnicas de Interação Humano-Computador (IHC)** adotadas ou aplicáveis a este projeto para avaliar, simular e quantificar a usabilidade e a experiência do usuário. 

---

## 1. Persona (Perfil e Necessidades de Usuário)

As **Personas** são arquétipos fictícios criados a partir de dados reais dos usuários para representar comportamentos, necessidades, limitações e frustrações comuns do público-alvo.

*   **Para que serve:** Centralizar as decisões de design e desenvolvimento nas necessidades de pessoas reais, evitando o viés de projetar para si mesmo.
*   **Como foi usado no projeto:** Desenvolvemos a Persona de Referência **[Carlos Alberto Ferreira](../avaliacao/persona.md)** (56 anos, técnico em manutenção predial e com baixa afinidade digital) para guiar a simulação de tarefas no portal do DETRAN-DF.

> [!TIP]
> **Como criar uma Persona rápida:**
> 1. Colete dados demográficos e de comportamento do seu público real.
> 2. Identifique padrões de uso (ex: facilidade com celular, mas medo de usar o computador).
> 3. Crie uma ficha resumida contendo: Foto/Nome fictício, Perfil, Frustrações e Necessidades de Interação.

---

## 2. Percurso Cognitivo (Cognitive Walkthrough)

O **Percurso Cognitivo** é um método de inspeção em que os avaliadores se colocam no lugar de uma persona e simulam a execução de tarefas críticas do sistema passo a passo, respondendo a quatro perguntas fundamentais:
1. O usuário tentará alcançar o efeito correto que a ação produz?
2. O usuário perceberá que o controle correto está disponível?
3. O usuário associará o controle correto com a ação que ele deseja realizar?
4. Se a ação correta for realizada, o usuário perceberá que está progredindo em direção ao seu objetivo?

*   **Para que serve:** Encontrar falhas de aprendizado e adivinhação em fluxos de tarefas novas para o usuário.
*   **Como foi usado no projeto:** Foi aplicado durante a inspeção do portal do DETRAN-DF na simulação de consulta de débitos e emissão de taxas.

---

## 3. Avaliação Heurística

É um método de inspeção sistemático em que especialistas avaliam a interface de acordo com princípios consagrados de usabilidade (as **[10 Heurísticas de Nielsen](heuristicas.md)**).

*   **Para que serve:** Identificar rapidamente a maioria dos problemas de usabilidade de uma interface de maneira econômica e sem a necessidade de recrutar usuários finais.
*   **Como foi usado no projeto:** Todos os problemas identificados no portal do DETRAN-DF foram categorizados de acordo com as heurísticas violadas (ex: falta de foco por teclado mapeada como falha de *Flexibilidade e Eficiência de Uso*).

---

## 4. Think Aloud (Pensar em Voz Alta)

O **Think Aloud** (Pensar em voz alta) é a técnica de observação mais rica em IHC. Consiste em pedir para o usuário realizar tarefas reais no sistema enquanto verbaliza em voz alta tudo o que está pensando, vendo, sentindo ou tentando fazer.

*   **Para que serve:** Entender o modelo mental do usuário, por que ele comete erros e quais áreas da interface causam maior sobrecarga cognitiva.
*   **Roteiro de Bolso para Aplicação:**
    1. **Prepare as tarefas:** Crie cenários objetivos (Ex: *"Tente emitir o boleto de licenciamento do seu carro"*).
    2. **Instrua o participante:** *"Por favor, fale em voz alta tudo o que passa pela sua cabeça. Não há respostas certas ou erradas; o sistema é que está sendo testado"*.
    3. **Observe e não interfira:** Se o usuário ficar calado, dê um leve incentivo: *"O que você está pensando agora?"*. Anote as hesitações, falhas e frustrações.

---

## 5. SUS (System Usability Scale)

A **System Usability Scale (SUS)** é um questionário padronizado, de alta fidelidade e de rápida aplicação, composto por 10 perguntas respondidas com base em uma escala Likert de 1 (Discordo totalmente) a 5 (Concordo totalmente).

*   **Para que serve:** Fornecer uma métrica quantitativa (de 0 a 100) sobre a facilidade de uso global do sistema.

### O Questionário SUS (10 Perguntas)
1. Eu gostaria de usar este sistema frequentemente.
2. Eu achei o sistema desnecessariamente complexo.
3. Eu achei o sistema fácil de usar.
4. Eu acho que precisaria de ajuda de suporte técnico para usar este sistema.
5. Eu achei que as várias funções deste sistema estavam bem integradas.
6. Eu achei que havia muita inconsistência neste sistema.
7. Eu imagino que a maioria das pessoas aprenderia a usar este sistema rapidamente.
8. Eu achei o sistema muito incômodo de usar.
9. Eu me senti muito confiante usando o sistema.
10. Eu precisei aprender muitas coisas novas antes de conseguir usar o sistema.

### Como calcular a pontuação SUS:
* Para as perguntas **ímpares (1, 3, 5, 7, 9)**: subtraia 1 da resposta dada pelo usuário ($Nota - 1$).
* Para as perguntas **pares (2, 4, 6, 8, 10)**: subtraia a resposta dada pelo usuário de 5 ($5 - Nota$).
* Some todos os valores convertidos e multiplique o total por **2,5**. O resultado final será uma nota de **0 a 100**.

> [!NOTE]
> **Interpretação da nota SUS:**
> - **Acima de 80.3:** Excelente (Interface altamente usável)
> - **Cerca de 68.0:** Média de mercado (Aceitável, mas necessita melhorias)
> - **Abaixo de 51.0:** Ruim / Inaceitável (Problema crítico de usabilidade)
