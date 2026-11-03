# OneHub — Especificação de Requisitos

## 1. Visão geral

O OneHub é uma plataforma web de comércio local que aproxima consumidores e vendedores da região. A solução permite que vendedores divulguem suas lojas e produtos, enquanto consumidores podem consultar o catálogo, pesquisar itens, salvar favoritos e entrar em contato com os vendedores.

## 2. Requisitos Funcionais

Os requisitos abaixo representam as dez funcionalidades priorizadas para o escopo inicial do OneHub.

| ID | Requisito | Descrição | Prioridade |
|---|---|---|---|
| RF01 | Cadastro de usuários | O sistema deve permitir que visitantes criem uma conta e indiquem se utilizarão a plataforma como comprador ou vendedor. | Alta |
| RF02 | Autenticação | O sistema deve permitir que usuários cadastrados entrem e saiam de suas contas por meio de credenciais válidas. | Alta |
| RF03 | Recuperação de senha | O sistema deve permitir que usuários solicitem a recuperação da senha associada à sua conta. | Média |
| RF04 | Gerenciamento de loja | O sistema deve permitir que vendedores cadastrem e atualizem as informações de sua loja. | Alta |
| RF05 | Cadastro de produtos | O sistema deve permitir que vendedores cadastrem produtos com informações como nome, descrição, preço, categoria e imagem. | Alta |
| RF06 | Gerenciamento de produtos | O sistema deve permitir que vendedores editem ou removam os produtos cadastrados em sua própria loja. | Alta |
| RF07 | Visualização de produtos | O sistema deve disponibilizar aos visitantes e compradores uma vitrine de produtos e uma página com os detalhes de cada item. | Alta |
| RF08 | Pesquisa e filtragem | O sistema deve permitir que usuários encontrem produtos por nome e categoria. | Alta |
| RF09 | Lista de favoritos | O sistema deve permitir que usuários autenticados salvem e removam produtos de sua lista de favoritos. | Média |
| RF10 | Contato com vendedor | O sistema deve apresentar uma forma de contato com o vendedor, permitindo que o comprador inicie uma comunicação por canal externo, como WhatsApp, quando disponibilizado. | Alta |

### 2.1 Detalhamento e critérios gerais

- RF01: o cadastro deve validar os campos obrigatórios, impedir a reutilização de e-mail já cadastrado e associar o perfil escolhido à conta.
- RF02: somente credenciais válidas devem permitir acesso à área autenticada; o usuário deve poder encerrar a sessão.
- RF03: a solicitação de recuperação deve utilizar o e-mail associado à conta e apresentar uma confirmação da solicitação.
- RF04: somente o vendedor responsável deve poder cadastrar ou alterar os dados de sua loja.
- RF05: o cadastro deve validar os dados obrigatórios e associar o produto à loja do vendedor autenticado.
- RF06: alterações e remoções devem ser permitidas somente ao vendedor proprietário do produto.
- RF07: a vitrine deve apresentar informações essenciais do produto e permitir acesso aos seus detalhes.
- RF08: a pesquisa deve considerar o nome do produto e a categoria selecionada, apresentando resultados compatíveis com os termos informados.
- RF09: o usuário deve conseguir adicionar e remover produtos dos favoritos, e a lista deve permanecer associada à sua conta.
- RF10: a página do produto ou da loja deve apresentar os dados de contato cadastrados pelo vendedor e permitir iniciar o contato pelo canal informado.

## 3. Requisitos Não Funcionais

| ID | Requisito | Descrição / critério verificável |
|---|---|---|
| RNF01 | Usabilidade | A interface deve apresentar navegação clara, textos compreensíveis e formulários com indicação de campos obrigatórios e erros de preenchimento. |
| RNF02 | Responsividade | As páginas devem adaptar sua apresentação a dispositivos móveis, tablets e computadores, sem perda das funções essenciais. |
| RNF03 | Segurança e controle de acesso | O sistema deve proteger credenciais e restringir operações de gerenciamento aos usuários autorizados, impedindo que um vendedor altere dados de outra loja. |
| RNF04 | Desempenho | As páginas e resultados de pesquisa devem ser apresentados em tempo adequado; como meta de projeto, as operações comuns devem responder em até 3 segundos em condições normais de uso. |
| RNF05 | Compatibilidade | A aplicação web deve funcionar nos navegadores modernos de uso comum e manter suas funções essenciais em diferentes tamanhos de tela. |
| RNF06 | Integridade dos dados | Os dados de usuários, lojas, produtos e favoritos devem manter associações consistentes, evitando registros órfãos e alterações não autorizadas. |

## 4. Histórias de Usuário

As histórias correspondem aos dez requisitos funcionais priorizados e seguem o formato “Como [tipo de usuário], quero [objetivo], para [benefício]”.

### HU01 — Cadastro de usuário (RF01)
Como visitante, quero criar uma conta como comprador ou vendedor, para utilizar os recursos da plataforma de acordo com meu perfil.

**Critérios de aceitação**
- O formulário solicita os campos obrigatórios.
- É possível selecionar comprador ou vendedor.
- O sistema rejeita e-mail já cadastrado e informa erros de validação.
- Após o cadastro, a conta fica associada ao perfil escolhido.

### HU02 — Autenticação (RF02)
Como usuário cadastrado, quero entrar e sair da minha conta, para acessar com segurança as funcionalidades correspondentes ao meu perfil.

**Critérios de aceitação**
- Credenciais válidas permitem entrar na conta.
- Credenciais inválidas não permitem acesso e geram mensagem adequada.
- O usuário consegue encerrar a sessão.
- Recursos restritos exigem autenticação.

### HU03 — Recuperação de senha (RF03)
Como usuário que não consegue acessar sua conta, quero solicitar a recuperação da senha, para voltar a utilizar a plataforma.

**Critérios de aceitação**
- O usuário pode informar o e-mail associado à conta.
- O sistema apresenta confirmação da solicitação.
- O processo não revela a senha atual do usuário.
- A redefinição deve ocorrer por um mecanismo seguro.

### HU04 — Gerenciamento de loja (RF04)
Como vendedor, quero cadastrar e atualizar as informações da minha loja, para apresentar meu negócio aos consumidores.

**Critérios de aceitação**
- O vendedor autenticado consegue cadastrar as informações exigidas.
- O vendedor consegue atualizar os dados da própria loja.
- O sistema impede que um vendedor altere a loja de outro usuário.
- As informações salvas são exibidas na página da loja.

### HU05 — Cadastro de produtos (RF05)
Como vendedor, quero cadastrar produtos com descrição, preço, categoria e imagem, para divulgar meu catálogo no OneHub.

**Critérios de aceitação**
- O formulário solicita os dados definidos como obrigatórios.
- O sistema valida os campos antes de salvar.
- O produto fica associado à loja do vendedor autenticado.
- O produto cadastrado pode ser encontrado na vitrine.

### HU06 — Edição e remoção de produtos (RF06)
Como vendedor, quero editar ou remover produtos da minha loja, para manter meu catálogo atualizado.

**Critérios de aceitação**
- O vendedor consegue editar os dados de seus produtos.
- O vendedor consegue solicitar a remoção de um produto.
- O sistema impede alterações em produtos de outras lojas.
- As mudanças são refletidas na vitrine.

### HU07 — Visualização de produtos (RF07)
Como visitante ou comprador, quero visualizar os produtos e seus detalhes, para conhecer as opções disponíveis antes de entrar em contato com o vendedor.

**Critérios de aceitação**
- A vitrine apresenta os produtos disponíveis.
- Cada produto apresenta informações essenciais, como nome, imagem e preço.
- O usuário consegue abrir a página de detalhes.
- Os detalhes apresentam a descrição e a identificação da loja responsável.

### HU08 — Pesquisa de produtos (RF08)
Como comprador, quero pesquisar produtos por nome e categoria, para encontrar itens de meu interesse com facilidade.

**Critérios de aceitação**
- O usuário consegue informar um termo de pesquisa.
- O usuário consegue selecionar uma categoria.
- Os resultados correspondem aos critérios informados.
- Quando não houver resultados, o sistema informa isso claramente.

### HU09 — Favoritos (RF09)
Como comprador autenticado, quero salvar produtos como favoritos, para encontrá-los novamente com facilidade.

**Critérios de aceitação**
- O usuário consegue adicionar um produto aos favoritos.
- O usuário consegue remover um produto dos favoritos.
- A lista é associada à conta autenticada.
- O usuário consegue consultar sua lista de favoritos.

### HU10 — Contato com vendedor (RF10)
Como comprador, quero visualizar as informações de contato do vendedor, para tirar dúvidas ou demonstrar interesse em um produto.

**Critérios de aceitação**
- A página do produto ou da loja apresenta os contatos disponibilizados pelo vendedor.
- O canal de contato é apresentado de forma identificável.
- Quando houver link para canal externo, ele direciona ao contato correspondente.
- O sistema não exibe informações de contato que o vendedor não cadastrou.

## 5. Relação entre requisitos e histórias

| Requisito Funcional | História de Usuário |
|---|---|
| RF01 — Cadastro de usuários | HU01 — Cadastro de usuário |
| RF02 — Autenticação | HU02 — Autenticação |
| RF03 — Recuperação de senha | HU03 — Recuperação de senha |
| RF04 — Gerenciamento de loja | HU04 — Gerenciamento de loja |
| RF05 — Cadastro de produtos | HU05 — Cadastro de produtos |
| RF06 — Gerenciamento de produtos | HU06 — Edição e remoção de produtos |
| RF07 — Visualização de produtos | HU07 — Visualização de produtos |
| RF08 — Pesquisa e filtragem | HU08 — Pesquisa de produtos |
| RF09 — Lista de favoritos | HU09 — Favoritos |
| RF10 — Contato com vendedor | HU10 — Contato com vendedor |

## 6. Observações

- As prioridades representam uma proposta inicial para o escopo do OneHub e podem ser ajustadas pelo grupo.
- Os critérios de aceitação detalham o comportamento esperado das histórias; não substituem a validação do grupo com as orientações e padrões apresentados em sala.
- Os requisitos não funcionais devem ser verificados durante a avaliação da solução.
