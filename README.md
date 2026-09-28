#Hold Fit - Sistema de Gestão Empresarial (ERP)

Sistema Integrado de Gestão Empresarial (ERP) desenvolvido para a **Hold Fit Atividades de Condicionamento Físico LTDA**. O projeto centraliza a operação, o gerenciamento de acesso de alunos e professores, e a administração financeira da empresa.

---

## Sumário

- [1. Visão Geral da Empresa](#1-visão-geral-da-empresa)
- [2. Justificativa do Projeto](#2-justificativa-do-projeto)
- [3. Processos de Negócio](#3-processos-de-negócio)
- [4. Problemas e Necessidades](#4-problemas-e-necessidades)
- [5. Requisitos e Regras de Negócio](#5-requisitos-e-regras-de-negócio)
  - [5.1 Requisitos Funcionais (RF)](#51-requisitos-funcionais-rf)
  - [5.2 Regras de Negócio (RN)](#52-regras-de-negócio-rn)
- [6. Restrições e Políticas Organizacionais](#6-restrições-e-políticas-organizacionais)
- [7. Fluxogramas dos Processos](#7-fluxogramas-dos-processos)
- [8. Modelagem de Dados](#8-modelagem-de-dados)
  - [8.1 Entidades e Atributos](#81-entidades-e-atributos)
  - [8.2 Relacionamentos e Cardinalidade](#82-relacionamentos-e-cardinalidade)

---

## 1. Visão Geral da Empresa

| Parâmetro | Detalhe |
| :--- | :--- |
| **Razão Social** | Hold Fit Atividades de Condicionamento Físico LTDA |
| **Data de Abertura** | 10/02/2023 |
| **Localização** | Zona Leste |
| **Público-Alvo** | Jovens (16-18 anos), Adultos (20-40 anos) e Terceira Idade |

Por se tratar de uma academia de bairro em expansão, a Hold Fit operava por meio de processos manuais, planilhas descentralizadas e comunicação informal. O objetivo deste sistema é automatizar e centralizar os controles operacionais e financeiros.

---

## 2. Justificativa do Projeto

A implementação deste sistema ERP justifica-se pela necessidade de:
1. **Centralização de Dados:** Integração do cadastro de usuários que desempenham múltiplos papéis (ex.: professor que também é aluno).
2. **Automação Financeira e de Acesso:** Vinculação do status de pagamento com a liberação de catracas/portas.
3. **Validação Profissional:** Verificação rígida de registro profissional (CREF) e indicação de Responsável Técnico (RT).
4. **Eficiência Operacional:** Gestão unificada de faturamento, contas a pagar, controle de manutenção e turmas.

---

## 3. Processos de Negócio

### 0.3.1 Cadastro e Matrícula de Aluno
* **Atores:** Pessoa (Aluno) e Sistema.
* **Gatilho:** Pessoa procura a academia para matrícula.
* **Fluxo:** Cadastro de dados pessoais e vinculação a planos e turmas.
* **Resultado:** Aluno cadastrado e apto a utilizar a academia.

### 3.2 Contratação e Alocação de Funcionário
* **Atores:** Gestão e Funcionário.
* **Gatilho:** Necessidade de preenchimento de vaga.
* **Fluxo:** Validação de documentos, vinculação a cargo/departamento e concessão de credenciais.
* **Resultado:** Funcionário integrado e operacional no sistema.

### 3.3 Gestão de Turmas e Aulas (Corpo Técnico)
* **Atores:** Professor (Mentor), Alunos e Operacional.
* **Gatilho:** Validação do CREF e definição da grade horária.
* **Fluxo:** Abertura da turma, alocação do professor e inclusão dos alunos.
* **Resultado:** Turmas estruturadas sob supervisão técnica.

### 3.4 Contas a Pagar (Despesas e Maquinário)
* **Atores:** Setor Financeiro e Fornecedores.
* **Gatilho:** Aquisição de equipamentos, manutenções ou contas operacionais.
* **Fluxo:** Lançamento de obrigações, validação de recebimento e pagamento.
* **Resultado:** Fornecedores quitados e equipamentos mantidos em operação.

### 3.5 Contas a Receber (Mensalidades)
* **Atores:** Aluno e Setor Financeiro.
* **Gatilho:** Vencimento de plano ou mensalidade.
* **Fluxo:** Pagamento e baixa financeira do título no sistema.
* **Resultado:** Receita confirmada e liberação de acesso na catraca.

---

## 4. Problemas e Necessidades

| Problema Mapeado | Consequência Negativa |
| :--- | :--- |
| **Cadastro em múltiplas planilhas** | Divergência de dados, perda de histórico e alto retrabalho. |
| **Preenchimento manual sem validação** | Erros cadastrais e riscos legais (ex.: ausência de CREF). |
| **Dispersão de dados financeiros** | Cobranças indevidas, alunos inadimplentes com acesso livre e pagantes bloqueados. |
| **Falta de categorização de despesas** | Perda do controle de manutenção preventiva e pagamentos em duplicidade. |
| **Desconexão Financeiro $\rightarrow$ Catraca** | Incapacidade de bloqueio automático por atrasos ou desligamento. |
| **Dificuldade de múltiplos papéis** | Cadastros duplicados quando o professor também é aluno. |

---

## 5. Requisitos e Regras de Negócio

### 5.1 Requisitos Funcionais (RF)
- **RF01 - Gestão de Usuários e Pessoas:** Permitir cadastro único de pessoas com múltiplos papéis.
- **RF02 - Gestão de Planos e Matrículas:** Inscrição, alteração e cancelamento de planos.
- **RF03 - Gestão de Turmas e Grade:** Cadastro de modalidades, horários, alocação de instrutores e turmas.
- **RF04 - Controle de Acesso:** Validação em tempo real para liberação na entrada.
- **RF05 - Contas a Receber:** Registro de pagamentos e previsões de lançamentos futuros.
- **RF06 - Contas a Pagar e Fornecedores:** Cadastro de fornecedores de insumos e manutenção.
- **RF07 - Alertas de Manutenção Preventiva:** Notificação sobre cronogramas de revisão de equipamentos.
- **RF08 - Relatórios Financeiros:** Painel geral de saldo, faturamento e inadimplência.
- **RF09 - Notificação de Cobrança:** Disparo de avisos aos alunos inadimplentes via canal cadastrado.

### 5.2 Regras de Negócio (RN)
- **RN01 - Documento Obrigatório:** Exigência de CPF ou RNM válido no cadastro.
- **RN02 - Validação de CREF:** Cadastro de professores exige validação do CREF e categoria (`G` - Graduado, `P` - Provisionado, `AE` - Atividade Específica).
- **RN03 - Responsável Técnico:** Obrigatoriedade de pelo menos um professor ativo indicado como RT.
- **RN04 - Registro Institucional:** A empresa deve manter seu CREF ativo cadastrado no sistema.
- **RN05 - Bloqueio Diário de Acesso:** Em caso de inadimplência ou demissão, o acesso é suspenso no mesmo dia até as 23:59.
- **RN06 - Restrição a Diárias:** Bloqueio de venda de diárias para usuários com débitos em aberto.
- **RN07 - Tabela Base de Planos:**
  - **Diário:** Cobrança avulsa fixada.
  - **Mensal:** R\$ 110,00/mês.
  - **Trimestral:** R\$ 104,50/mês (5% desc. base + 2% adiantamento).
  - **Anual:** R\$ 99,00/mês (10% desc. base + 4% adiantamento).
- **RN08 - Vínculo Funcional:** Funcionários devem obrigatoriamente ter cargo e departamento.
- **RN09 - Manutenção de Período Pago:** Cancelamentos interrompem cobranças futuras sem revogar o período vigente já quitado.
- **RN10 - Acesso Restrito à Agenda:** Visibilidade de ajuste da grade restrita a *Professores* e *Administradores*.

### 5.3 Requisito não Funcional (RNF)
- **RNF01 - Restrição de funcionalidade:** O sistema deverá restringir o acesso às funcionalidades conforme o perfil de usuário, como administrador, professor e demais perfis autorizados.
- **RNF02 - Proteção aos Dados:** Os dados pessoais tratados pelo sistema deverão possuir mecanismos de proteção e controle de acesso compatíveis com a LGPD.
- **RNF03 - Liberação de Catraca:** A operação de liberação da catraca deverá apresentar tempo de resposta inferior a 1 segundo em condições normais de operação.
- **RNF04 - Histórico das Operações:** O sistema deverá manter histórico/auditoria das operações financeiras relevantes, incluindo cancelamentos e estornos.
- **RNF05 - Chaves Estrangeiras:** As tabelas relacionadas do banco de dados deverão utilizar chaves estrangeiras com regras explícitas de atualização e deleção, evitando exclusões acidentais.
- **RNF06 - Autenticação para Acesso:** O sistema deverá exigir autenticação para acesso às funcionalidades restritas.
- **RNF07 - Proteção de Credenciais:** O sistema deverá proteger credenciais de acesso, armazenando-as de forma segura e não em texto puro.
- **RNF08 - Cópias de Segurança:** O sistema deverá realizar cópias de segurança periódicas dos dados, com procedimento definido de restauração.
- **RNF09 - Preservação da Integridade dos Dados:** O sistema deverá preservar a integridade e consistência dos dados durante operações de cadastro, alteração, pagamento e cancelamento.
- **RNF10 - Mensagens de Erro:** O sistema deverá disponibilizar mensagens claras de erro e confirmação para operações realizadas pelos usuários.
- **RNF11 - Manutenção do Banco de Dados:** O sistema deverá permitir manutenção do banco de dados sem comprometer a integridade dos registros existentes.
- **RNF12 - Acesso de Informações:** As informações financeiras e pessoais deverão ser acessíveis somente a usuários com autorização compatível com sua função.

---

## 6. Restrições e Políticas Organizacionais

1. **Controle de Acesso e Permissões:**
   - Apenas perfis `Administrador` ou `Gestor` alteram níveis de acesso ou registram demissões.
   - Alunos possuem apenas permissão de consulta às suas turmas ativas.
2. **Políticas Financeiras:**
   - Descontos padrão sobre plano base de R\$ 120,00: *Mensal (0%)*, *Trimestral (10%)*, *Anual (20%)*.
   - Qualquer concessão fora da tabela requer aprovação expressa da administração.
3. **Inadimplência:**
   - Suspensão imediata de acessos e restrição de compras avulsas até regularização financeira.
4. **Regulamentações:**
   - Trava sistêmica que impede a criação de registros duplicate de CPF/RNM.

---

## 7. Modelagem de Dados

### 7.1 Entidades e Atributos

| Entidade | Tipo | PK / FK | Atributos |
| :--- | :--- | :--- | :--- |
| **EMPRESA** | Forte | `cnpj` (PK) | `endereco`, `nome_fantasia`, `horario_ab`, `horario_fc`, `telefone`, `email` |
| **PESSOA** | Forte | `cpf` (PK) | `nome`, `dt_nasci`, `endereco`, `telefone`, `email`, `genero` |
| **ALUNO** | Fraca | `rgm` (PK), `cpf` (FK) | `cod_matricula`, `data_in`, `data_f`, `status_al` |
| **FUNCIONARIO** | Fraca | `funcionario_id` (PK), `cpf` (FK) | `funcao`, `salario`, `carga_h`, `h_entrada`, `h_saida` |
| **PROFESSOR** | Fraca | `cref` (PK), `funcionario_id` (FK) | `categoria_cref`, `is_responsavel_tecnico` |
| **DEPENDENTE** | Fraca | `funcionario_id` (FK) | `parentesco` |
| **MODALIDADE** | Forte | `modalidade_id` (PK) | `nome`, `descricao`, `capacidade`, `status`, `duracao` |
| **TURMA** | Associativa | `modalidade_id` (FK), `rgm` (FK) | `horario_i`, `horario_f`, `data` |
| **FORNECEDOR** | Fraca | `cpf` / `cnpj` (PK) | `razao_social` |
| **DEPARTAMENTO**| Fraca | `n_id` (PK) | `nome`, `descricao` |
| **DESPESAS** | Fraca | `produto_id` (PK) | `nome`, `descricao`, `validade`, `preco`, `quantidade` |
| **MAQUINARIO** | Fraca | `maquinario_id` (PK)| `nome`, `descricao`, `preco`, `estoque` |
| **CONTA** | Fraca | `num_conta` (PK) | `saldo`, `qnt_pendente`, `qnt_pago` |
| **CONTAS A PAGAR**| Fraca | `pagamento_id` (PK) | `dt_pagamento`, `dt_vencimento`, `tipo` |
| **CONTAS A RECEBER**| Fraca | `recebimento_id` (PK)| `dt_pagamento`, `dt_vencimento`, `tipo` |
| **PLANOS** | Associativa | `rgm` (FK), `modalidade_id` (FK) | `dt_i`, `dt_f`, `valor`, `nome`, `descricao`, `desconto` |

### 7.2 Relacionamentos e Cardinalidade

```
[EMPRESA] -------- (1:N) --------> [CONTAS]
[EMPRESA] -------- (1:N) --------> [PESSOA]
[CONTAS] --------- (1:N) --------> [CONTAS A PAGAR]
[CONTAS] --------- (1:N) --------> [CONTAS A RECEBER]
[CONTAS A PAGAR] - (N:N) --------> [PAGAMENTO]
[CONTAS A RECEBER] (N:N) --------> [PAGAMENTO]
[ALUNO] ---------- (1:N) --------> [PAGAMENTO]
[PAGAMENTO] ------ (1:N) --------> [DESPESAS]
[PAGAMENTO] ------ (1:N) --------> [MAQUINARIO]
[PESSOA] --------- (1:1) --------> [ALUNO]
[PESSOA] --------- (1:1) --------> [RESPONSÁVEL]
[PESSOA] --------- (1:N) --------> [DEPENDENTE]
[ALUNO] ---------- (1:1) --------> [RESPONSÁVEL]
[ALUNO] ---------- (N:N) --------> [MODALIDADE] (via PLANO)
[FUNCIONARIO] ---- (1:1) --------> [PROFESSOR]
[FUNCIONARIO] ---- (1:N) --------> [DEPENDENTE]
[FUNCIONARIO] ---- (1:N) --------> [CARGO]
[PROFESSOR] ------ (N:N) --------> [ALUNO] (via TURMA)
```
