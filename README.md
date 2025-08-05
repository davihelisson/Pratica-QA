# Atividade Prática - O Dia-a-Dia de QA

## Contexto
A proposta é mostrar alguns itens relacionados a prática de Testes Manuais Funcionais (QA).


## Fluxo de Trabalho de Desenvolvimento
![Fluxo Flowchart](Fluxo_diagram.svg)

## Ciclo de Vida do BUG
![Bug Flowchart](Bug_diagram.svg)


---

## 🧾 User Story 1

### Funcionalidade:
**Filtro de Produtos por Categoria e Faixa de Preço**

### Valor:
**Facilitar a localização de produtos específicos, otimizando a experiência de compra do cliente.**

### Narrativa de Usuário:
**A FIM DE** encontrar rapidamente produtos compatíveis com meu orçamento e interesse  
**COMO** cliente da loja virtual  
**QUERO** filtrar os produtos por categoria e faixa de preço  
**ASSIM QUE** eu estiver navegando pela página de listagem de produtos

### REQUISITOS:
- **Atores:** Cliente logado ou visitante
- **Interfaces:** Página de listagem de produtos com filtros dinâmicos
- **Dados:** Criação de filtros dinâmicos no front-end, integração com backend via API
- **Plataformas:** Web (desktop e mobile)
- **Ambientes:** Teste / Produção

### Critérios de Aceite:
**CENÁRIO:** uso de filtros de produto  
**DADO QUE** o cliente acessa a listagem de produtos  
**QUANDO** ele selecionar a categoria "Placas de Vídeo" e faixa de preço entre R$1000 e R$2000  
**ENTÃO** o sistema deve exibir apenas os produtos correspondentes aos filtros aplicados


---

## 🧾 User Story 2

### Funcionalidade:
**Notificação por E-mail de Produto Disponível**

### Valor:
**Permitir que clientes interessados comprem itens fora de estoque assim que forem reabastecidos.**

### Narrativa de Usuário:
**A FIM DE** comprar um produto indisponível no momento  
**COMO** cliente da loja  
**QUERO** ser notificado por e-mail  
**ASSIM QUE** o produto estiver disponível novamente no estoque

### REQUISITOS:
- **Atores:** Cliente logado
- **Interfaces:** Página do produto (botão de ativar notificação)
- **Dados:** Banco de dados de assinaturas de notificação; API para gerenciar alertas; verificação periódica de estoque
- **Plataformas:** Web (desktop e mobile)
- **Ambientes:** Teste / Produção / Protótipo

### Critérios de Aceite:
**CENÁRIO:** receber uma notificação  
**DADO QUE** determinado usuário está logado no site  
**QUANDO** o usuário clicar em "Avisar quando disponível" em um produto esgotado  
**ENTÃO** o sistema deve registrar a solicitação e enviar um e-mail quando o estoque for atualizado para esse produto

