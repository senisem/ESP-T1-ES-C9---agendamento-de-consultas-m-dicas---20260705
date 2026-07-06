# Estratégias de Resposta aos Riscos

Este documento apresenta uma análise exploratória das possíveis estratégias de resposta (Evitar, Mitigar, Transferir e Aceitar) para os riscos identificados no projeto do Aplicativo Móvel de Agendamento de Consultas Médicas. A análise tem caráter consultivo para apoiar a tomada de decisão.

---

## 1. Estratégias Possíveis por Risco

### Risco 01
* **Risco:** Quebra definitiva ou falha contínua na integração com o Prontuário Eletrônico do Paciente (PEP).
* **Descrição:** A instabilidade atual, decorrente de mudanças recentes no sistema externo e falta de documentação da API, pode evoluir para falhas sistêmicas irrecuperáveis durante a fase de implantação.
* **Estratégias de resposta possíveis:**
    * **i. Evitar:** Alterar a arquitetura do sistema para não depender de sincronização em tempo real (ex: usar um banco de dados intermediário assíncrono) ou trocar o fornecedor do PEP, caso exista viabilidade contratual.
    * **ii. Mitigar:** Desenvolver mecanismos de resiliência no código (como *Circuit Breakers* e rotinas de *fallback* offline), além de alocar temporariamente um desenvolvedor focado exclusivamente em mapear empiricamente os *endpoints* da API não documentada.
    * **iii. Transferir:** Contratar uma consultoria especializada em integrações de saúde para assumir a construção do *middleware*, ou acionar juridicamente/comercialmente o fornecedor do PEP para exigir o cumprimento de um Acordo de Nível de Serviço (SLA).
    * **iv. Aceitar:** Assumir que o agendamento poderá ficar indisponível intermitentemente, configurando mensagens amigáveis de erro para o paciente, caso não haja orçamento ou tempo hábil para reverter a instabilidade técnica.

### Risco 02
* **Risco:** *Scope Creep* (Aumento descontrolado de escopo) no fluxo de agendamento.
* **Descrição:** A adição contínua de novas validações e regras de negócio no fluxo de agendamento pelos stakeholders.
* **Estratégias de resposta possíveis:**
    * **i. Evitar:** Aplicar um congelamento de escopo (*Scope Freeze*), rejeitando formalmente qualquer nova solicitação de requisito e garantindo a entrega da *baseline* original.
    * **ii. Mitigar:** Estabelecer um Comitê de Controle de Mudanças (CCB) rigoroso e adotar a prática de troca (*trade-off*): para cada nova regra adicionada, um requisito de menor prioridade é retirado da release atual.
    * **iii. Transferir:** Transferir a responsabilidade da priorização e do impacto no prazo para um Comitê Executivo (Sponsors), obrigando-os a assinar a aprovação do atraso cronológico em troca das novas features.
    * **iv. Aceitar:** Acolher todas as mudanças solicitadas sem aplicar filtros, assumindo publicamente o impacto de extensão no cronograma e o aumento do custo do projeto.

### Risco 03
* **Risco:** Gargalo operacional na etapa de Qualidade e Testes (QA).
* **Descrição:** Sobrecarga de trabalho sobre o único tester da equipe para validar integrações instáveis e novas regras de negócio.
* **Estratégias de resposta possíveis:**
    * **i. Evitar:** Interromper temporariamente o desenvolvimento de novas funcionalidades (*Code Freeze*) até que o profissional de QA consiga zerar a fila de testes acumulados.
    * **ii. Mitigar:** Implementar a prática de *Shift-Left Testing*, obrigando os 4 desenvolvedores a criarem testes unitários e de integração automatizados mais robustos antes de passar a demanda para o QA.
    * **iii. Transferir:** Terceirizar parte da demanda de testes para uma fábrica de software especializada ou contratar profissionais de QA *freelancers* sob demanda (Staff Augmentation).
    * **iv. Aceitar:** Aceitar que a cobertura de testes será superficial, assumindo o risco técnico de que *bugs* críticos possam vazar para o ambiente de produção.

### Risco 04
* **Risco:** Queda de produtividade e esgotamento (*burnout*) da equipe de desenvolvimento.
* **Descrição:** Queda do rendimento individual e coletivo devido à pressão por prazos apertados, retrabalho de escopo e dificuldades técnicas contínuas com a integração do PEP.
* **Estratégias de resposta possíveis:**
    * **i. Evitar:** Repactuar agressivamente o prazo final de entrega com os stakeholders, estendendo o cronograma para níveis realistas e removendo a pressão imediata.
    * **ii. Mitigar:** Proibir horas extras, promover rodízio das tarefas mais estressantes (ex: lidar com a API do PEP) entre os desenvolvedores, e realizar dinâmicas de descompressão.
    * **iii. Transferir:** Expandir a equipe contratando mais desenvolvedores temporários para diluir a carga de trabalho do time principal.
    * **iv. Aceitar:** Não intervir na dinâmica de trabalho, aceitando a alta probabilidade de absenteísmo, queda de qualidade no código ou perda de membros da equipe, criando apenas um plano de sucessão de emergência.

### Risco 05
* **Risco:** Desalinhamento técnico devido a falhas de comunicação e coordenação na equipe distribuída.
* **Descrição:** Perda de informações críticas ou decisões desalinhadas em virtude do trabalho remoto e da volatilidade dos requisitos.
* **Estratégias de resposta possíveis:**
    * **i. Evitar:** Consolidar a equipe em um ambiente presencial ou estabelecer blocos de horário fixos obrigatórios em que todos devem estar em chamadas de vídeo abertas.
    * **ii. Mitigar:** Reforçar os ritos ágeis (Dailies rigorosas), exigir documentação assíncrona detalhada (ADRs - *Architecture Decision Records*) e instituir sessões de *Pair Programming* para tarefas complexas.
    * **iii. Transferir:** Alocar um Scrum Master dedicado (externo à equipe de dev) exclusivamente para rastrear bloqueios e facilitar o fluxo de comunicação entre os membros.
    * **iv. Aceitar:** Considerar as falhas de comunicação como inerentes ao modelo remoto e aceitar uma margem calculada de retrabalho no planejamento das Sprints.

---

## 2. Considerações sobre aplicação das estratégias

* **Situações de adequação:** 
  * Estratégias de **Evitar** são recomendadas para riscos que ameaçam a viabilidade do produto como um todo (como repensar a arquitetura para o Risco 01). 
  * A **Mitigação** é a abordagem padrão mais equilibrada em contextos ágeis (como testes automatizados para o Risco 03 e *trade-off* de escopo para o Risco 02). 
  * A **Transferência** é ideal quando falta especialidade interna ou capacidade braçal, mas exige injeção de capital. 
  * A **Aceitação** só deve ser adotada quando o custo da ação for maior que o impacto da ocorrência ou quando os stakeholders rejeitarem todas as outras alternativas.

* **Limitações e Trade-offs:**
  * **Evitar:** Frequentemente inviabiliza requisitos de negócio centrais ou reduz drasticamente o valor inicial do produto.
  * **Mitigar:** Consome esforço da própria equipe (ex: escrever mais testes atrasa o desenvolvimento de *features* em um primeiro momento).
  * **Transferir:** Aumenta os custos do projeto e cria novas dependências de fornecedores externos.
  * **Aceitar:** Coloca em risco a reputação do software e pode resultar em falha completa da adoção pelos usuários.

---

## 3. Observações gerais

* **Dependência de contexto adicional:** As sugestões acima são exploratórias. A escolha definitiva dependerá de informações orçamentárias (existe verba para contratar terceiros?), contratuais (qual o SLA do PEP?) e técnicas (qual a flexibilidade da arquitetura atual?).
* **Pontos que exigem validação com stakeholders:** Nenhuma estratégia de repactuação de prazo, aumento de orçamento ou congelamento de escopo pode ser executada unilateralmente pelo Gerente de Projetos. É mandatório realizar uma reunião de crise com os patrocinadores para validar limites de flexibilidade antes da decisão final.
