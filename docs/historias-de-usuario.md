# Histórias de Usuário — OneHub

## 1. Apresentação

As histórias de usuário representam as necessidades dos perfis que utilizarão o OneHub. Elas seguem o formato:

> Como [tipo de usuário], quero [objetivo], para [benefício].

Cada história está relacionada a um Requisito Funcional (RF) e possui critérios de aceitação para orientar a validação do comportamento esperado.

## 2. HU01 — Cadastro de usuário (RF01)

**História**

Como visitante, quero criar uma conta como comprador ou vendedor, para utilizar os recursos da plataforma de acordo com meu perfil.

**Critérios de aceitação**
- O formulário solicita os campos obrigatórios.
- É possível selecionar comprador ou vendedor.
- O sistema rejeita e-mail já cadastrado e informa erros de validação.
- Após o cadastro, a conta fica associada ao perfil escolhido.

## 3. HU02 — Autenticação (RF02)

**História**

Como usuário cadastrado, quero entrar e sair da minha conta, para acessar com segurança as funcionalidades correspondentes ao meu perfil.

**Critérios de aceitação**
- Credenciais válidas permitem entrar na conta.
- Credenciais inválidas não permitem acesso e geram mensagem adequada.
- O usuário consegue encerrar a sessão.
- Recursos restritos exigem autenticação.

## 4. HU03 — Recuperação de senha (RF03)

**História**

Como usuário que não consegue acessar sua conta, quero solicitar a recuperação da senha, para voltar a utilizar a plataforma.

**Critérios de aceitação**
- O usuário pode informar o e-mail associado à conta.
- O sistema apresenta confirmação da solicitação.
- O processo não revela a senha atual do usuário.
- A redefinição deve ocorrer por um mecanismo seguro.

## 5. HU04 — Gerenciamento de loja (RF04)

**História**

Como vendedor, quero cadastrar e atualizar as informações da minha loja, para apresentar meu negócio aos consumidores.

**Critérios de aceitação**
- O vendedor autenticado consegue cadastrar as informações exigidas.
- O vendedor consegue atualizar os dados da própria loja.
- O sistema impede que um vendedor altere a loja de outro usuário.
- As informações salvas são exibidas na página da loja.

## 6. HU05 — Cadastro de produtos (RF05)

**História**

Como vendedor, quero cadastrar produtos com descrição, preço, categoria e imagem, para divulgar meu catálogo no OneHub.

**Critérios de aceitação**
- O formulário solicita os dados definidos como obrigatórios.
- O sistema valida os campos antes de salvar.
- O produto fica associado à loja do vendedor autenticado.
- O produto cadastrado pode ser encontrado na vitrine.

## 7. HU06 — Edição e remoção de produtos (RF06)

**História**

Como vendedor, quero editar ou remover produtos da minha loja, para manter meu catálogo atualizado.

**Critérios de aceitação**
- O vendedor consegue editar os dados de seus produtos.
- O vendedor consegue solicitar a remoção de um produto.
- O sistema impede alterações em produtos de outras lojas.
- As mudanças são refletidas na vitrine.

## 8. HU07 — Visualização de produtos (RF07)

**História**

Como visitante ou comprador, quero visualizar os produtos e seus detalhes, para conhecer as opções disponíveis antes de entrar em contato com o vendedor.

**Critérios de aceitação**
- A vitrine apresenta os produtos disponíveis.
- Cada produto apresenta informações essenciais, como nome, imagem e preço.
- O usuário consegue abrir a página de detalhes.
- Os detalhes apresentam a descrição e a identificação da loja responsável.

## 9. HU08 — Pesquisa de produtos (RF08)

**História**

Como comprador, quero pesquisar produtos por nome e categoria, para encontrar itens de meu interesse com facilidade.

**Critérios de aceitação**
- O usuário consegue informar um termo de pesquisa.
- O usuário consegue selecionar uma categoria.
- Os resultados correspondem aos critérios informados.
- Quando não houver resultados, o sistema informa isso claramente.

## 10. HU09 — Favoritos (RF09)

**História**

Como comprador autenticado, quero salvar produtos como favoritos, para encontrá-los novamente com facilidade.

**Critérios de aceitação**
- O usuário consegue adicionar um produto aos favoritos.
- O usuário consegue remover um produto dos favoritos.
- A lista é associada à conta autenticada.
- O usuário consegue consultar sua lista de favoritos.

## 11. HU10 — Contato com vendedor (RF10)

**História**

Como comprador, quero visualizar as informações de contato do vendedor, para tirar dúvidas ou demonstrar interesse em um produto.

**Critérios de aceitação**
- A página do produto ou da loja apresenta os contatos disponibilizados pelo vendedor.
- O canal de contato é apresentado de forma identificável.
- Quando houver link para canal externo, ele direciona ao contato correspondente.
- O sistema não exibe informações de contato que o vendedor não cadastrou.

## 12. Relação entre Requisitos Funcionais e Histórias

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
