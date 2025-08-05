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


---

# Casos de Teste


---

## ✅ Técnica: Step-by-Step

### 🧪 Caso de Teste 1 – Aplicação de Filtro por Categoria e Faixa de Preço

**Identificação:** CT001 – Aplicar filtros de categoria e faixa de preço  
**Objetivo:** Verificar se o sistema retorna corretamente os produtos com base nos filtros aplicados pelo usuário.  

**Pré-condições:**
- O usuário está na página de listagem de produtos.
- O sistema possui produtos cadastrados em múltiplas categorias e faixas de preço.

**Dados de Teste:**
- Categoria: “Placas de Vídeo”
- Faixa de preço: R$1000 a R$2000

**Passos:**

| Passo | Ação do Usuário                                       | Resultado Esperado                                      |
|------:|--------------------------------------------------------|----------------------------------------------------------|
| 1     | Acessar a loja virtual                                 | Página principal da loja é carregada                    |
| 2     | Navegar até a seção de produtos                        | Página de listagem de produtos é exibida                |
| 3     | Selecionar a categoria “Placas de Vídeo”               | Somente produtos dessa categoria são listados           |
| 4     | Definir a faixa de preço de R$1000 a R$2000            | Lista de produtos é atualizada com base nos filtros     |
| 5     | Verificar os produtos exibidos                         | Todos os produtos exibidos pertencem à categoria e faixa definida |

**Critério de Sucesso:**  
Todos os produtos exibidos após a aplicação dos filtros estão corretos conforme os parâmetros definidos.

---

### 🧪 Caso de Teste 2 – Notificação por E-mail de Produto Indisponível

**Identificação:** CT002 – Solicitar notificação de produto indisponível  
**Objetivo:** Verificar se a funcionalidade de solicitação de notificação por e-mail funciona corretamente quando um produto está fora de estoque.

**Pré-condições:**
- O usuário está logado.
- Existe ao menos um produto marcado como “Indisponível”.
- O e-mail do usuário está confirmado no sistema.

**Dados de Teste:**
- Produto: “Teclado Mecânico XYZ”
- E-mail: usuario@exemplo.com

**Passos:**

| Passo | Ação do Usuário                                                       | Resultado Esperado                                               |
|------:|------------------------------------------------------------------------|------------------------------------------------------------------|
| 1     | Logar na conta da loja virtual                                         | Usuário autenticado com sucesso                                 |
| 2     | Acessar a página do produto “Teclado Mecânico XYZ”                    | Página do produto é carregada com status "Indisponível"         |
| 3     | Clicar no botão “Avisar quando disponível”                            | Sistema confirma solicitação e exibe mensagem de confirmação     |
| 4     | Aguardar a reposição do produto no sistema (estoque > 0)             | Produto é atualizado para “Disponível”                          |
| 5     | Verificar a caixa de entrada do e-mail cadastrado                    | E-mail de notificação é recebido informando a disponibilidade   |

**Critério de Sucesso:**  
Usuário recebe e-mail assim que o produto volta ao estoque.

---

## ✅ Técnica: BDD (Behavior-Driven Development)

### 🧪 Caso de Teste BDD 1 – Finalizar Compra com Produto em Estoque

```gherkin
Funcionalidade: Finalização de compra

  Como cliente da loja virtual
  Quero poder finalizar uma compra com sucesso
  Para que eu possa receber meus produtos em casa

  Cenário: Finalizar pedido com item em estoque
    Dado que o cliente está logado na loja
    E adicionou um produto disponível ao carrinho
    Quando acessar o carrinho e clicar em “Finalizar Compra”
    E preencher os dados de entrega e pagamento válidos
    Então o sistema deve concluir o pedido
    E exibir a mensagem “Compra realizada com sucesso”
```

---

### 🧪 Caso de Teste BDD 2 – Falha no Login por Senha Incorreta

```gherkin
Funcionalidade: Autenticação de usuário

  Como usuário registrado
  Quero ser impedido de acessar o sistema com senha errada
  Para garantir a segurança da minha conta

  Cenário: Tentativa de login com senha incorreta
    Dado que o usuário acessa a tela de login
    E informa o e-mail registrado "cliente@exemplo.com"
    E digita a senha incorreta "senha123"
    Quando clicar no botão “Entrar”
    Então o sistema deve exibir a mensagem “Usuário ou senha inválidos”
    E o login não deve ser realizado
```
