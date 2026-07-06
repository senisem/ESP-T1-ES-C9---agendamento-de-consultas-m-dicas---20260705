# Identificação de Riscos

Abaixo estão listados os riscos identificados para o projeto do Aplicativo Móvel de Agendamento de Consultas Médicas, estruturados com base no cenário de desenvolvimento intermediário, na configuração da equipe e nos desafios mapeados.

---

## 1. Lista de Riscos Identificados

### Risco 01
* **Risco:** Quebra definitiva ou falha contínua na integração com o Prontuário Eletrônico do Paciente (PEP).
* **Descrição:** A falta de documentação da API externa e as mudanças recentes sem aviso prévio por parte do fornecedor tornam a integração altamente instável, podendo impossibilitar a funcionalidade crítica de agendamento e sincronização de dados clínicos.
* **Contexto de ocorrência:** Durante os testes de integração, chamadas reais da aplicação para a API do sistema externo ou quando o fornecedor terceiro realizar novas atualizações em seu sistema legados.
* **Nota de Incerteza/Validação:** É incerto o nível de acesso e o canal de comunicação que nossa equipe possui com os desenvolvedores do sistema externo. É necessário validar se existe um Acordo de Nível de Serviço (SLA) estabelecido com o fornecedor para suportar essa integração crítica.

### Risco 02
* **Risco:** *Scope Creep* (Aumento descontrolado de escopo) no fluxo de agendamento.
* **Descrição:** A solicitação de novas validações e regras de negócio por parte dos stakeholders em uma fase intermediária, combinada com a natureza evolutiva dos requisitos, pode inviabilizar o cronograma e o orçamento originais.
* **Contexto de ocorrência:** Ao tentar incorporar os novos requisitos no código já desenvolvido, o que exigirá refatoração de funcionalidades que já estavam prontas ou em andamento.

### Risco 03
* **Risco:** Gargalo operacional na etapa de Qualidade e Testes (QA).
* **Descrição:** A proporção estrutural de 4 desenvolvedores para apenas 1 tester, somada à instabilidade da integração e à introdução de novas regras de negócio complexas, pode sobrecarregar o profissional de QA, comprometendo a qualidade da entrega ou travando a esteira de liberação (*release*).
* **Contexto de ocorrência:** Na fase de homologação das novas regras do fluxo de agendamento e, de forma contínua, durante os testes de regressão necessários após cada mudança ou quebra na integração com o PEP.

### Risco 04
* **Risco:** Queda de produtividade e esgotamento (*burnout*) da equipe de desenvolvimento.
* **Descrição:** A equipe já reportou aumento da carga de trabalho e dificuldades para cumprir os prazos iniciais. A pressão para absorver mudanças de escopo e lidar com o retrabalho gerado por uma API externa não documentada agravará drasticamente a sobrecarga.
* **Contexto de ocorrência:** Ao longo das próximas semanas de desenvolvimento, caso as expectativas dos stakeholders não sejam realinhadas e os prazos não sejam ajustados para refletir as novas complexidades.

### Risco 05
* **Risco:** Desalinhamento técnico devido a falhas de comunicação e coordenação.
* **Descrição:** Sendo uma equipe distribuída lidando com requisitos voláteis, há um risco elevado de perda de informações, atrasos na resolução de bloqueios técnicos e desenvolvedores atuando com premissas desatualizadas.
* **Contexto de ocorrência:** Durante a passagem de bastão (*handoff*) entre os desenvolvedores e o tester, no momento de interpretar as novas solicitações dos stakeholders ou na tentativa de debugar problemas complexos de integração remotamente.
* **Nota de Incerteza/Validação:** Como não foram detalhados os processos de trabalho remoto da equipe, há incerteza sobre quais ferramentas e ritos ágeis (ex: *Dailies*, documentação assíncrona) estão sendo efetivamente utilizados. Necessita-se validar a maturidade do processo de comunicação da equipe distribuída.