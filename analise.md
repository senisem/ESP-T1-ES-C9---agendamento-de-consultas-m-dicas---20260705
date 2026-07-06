# Análise dos Riscos

Este documento apresenta a análise qualitativa detalhada dos riscos identificados na etapa anterior para o projeto do Aplicativo Móvel de Agendamento de Consultas Médicas.

---

## 1. Análise Estruturada dos Riscos

### Risco 01
* **Risco:** Quebra definitiva ou falha contínua na integração com o Prontuário Eletrônico do Paciente (PEP).
* **Descrição:** A instabilidade atual, decorrente de mudanças recentes no sistema externo e falta de documentação da API, pode evoluir para falhas sistêmicas irrecuperáveis durante a fase de implantação.
* **Possíveis impactos no projeto:** Impacto severo no **prazo** (tempo gasto em engenharia reversa e debugging), **esforço** (desvio de foco da equipe) e **qualidade** (produto principal incapacitado de funcionar).
* **Fatores que influenciam a ocorrência:** Ausência de documentação da API do fornecedor; falta de aviso prévio sobre atualizações no sistema externo; natureza crítica desta integração para o sucesso do projeto.
* **Probabilidade:** Alta
* **Impacto:** Alto
* **Justificativa da classificação:** A probabilidade é Alta pois a instabilidade já está ocorrendo e não há controle sobre o sistema terceiro. O impacto é Alto porque a integração é expressamente definida como crítica para a entrega do projeto.

### Risco 02
* **Risco:** *Scope Creep* (Aumento descontrolado de escopo) no fluxo de agendamento.
* **Descrição:** A adição contínua de novas validações e regras de negócio no fluxo de agendamento pelos stakeholders.
* **Possíveis impactos no projeto:** Extensão do **prazo** final de entrega e aumento do **esforço** de desenvolvimento, exigindo refatoração de código de funcionalidades (como a interface base) que já estavam pré-aprovadas.
* **Fatores que influenciam a ocorrência:** Requisitos ainda em evolução; stakeholders ativos solicitando mudanças na fase intermediária; falta de um comitê rígido de controle de mudanças (Change Control Board).
* **Probabilidade:** Alta
* **Impacto:** Médio
* **Justificativa da classificação:** A probabilidade é Alta dado que as solicitações de alteração já foram formalizadas e o escopo é inerentemente volátil. O impacto é Médio porque afeta o esforço e o prazo, mas não bloqueia tecnologicamente o andamento da arquitetura central como o Risco 01.

### Risco 03
* **Risco:** Gargalo operacional na etapa de Qualidade e Testes (QA).
* **Descrição:** Sobrecarga de trabalho sobre o único tester da equipe para validar integrações instáveis e novas regras de negócio.
* **Possíveis impactos no projeto:** Queda drástica na **qualidade** da entrega final (bugs vazando para produção) e gargalo severo na **coordenação** das releases, retardando o cronograma.
* **Fatores que influenciam a ocorrência:** Proporção estrutural desbalanceada (4 desenvolvedores produzindo código para 1 QA testar); complexidade acrescida pelas novas validações de negócio solicitadas.
* **Probabilidade:** Alta
* **Impacto:** Alto
* **Justificativa da classificação:** A probabilidade é Alta devido à sobrecarga matemática (4:1) sob o contexto de instabilidade e retrabalho. O impacto é Alto porque o teste rigoroso em um sistema de saúde lida com dados sensíveis e marcações críticas de pacientes.

### Risco 04
* **Risco:** Queda de produtividade e esgotamento (*burnout*) da equipe de desenvolvimento.
* **Descrição:** Queda do rendimento individual e coletivo devido à pressão por prazos apertados, retrabalho de escopo e dificuldades técnicas contínuas com a integração do PEP.
* **Possíveis impactos no projeto:** Redução imediata no **esforço** produtivo, aumento de erros lógicos de codificação, e possível perda de capital intelectual (afastamento de membros).
* **Fatores que influenciam a ocorrência:** Aumento da carga de trabalho já reportada; dificuldade de cumprir os prazos iniciais; estresse gerado por dependências técnicas mal documentadas.
* **Probabilidade:** Alta
* **Impacto:** Alto
* **Justificativa da classificação:** A equipe já relatou dificuldades com prazos e carga de trabalho, tornando a ocorrência iminente (Alta). O impacto é Alto pois a equipe de desenvolvimento é enxuta (4 membros) e a falha de qualquer componente paralisa o cronograma.

### Risco 05
* **Risco:** Desalinhamento técnico devido a falhas de comunicação e coordenação na equipe distribuída.
* **Descrição:** Perda de informações críticas ou decisões desalinhadas em virtude do trabalho remoto e da volatilidade dos requisitos.
* **Possíveis impactos no projeto:** Impacto no **esforço** (retrabalho por falta de entendimento correto das regras de negócio) e na **coordenação** (dificuldade de sincronizar integrações entre os módulos de back-end e front-end).
* **Fatores que influenciam a ocorrência:** Natureza distribuída da equipe; fluxo constante de novas alterações vindas dos stakeholders.
* **Probabilidade:** Média
* **Impacto:** Médio
* **Justificativa da classificação:** Embora seja um risco sempre presente em times distribuídos, é classificado com incerteza na probabilidade (Média), assumindo-se que metodologias ágeis (Scrum) estejam parcialmente mitigando isso. O impacto é Médio, resultando em retrabalho local e atrasos contornáveis se detectados a tempo.

---

## 2. Matriz Qualitativa de Riscos

| Probabilidade\Impacto | Baixo | Médio      | Alto                           |
| --------------------- | ----- | ---------- | ------------------------------ |
| **Alta**              |       | Risco 02   | Risco 01, Risco 03, Risco 04   |
| **Média**             |       | Risco 05   |                                |
| **Baixa**             |       |            |                                |