# Requisitos Não Funcionais — OneHub

## 1. Visão geral

Os Requisitos Não Funcionais (RNF) estabelecem critérios de qualidade, segurança, desempenho e compatibilidade que devem ser considerados no desenvolvimento e na avaliação do OneHub.

## 2. Lista de Requisitos Não Funcionais

| ID | Requisito | Descrição / critério verificável |
|---|---|---|
| RNF01 | Usabilidade | A interface deve apresentar navegação clara, textos compreensíveis e formulários com indicação de campos obrigatórios e erros de preenchimento. |
| RNF02 | Responsividade | As páginas devem adaptar sua apresentação a dispositivos móveis, tablets e computadores, sem perda das funções essenciais. |
| RNF03 | Segurança e controle de acesso | O sistema deve proteger credenciais e restringir operações de gerenciamento aos usuários autorizados, impedindo que um vendedor altere dados de outra loja. |
| RNF04 | Desempenho | As páginas e resultados de pesquisa devem ser apresentados em tempo adequado; como meta de projeto, as operações comuns devem responder em até 3 segundos em condições normais de uso. |
| RNF05 | Compatibilidade | A aplicação web deve funcionar nos navegadores modernos de uso comum e manter suas funções essenciais em diferentes tamanhos de tela. |
| RNF06 | Integridade dos dados | Os dados de usuários, lojas, produtos e favoritos devem manter associações consistentes, evitando registros órfãos e alterações não autorizadas. |

## 3. Observações

- Os requisitos não funcionais devem ser verificados durante a avaliação da solução.
- O limite de até 3 segundos do RNF04 é uma meta de projeto proposta e deve ser validada em condições de teste definidas pelo grupo.
