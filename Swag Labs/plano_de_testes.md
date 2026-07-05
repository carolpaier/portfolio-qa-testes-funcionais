# Plano de Testes – Swag Labs

**Objetivo do documento:** descrever o escopo, objetivos e atividades de teste para validar a qualidade do Swag Labs.
**Produto:** Swag Labs - E-commerce de exemplo para testes (login, catálogo, carrinho, checkout).
**Responsável:** Caroline Paier

## Escopo dos Testes
* Página de login
* Navegação no catálogo
* Funcionalidade do carrinho
* Fluxo de checkout
* Validação de mensagens de erro
* Testes de usabilidade básica

## Objetivos dos testes
* Verificar se o usuário consegue logar com credenciais válidas.
* Validar mensagens de erro em campo de login.
* Confirmar que itens são adicionados/removidos do carrinho.
* Validar fluxo de compra completo (checkout).

## Ambiente de teste
* **URL:** https://www.saucedemo.com
* **Ambiente de teste:** Navegador web
* **Navegador:** Google Chrome - Versão 143.0.7499.170

---

## Casos de teste

| ID | Descrição | Passos para reprodução | Resultado Esperado | Observações |
| :--- | :--- | :--- | :--- | :--- |
| **1** | Login com sucesso | 1. Acessar site<br>2. Inserir usuário válido no campo Username<br>3. Inserir senha válida no campo Password<br>4. Clicar no botão Login | O sistema deve realizar a autenticação dos dados, permitir o acesso ao sistema e redirecionar para a página inicial do e-commerce. | Pré-requisito: possuir usuário e senha registrados no sistema |
| **2** | Login sem dados | 1. Acessar o site<br>2. Deixar os campos Username e Password vazios<br>3. Clicar no botão Login | O sistema deve exibir uma mensagem de erro informando que o campo Username é obrigatório. | Mensagem de erro: *Epic sadface: Username is required* |
| **3** | Login sem senha | 1. Acessar o site<br>2. Inserir usuário válido no campo Username<br>3. Deixar o campo Password vazio<br>4. Clicar no botão Login | O sistema deve exibir uma mensagem de erro informando que o campo Password é obrigatório. | Mensagem de erro: *Epic sadface: Password is required* |
| **4** | Login com dados inválidos | 1. Acessar o site<br>2. Inserir usuário inválido no campo Username<br>3. Inserir senha inválida no campo Password<br>4. Clicar no botão Login | O sistema deve exibir uma mensagem de erro informando que as credenciais são inválidas e impedir o acesso | Mensagem de erro: *Epic sadface: Username and password do not match any user in this service* |
| **5** | Adição de item no carrinho | 1. Acessar a página de produtos<br>2. Selecionar um produto<br>3. Clicar no botão Add to cart | O sistema deve adicionar o item ao carrinho com sucesso e atualizar o número de itens no carrinho | Pré-requisito: usuário logado no sistema |
| **6** | Remover item do carrinho a partir da listagem | 1. Acessar a página de produtos<br>2. Clicar no botão Remove do item desejado | O item deve ser removido do carrinho com sucesso e o sistema deve atualizar o número de itens no carrinho | Pré-requisito: possuir itens no carrinho |
| **7** | Ordenar itens | 1. Acessar a página de produtos<br>2. Clicar no menu suspenso de ordenação<br>3. Selecionar uma opção de ordenação | O sistema deve realizar a ordenação dos itens conforme o filtro selecionado pelo usuário | Pré-requisito: usuário logado no sistema |
| **8** | Ver detalhes do item | 1. Acessar a página de produtos<br>2. Clicar sobre o nome ou imagem de um produto | O sistema deve redirecionar o usuário para a página de detalhes do produto | Pré-requisito: usuário logado no sistema |
| **9** | Continuar comprando a partir do carrinho | 1. Acessar carrinho de compras<br>2. Clicar no botão Continue Shopping | O sistema deve redirecionar o usuário para a página inicial do e-commerce | Pré-requisito: usuário logado |
| **10** | Checkout | 1. Acessar carrinho de compras<br>2. Clicar no botão Checkout<br>3. Informar dados obrigatórios (First Name, Last Name, Zip/Postal Code)<br>4. Clicar no botão Continue<br>5. Clicar no botão Finish | O sistema deve processar as informações do pedido e exibir uma mensagem de sucesso | Pré-requisito: possuir itens no carrinho.<br>Mensagem de sucesso: *Thank you for your order! Your order has been dispatched, and will arrive just as fast as the pony can get there!* |