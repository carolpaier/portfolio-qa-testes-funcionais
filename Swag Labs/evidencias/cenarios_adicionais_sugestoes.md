## Cenários adicionais de teste

Os testes descritos neste documento representam os principais fluxos funcionais do sistema. Em um ambiente real de projeto, outros cenários relevantes também poderiam ser considerados para ampliar a cobertura de qualidade do produto, conforme exemplos abaixo.

### Cenários Funcionais Adicionais
* Login com usuário bloqueado
* Múltiplas tentativas de login inválido
* Inclusão e exclusão de múltiplos itens no carrinho
* Validação de tipo de dados inseridos como CEP apenas com números
* Validação de cálculo do valor total da compra
* Interrupção do fluxo de checkout
* Comportamento do sistema ao atualizar a página durante uma compra
* Persistência do carrinho ao sair e retornar ao sistema

### Cenários de Acessibilidade
* Navegação completa utilizando apenas teclado
* Presença de rótulos (labels) nos campos de formulário
* Leitura correta da interface por leitores de tela
* Contraste adequado entre texto e fundo
* Foco visível ao navegar pelos elementos da página
* Tamanho e legibilidade dos textos e botões

### Cenários de Segurança
* Proteção de dados sensíveis no fluxo de checkout
* Verificação do uso de HTTPS
* Validação de sessão expirada durante o processo de compra
* Tentativas de manipulação de valores no carrinho via navegador
* Prevenção contra injeção de código nos campos de formulário

### Sugestões de Melhoria
* Feedback visual mais claro ao adicionar ou remover itens do carrinho
* Botão para alterar quantidade de cada item no carrinho
* Botão adicional no card do produto para adicionar ao carrinho e finalizar a compra
* Carrossel com indicação de produtos semelhantes ao ver detalhes de um produto
* Mostrar avaliação dos produtos nos detalhes do item