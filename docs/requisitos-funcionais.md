# Requisitos Funcionais — OneHub

## 1. Visão geral

Os Requisitos Funcionais (RF) descrevem as funcionalidades que o sistema OneHub deve oferecer. Os dez requisitos abaixo representam as funcionalidades priorizadas para o escopo inicial do projeto.

## 2. Lista de Requisitos Funcionais

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

## 3. Detalhamento e critérios gerais

- **RF01 — Cadastro de usuários:** o cadastro deve validar os campos obrigatórios, impedir a reutilização de e-mail já cadastrado e associar o perfil escolhido à conta.
- **RF02 — Autenticação:** somente credenciais válidas devem permitir acesso à área autenticada; o usuário deve poder encerrar a sessão.
- **RF03 — Recuperação de senha:** a solicitação de recuperação deve utilizar o e-mail associado à conta e apresentar uma confirmação da solicitação.
- **RF04 — Gerenciamento de loja:** somente o vendedor responsável deve poder cadastrar ou alterar os dados de sua loja.
- **RF05 — Cadastro de produtos:** o cadastro deve validar os dados obrigatórios e associar o produto à loja do vendedor autenticado.
- **RF06 — Gerenciamento de produtos:** alterações e remoções devem ser permitidas somente ao vendedor proprietário do produto.
- **RF07 — Visualização de produtos:** a vitrine deve apresentar informações essenciais do produto e permitir acesso aos seus detalhes.
- **RF08 — Pesquisa e filtragem:** a pesquisa deve considerar o nome do produto e a categoria selecionada, apresentando resultados compatíveis com os termos informados.
- **RF09 — Lista de favoritos:** o usuário deve conseguir adicionar e remover produtos dos favoritos, e a lista deve permanecer associada à sua conta.
- **RF10 — Contato com vendedor:** a página do produto ou da loja deve apresentar os dados de contato cadastrados pelo vendedor e permitir iniciar o contato pelo canal informado.

## 4. Observações

As prioridades representam uma proposta inicial para o escopo do OneHub e podem ser ajustadas pelo grupo durante a validação dos requisitos.
