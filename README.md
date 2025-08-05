# Atividade Prática - O Dia-a-Dia de QA

## Contexto
A proposta é mostrar alguns itens relacionados a prática de Testes Manuais Funcionais (QA).


## Fluxo de Trabalho de Desenvolvimento
<<<<<<< HEAD
![Fluxo Flowchart](Fluxo_diagram.svg)
## Ciclo de Vida do BUG
![Bug Flowchart](Bug_diagram.svg)
=======
<pre>```mermaid flowchart TD A[TO DO] --> B[IN PROGRESS]
    B --> C{Impedimentos?}
    C -- Sim --> D[BLOCKED]
    C -- Não --> E[READY FOR TEST]
    E --> F{Aprovado?}
    F -- Sim --> G[DONE]
    F -- Não --> E
```</pre>
## Ciclo de Vida do BUG
<pre>
```mermaid
flowchart TD
    A["New"] --> B["Open"]
    B --> C{"É um bug?"}
    C -- Não --> D["Not a Bug"]
    C -- Sim --> E["Defered"]
    E --> F["Ready for Retest"]
    F --> G["Retesting"]
    G --> H{"Aprovado?"}
    H -- Sim --> I["Verified"]
    I --> J["Close"]
    H -- Não --> K["ReOpened"]
    K --> B
```</pre>
>>>>>>> 1b7295498548b857af34eabd4d9db38e5e629c41


