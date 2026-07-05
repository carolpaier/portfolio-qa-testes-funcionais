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

## Evidências de Testes

### 1. Login com sucesso
![Tela de login do Swag Labs com os campos de usuário e senha preenchidos com credenciais válidas](evidencias/login_com_sucesso_1.jpg)
![Página inicial do e-commerce exibindo o catálogo de produtos logo após a autenticação bem-sucedida](evidencias/login_com_sucesso_2.jpg)
![Menu de navegação lateral expandido na página inicial de produtos](evidencias/login_com_sucesso_3.jpg)

### 2. Login sem dados
![Tela de login do Swag Labs com os campos de usuário e senha completamente em branco](evidencias/login_sem_dados_1.jpg)
![Mensagem de erro destacada em vermelho informando 'Epic sadface: Username is required'](evidencias/login_sem_dados_2.jpg)

### 3. Login sem senha
![Tela de login preenchida com um usuário válido, mas com o campo de senha em branco](evidencias/login_sem_senha_1.jpg)
![Mensagem de erro destacada em vermelho informando 'Epic sadface: Password is required'](evidencias/login_sem_senha_2.jpg)

### 4. Login com dados inválidos
![Tela de login com informações de usuário e senha incorretas preenchidas nos campos](evidencias/login_com_dados_invalidos_1.jpg)
![Mensagem de erro destacada em vermelho informando que o usuário e a senha não coincidem neste serviço](evidencias/login_com_dados_invalidos_2.jpg)

### 5. Adição de item no carrinho
![Listagem de produtos no catálogo com destaque para o clique no botão 'Add to cart'](evidencias/adicao_de_item_no_carrinho_1.jpg)
![Catálogo de produtos atualizado, exibindo o ícone do carrinho com a contagem de 1 item e o botão alterado para 'Remove'](evidencias/adicao_de_item_no_carrinho_2.jpg)

### 6. Remover item do carrinho a partir da listagem
![Produto no catálogo exibindo o botão 'Remove', indicando que já está no carrinho](evidencias/remover_item_do_carrinho_a_partir_da_listagem_1.jpg)
![Catálogo de produtos atualizado após a remoção, com o ícone do carrinho zerado e o botão restaurado para 'Add to cart'](evidencias/remover_item_do_carrinho_a_partir_da_listagem_2.jpg)

### 7. Ordenar itens
![Menu suspenso de ordenação no topo da listagem de produtos](evidencias/ordenar_itens_1.jpg)
![Menu de ordenação expandido exibindo a opção de organizar os preços do menor para o maior](evidencias/ordenar_itens_2.jpg)
![Listagem de produtos reordenada com sucesso, exibindo os itens com os menores preços primeiro](evidencias/ordenar_itens_3.jpg)

### 8. Ver detalhes do item
![Ação de clique sobre o título e a imagem de um produto específico no catálogo principal](evidencias/ver_detalhes_do_item_1.jpg)
![Página exclusiva de detalhes do produto, exibindo imagem ampliada, descrição completa e botão de adicionar ao carrinho](evidencias/ver_detalhes_do_item_2.jpg)

### 9. Continuar comprando a partir do carrinho
![Página do carrinho de compras com um item e destaque para o clique no botão 'Continue Shopping'](evidencias/continuar_comprando_a_partir_do_carrinho_1.jpg)
![Redirecionamento bem-sucedido de volta para a página inicial do catálogo de produtos](evidencias/continuar_comprando_a_partir_do_carrinho_2.jpg)

### 10. Checkout
![Página do carrinho de compras com destaque para o clique no botão 'Checkout'](evidencias/checkout_1.jpg)
![Formulário de informações do cliente solicitando Nome, Sobrenome e Código Postal em branco](evidencias/checkout_2.jpg)
![Formulário de informações do cliente devidamente preenchido com os dados do usuário](evidencias/checkout_3.jpg)
![Página de visão geral do pedido (Checkout Overview) exibindo o resumo dos itens, informações de pagamento, envio e valor total](evidencias/checkout_4.jpg)
![Página de confirmação com ícone verde de check e a mensagem de sucesso 'Thank you for your order!'](evidencias/checkout_5.jpg)