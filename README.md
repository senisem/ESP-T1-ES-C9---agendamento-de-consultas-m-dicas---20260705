# Projeto: Aplicativo Móvel de Agendamento de Consultas Médicas

Este repositório contém a documentação estratégica e o mapeamento de gerenciamento de riscos do projeto de desenvolvimento do **Aplicativo Móvel para Agendamento de Consultas Médicas**. Este projeto é parte integrante das atividades práticas da Pós-Graduação em Engenharia de Software com ênfase em Automação e Inovação com Inteligência Artificial Generativa.

---

## 1. Visão Geral do Projeto

O objetivo principal deste projeto é conceber, desenhar e implementar uma solução mobile multiplataforma que centralize e otimize a jornada do paciente e do médico no agendamento de consultas e gerenciamento de horários. A solução foca na desburocratização de processos clínicos e na garantia de sincronia de dados em tempo real com sistemas legados de saúde.

### 1.1 Funcionalidades Principais (Módulos do Sistema)
* **Módulo de Autenticação e Perfis (Cadastro de Usuários):** Controle de acessos seguro para Pacientes, Médicos e Administradores da Clínica, contemplando LGPD e criptografia de dados sensíveis.
* **Gestão de Agenda Médica:** Painel dinâmico para os profissionais de saúde configurarem seus horários de atendimento, bloqueios por férias, plantões e tempos de consulta customizados.
* **Agendamento de Consultas:** Fluxo intuitivo e em poucas etapas para o paciente selecionar especialidade, médico, localidade e horário, com validações de conflitos em tempo real.
* **Módulo de Notificações:** Sistema push notification e SMS para confirmação de consultas, lembretes de véspera e avisos de alterações na agenda, visando reduzir a taxa de absenteísmo.
* **Integração com Prontuário Eletrônico do Paciente (PEP):** Sincronização automatizada e crítica com um sistema externo para verificação de histórico clínico e elegibilidade no momento do agendamento.

---

## 2. Estrutura da Equipe de Engenharia

O projeto conta com uma estrutura enxuta operando sob metodologias ágeis (Scrum adaptado):

* **1 Gerente de Projetos (PM):** Responsável pela governança, escopo, gestão de riscos e interface com stakeholders.
* **4 Desenvolvedores de Software:** Focados na implementação das camadas front-end mobile, back-end (APIs) e esteiras de CI/CD.
* **1 Engenheiro de Qualidade / Tester (QA):** Responsável por testes automatizados, testes de integração, regressão e validação de critérios de aceitação.

---

## 3. Estado Atual e Desafios Críticos

O projeto encontra-se atualmente em sua **fase intermediária de desenvolvimento**. Os módulos de autenticação e a interface base do agendamento foram validados com sucesso. No entanto, o cronograma e a estabilidade da entrega enfrentam os seguintes desafios estratégicos:

1.  **Instabilidade Crítica na Integração (PEP):** A conexão com o sistema externo de prontuário apresentou quebras devido à escassez de documentação clara de API e alterações repentinas sem aviso prévio por parte do fornecedor terceirizado.
2.  **Volatilidade de Escopo (Solicitações de Stakeholders):** Demanda recente de novas regras de negócio e validações complexas dentro do fluxo de agendamento que não estavam mapeadas na baseline inicial.
3.  **Capacidade de Entrega da Equipe (Burnout/Prazo):** Alocação e carga de trabalho elevadas, resultando em desvios entre as estimativas iniciais de esforço e o tempo real de execução das tarefas.

---

## 4. Governança e Arquitetura da Informação (Repositório)

Para mitigar os desafios citados e garantir o alinhamento acadêmico e profissional, este repositório organiza a documentação de gestão de riscos de forma modularizada, utilizando arquivos Markdown (`.md`) interconectados.

A estrutura de pastas e arquivos segue estritamente a arquitetura abaixo:

projeto-agendamento-consultas/
├── README.md                           # Visão geral do projeto e contexto estratégico (Este arquivo)
├── riscos/
│   ├── identificacao.md                # Listagem detalhada dos riscos mapeados e gatilhos
│   ├── analise.md                      # Avaliação de matriz de impacto, probabilidade e criticidade
│   └── respostas.md                    # Planos de contingência, mitigação e aceitação com justificativas
└── comunicacao/
    └── status-stakeholders.md          # Relatório executivo de status e alinhamento de expectativas