# Requisitos Não Funcionais — OneHub

## Visão geral

Esta documentação apresenta os **8 requisitos não funcionais ativos** da especificação atual do OneHub, com metas de qualidade propostas e critérios verificáveis. Os identificadores são mantidos para preservar a rastreabilidade existente no artigo e nas issues. Os RNFs retirados do escopo não são parte desta especificação.

> **Atenção:** os limites numéricos são metas de projeto ainda sujeitas à validação pela equipe e pelos serviços de infraestrutura utilizados. Um critério marcado em checklist exige evidência de teste.

## Requisitos ativos

| ID | Requisito | Issue |
|---|---|---|
| RNF01 | Responsividade da interface | [#11](https://github.com/ehnb1-creator/OneHub/issues/11) |
| RNF02 | Segurança e controle de acesso | [#12](https://github.com/ehnb1-creator/OneHub/issues/12) |
| RNF04 | Tempo de resposta | [#14](https://github.com/ehnb1-creator/OneHub/issues/14) |
| RNF05 | Disponibilidade da plataforma | [#15](https://github.com/ehnb1-creator/OneHub/issues/15) |
| RNF07 | Acessibilidade | [#17](https://github.com/ehnb1-creator/OneHub/issues/17) |
| RNF08 | Compatibilidade entre navegadores | [#18](https://github.com/ehnb1-creator/OneHub/issues/18) |
| RNF09 | Armazenamento e otimização de imagens | [#19](https://github.com/ehnb1-creator/OneHub/issues/19) |
| RNF10 | Backup e recuperação dos dados | [#20](https://github.com/ehnb1-creator/OneHub/issues/20) |

## Especificação e critérios verificáveis

### RNF01 — Responsividade da interface

**Tipo:** Requisito não funcional (meta de qualidade proposta para o MVP)

### Descrição verificável
O sistema deve apresentar corretamente suas interfaces em dispositivos com largura de tela entre **360 e 1920 px**, sem ocultar informações essenciais e sem exigir rolagem horizontal para executar operações principais.

### Critérios de aceitação / verificação
- [ ] Verificar cadastro, login, catálogo, pesquisa, detalhes e gerenciamento de loja nas larguras **360, 390, 768, 1366 e 1920 px**.
- [ ] Em cada largura, todos os campos obrigatórios, textos, imagens e controles das telas testadas permanecem legíveis e utilizáveis.
- [ ] Nenhum botão essencial fica oculto ou sobreposto a outro elemento.
- [ ] Nenhuma página testada apresenta rolagem horizontal causada pelo conteúdo principal.

**Requisitos funcionais relacionados:** RF01, RF03, RF05, RF06, RF07, RF08, RF09.

> **Situação:** os parâmetros quantitativos são metas propostas na especificação acadêmica e precisam ser aprovados pela equipe e testados na infraestrutura real. Marcar os critérios apenas após evidência de teste.

[Ver issue #11](https://github.com/ehnb1-creator/OneHub/issues/11)

---

### RNF02 — Segurança e controle de acesso

**Tipo:** Requisito não funcional (meta de qualidade proposta para o MVP)

### Descrição verificável
Todas as operações restritas devem exigir autenticação e autorização **no backend**, negando tentativas de usuários sem permissão, inclusive por chamadas diretas à API.

### Critérios de aceitação / verificação
- [ ] Todas as comunicações com os serviços de autenticação e dados devem ocorrer por **HTTPS**.
- [ ] Usuário não autenticado não pode cadastrar, editar ou excluir produtos por API.
- [ ] Realizar **10 tentativas** de alterar produtos de outros vendedores; **nenhuma** pode modificar dados.
- [ ] Aplicar políticas de autorização no backend, como **RLS do Supabase**, para isolar lojas e produtos por proprietário.
- [ ] Senhas e credenciais privadas não devem ser expostas em respostas públicas, logs do cliente ou arquivos enviados ao navegador; chaves administrativas do Supabase não podem estar no frontend.

**Requisitos funcionais relacionados:** RF01, RF02, RF03, RF04, RF05, RF09, RF10.

> **Situação:** os parâmetros quantitativos são metas propostas na especificação acadêmica e precisam ser aprovados pela equipe e testados na infraestrutura real. Marcar os critérios apenas após evidência de teste.

[Ver issue #12](https://github.com/ehnb1-creator/OneHub/issues/12)

---

### RNF04 — Tempo de resposta

**Tipo:** Requisito não funcional (meta de qualidade proposta para o MVP)

### Descrição verificável
Em pelo menos **95% das medições de cada operação**, o conteúdo principal do **catálogo** deve aparecer em até **3 s**, os resultados de **pesquisa** em até **2 s** e os **detalhes** em até **2,5 s**.

### Critérios de aceitação / verificação
- [ ] Utilizar banco de teste com no mínimo **1.000 produtos**.
- [ ] Simular **20 usuários simultâneos**, conexão de referência de **10 Mbps** e latência de **100 ms**.
- [ ] Executar no mínimo **100 medições por operação**: catálogo, pesquisa e detalhes.
- [ ] Aferir tempo entre a solicitação do usuário e a apresentação visível do conteúdo principal.
- [ ] Confirmar cumprimento de cada limite em pelo menos **95 das 100 medições** por operação; registrar resultados e ambiente.

**Requisitos funcionais relacionados:** RF02, RF04, RF05, RF06, RF07, RF08.

> **Situação:** os parâmetros quantitativos são metas propostas na especificação acadêmica e precisam ser aprovados pela equipe e testados na infraestrutura real. Marcar os critérios apenas após evidência de teste.

[Ver issue #14](https://github.com/ehnb1-creator/OneHub/issues/14)

---

### RNF05 — Disponibilidade da plataforma

**Tipo:** Requisito não funcional (meta de qualidade proposta para o MVP)

### Descrição verificável
O OneHub deve alcançar **disponibilidade mensal mínima de 99,5%** para acesso à aplicação web e consulta ao catálogo.

### Critérios de aceitação / verificação
- [ ] Executar monitoramento automatizado em intervalos de até **1 minuto**.
- [ ] Em cada verificação, confirmar que página inicial e consulta ao catálogo respondem corretamente.
- [ ] Registrar como indisponibilidade a falha de qualquer uma dessas duas verificações.
- [ ] Calcular a disponibilidade mensal como tempo de operação dividido pelo tempo total monitorado; resultado deve ser **≥ 99,5%**.
- [ ] Registrar janelas de manutenção; antes da avaliação, definir e documentar se serão incluídas ou excluídas do cálculo.

**Requisitos funcionais relacionados:** RF02, RF06.

> **Situação:** os parâmetros quantitativos são metas propostas na especificação acadêmica e precisam ser aprovados pela equipe e testados na infraestrutura real. Marcar os critérios apenas após evidência de teste.

[Ver issue #15](https://github.com/ehnb1-creator/OneHub/issues/15)

---

### RNF07 — Acessibilidade

**Tipo:** Requisito não funcional (meta de qualidade proposta para o MVP)

### Descrição verificável
As páginas públicas e os formulários principais do OneHub devem garantir **contraste mínimo de 4,5:1 para texto comum**, navegação por teclado e uso com **zoom de 200%**.

### Critérios de aceitação / verificação
- [ ] Textos normais possuem contraste **≥ 4,5:1** e textos grandes **≥ 3:1**.
- [ ] Cadastro, login, pesquisa e detalhes podem ser operados por **Tab, Shift+Tab e Enter** sem depender de mouse.
- [ ] Todos os elementos interativos têm **foco visual perceptível**.
- [ ] Campos de formulários possuem rótulos identificáveis por leitores de tela.
- [ ] As páginas principais continuam utilizáveis com **zoom de 200%**, sem perda de conteúdo ou de funcionalidades.

**Requisitos funcionais relacionados:** RF01, RF06, RF07, RF08, RF09.

> **Situação:** parâmetros quantitativos propostos; a equipe deve aprovar a meta e verificar se a hospedagem e o plano de serviços contratados permitem cumpri-la antes de considerar o RNF atendido.

[Ver issue #17](https://github.com/ehnb1-creator/OneHub/issues/17)

---

### RNF08 — Compatibilidade entre navegadores

**Tipo:** Requisito não funcional (meta de qualidade proposta para o MVP)

### Descrição verificável
Os fluxos essenciais do OneHub devem funcionar nas **duas versões estáveis mais recentes** de Chrome, Firefox e Edge para desktop, e nas versões selecionadas de Chrome para Android e Safari para iOS.

### Critérios de aceitação / verificação
- [ ] Testar duas versões estáveis mais recentes de **Chrome, Firefox e Edge no desktop**.
- [ ] Testar **Chrome no Android** e **Safari no iOS**, registrando as versões de sistema e navegador utilizadas.
- [ ] Executar cadastro, login, pesquisa, detalhes e contato nos navegadores selecionados.
- [ ] Executar cadastro e edição de produtos nos navegadores desktop.
- [ ] Não devem ocorrer falhas que impeçam concluir os fluxos essenciais; registrar ambiente e resultados.

**Requisitos funcionais relacionados:** RF01, RF02, RF06, RF07, RF08, RF09.

> **Situação:** parâmetros quantitativos propostos; a equipe deve aprovar a meta e verificar se a hospedagem e o plano de serviços contratados permitem cumpri-la antes de considerar o RNF atendido.

[Ver issue #18](https://github.com/ehnb1-creator/OneHub/issues/18)

---

### RNF09 — Armazenamento e otimização de imagens

**Tipo:** Requisito não funcional (meta de qualidade proposta para o MVP)

### Descrição verificável
O envio de imagens de produtos deve aceitar apenas **JPEG, PNG ou WebP**, com tamanho máximo de **5 MB por arquivo**, e o catálogo deve utilizar miniaturas otimizadas de até **200 KB**.

### Critérios de aceitação / verificação
- [ ] Aceitar imagens válidas JPEG, PNG ou WebP com tamanho **≤ 5 MB**.
- [ ] Rejeitar arquivos de outros formatos e arquivos **> 5 MB**, exibindo mensagem específica.
- [ ] Gerar versão de exibição para listagens com tamanho **≤ 200 KB**, mantendo proporção sem distorção.
- [ ] Imagens devem permanecer associadas ao produto e a vendedor autorizado.
- [ ] Verificar comportamento para arquivo inválido, falha de envio e imagem não encontrada.

**Requisitos funcionais relacionados:** RF04, RF05, RF06, RF08.

> **Situação:** parâmetros quantitativos propostos; a equipe deve aprovar a meta e verificar se a hospedagem e o plano de serviços contratados permitem cumpri-la antes de considerar o RNF atendido.

[Ver issue #19](https://github.com/ehnb1-creator/OneHub/issues/19)

---

### RNF10 — Backup e recuperação dos dados

**Tipo:** Requisito não funcional (meta de qualidade proposta para o MVP)

### Descrição verificável
A solução deve executar **backup do banco de dados em intervalos máximos de 24 h**, com **RPO ≤ 24 h** e **RTO ≤ 4 h** para restauração dos dados.

### Critérios de aceitação / verificação
- [ ] Confirmar que o intervalo entre dois backups concluídos não excede **24 horas**.
- [ ] Os backups incluem usuários, lojas, produtos e relacionamentos necessários à restauração consistente.
- [ ] Em teste de desastre controlado, recuperar dados de um ponto com perda máxima de **24 h (RPO)**.
- [ ] Concluir recuperação funcional dos dados em até **4 horas (RTO)** a partir do início do procedimento de restauração.
- [ ] Realizar **um teste de restauração por trimestre** em ambiente separado da produção e conferir relações usuário-loja-produto.
- [ ] Registrar logs de backup, procedimento, data, duração e resultado dos testes.

**Requisitos funcionais relacionados:** RF03, RF04, RF10.

> **Situação:** parâmetros quantitativos propostos; a equipe deve aprovar a meta e verificar se a hospedagem e o plano de serviços contratados permitem cumpri-la antes de considerar o RNF atendido.

[Ver issue #20](https://github.com/ehnb1-creator/OneHub/issues/20)

---

