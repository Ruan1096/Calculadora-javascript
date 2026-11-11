# 🧮 Projeto Web Calculator: Engenharia Front-End de uma Calculadora Moderna

Este repositório apresenta uma aplicação web de calculadora desenvolvida inteiramente com tecnologias nativas (*Vanilla Stack*), concebida para unir robustez lógica, design responsivo e uma experiência de usuário (UX) refinada.

O projeto foi estruturado não apenas como uma ferramenta utilitária, mas como um estudo de arquitetura front-end leve, demonstrando domínio sobre a manipulação do DOM, estilização avançada via CSS e estruturação semântica em HTML5.

---

## 🎯 Propósito e Justificativa do Projeto

No ecossistema de desenvolvimento web moderno, frameworks e bibliotecas pesadas muitas vezes abstraem os fundamentos da computação cliente. O objetivo principal deste projeto foi construir uma aplicação funcional do zero, aplicando conceitos essenciais de engenharia de software sem depender de dependências externas ou bibliotecas de terceiros (*zero dependencies*).

A motivação por trás da construção envolveu:

* **Domínio do DOM (Document Object Model):** Compreender a comunicação síncrona entre o layout estático e a interatividade gerenciada por scripts.
* **Resolução de Layouts Complexos:** Desafios de alinhamento visual, como centralização absoluta fluida e proporções harmônicas de grid baseadas em tabelas semânticas.
* **Tratamento de Exceções Lógicas:** Garantir que entradas inválidas do usuário não quebrem o fluxo de execução do script.

---

## 🛠️ Arquitetura e Estrutura do Código

A aplicação é dividida em três pilares fundamentais da web, mantendo uma separação estrita de responsabilidades (*Separation of Concerns*):

```text
├── index.html       # Camada de Estrutura e Marcação Semântica
├── cal-styles.css   # Camada de Estilização, Cores e Layout Visual
└── cal-script.js    # Camada de Regras de Negócio e Lógica Computacional

```

### 1. Estrutura e Marcação (`index.html`)

A interface foi estruturada utilizando marcação HTML5 semântica. Para organizar a matriz de botões de forma consistente em diferentes viewports, utilizou-se uma estrutura tabular combinada com atributos de controle de células (`rowspan` e `colspan`), garantindo que o teclado numérico e de operadores mantenha uma grade geométrica estável. O display de resultados é alimentado por um elemento dinâmico atualizado via script.

### 2. Estilização e Design System (`cal-styles.css`)

O design adota uma identidade visual moderna inspirada em conceitos de *Dark Mode* e minimalismo:

* **Fundo Imersivo:** Utilização de gradientes lineares dinâmicos (`linear-gradient(45deg, black, crimson)`) combinados com altura de viewport controlada (`100vh`) para evitar rolagens desnecessárias.
* **Posicionamento Avançado:** A caixa da calculadora é perfeitamente centralizada na tela utilizando o modelo de posicionamento absoluto em conjunto com a matriz de transformação (`position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%);`), garantindo suporte cross-browser com prefixos de compatibilidade (`-webkit`, `-moz`, `-ms`, `-o`).
* **Feedback Visual e Interatividade:** Os botões possuem estados de foco e transições suaves de cor no gatilho `:hover`, além de bordas arredondadas e propriedades de *box-sizing* normalizadas para eliminar inconsistências de espaçamento (`border-box`).

### 3. Lógica e Inteligência Computacional (`cal-script.js`)

O script foi escrito em JavaScript moderno (ES6+), implementando funções modulares e reativas:

* **`insert(num)`:** Captura o evento de clique nos botões numéricos e operadores, lendo o estado atual do visor (`innerHTML`) e concatenando a nova entrada de forma sequencial.
* **`back()`:** Implementa a lógica de remoção retroativa (*backspace*), utilizando o método `substring()` para fatiar a string do visor, eliminando apenas o último caractere inserido.
* **`clean()`:** Executa o reset completo do estado visual do visor, limpando quaisquer dados ou erros residuais.
* **`calcular()`:** Responsável pelo núcleo matemático da aplicação. A função verifica a integridade da string armazenada no visor e utiliza a função de avaliação do interpretador para processar a expressão aritmética de forma síncrona, incorporando um bloco de tratamento de exceções (`try...catch` / validação condicional) para mitigar falhas caso o usuário dispare o gatilho de igualdade sem uma expressão válida.

---

## ⚙️ Funcionalidades Implementadas

* **Operações Aritméticas Completas:** Suporte nativo a adição, subtração, multiplicação, divisão e ponto flutuante (números decimais).
* **Visor Inteligente com Auto-Ajuste:** O display possui propriedades de estouro controladas (`overflow: hidden` e `word-wrap`), garantindo que sequências numéricas longas respeitem os limites da caixa de texto sem quebrar o layout da interface.
* **Correção Incremental:** Capacidade de apagar dígito por dígito sem precisar reiniciar o cálculo inteiro.

---

Previa :


<img width="1198" height="532" alt="image" src="https://github.com/user-attachments/assets/d12175dc-8c4a-4718-82b5-0fb6ab1c1f64" />


---
