## Proyecto ERP - Hold Fit

Sistema Integrado de Gestão Empresarial (ERP) desenvolvido para a **Hold Fit Atividades de Condicionamento Físico LTDA**. O projeto centraliza a operação, o gerenciamento de acesso de alunos e professores, e a administração financeira da empresa.

(Trabalho feito com fins de estudo e pesquisa para a entrega do trabalho semestral da disciplina banco de dados, lecionada pelo professor Clovis Jose Ramos Ferraro)



---

## Sumário

- [1. Identificação da Equipe](#1-identificação-da-equipe)
- [2. Caracterização da Empresa](#2-caracterização-da-empresa)
- [3. Justificativa da Escolha do Negócio](#3-justificativa-da-escolha-do-negócio)
- [4. Problemas e Necessidades Identificados](#4-problemas-e-necessidades-identificados)
- [5. Processos de Negócio](#5-processos-de-negócio)
- [6. Requisitos Funcionais (RF)](#6-requisitos-funcionais-rf)
- [7. Requisitos Não Funcionais (RNF)](#7-requisitos-não-funcionais-rnf)
- [8. Regras de Negócio e Operacionais (RN)](#8-regras-de-negócio-e-operacionais-rn)
- [9. Restrições e Políticas Organizacionais](#9-restrições-e-políticas-organizacionais)
- [10. Entidades e Atributos](#10-entidades-e-atributos)
- [11. Relacionamentos e Cardinalidades](#11-relacionamentos-e-cardinalidades)
- [12. Justificativas Técnicas das Decisões](#12-justificativas-técnicas-das-decisões)
- [13. Conclusão](#13-conclusão)

---
## 1. Identificação da Equipe

| Nome Completo | RGM |
| :--- | :--- |
| Lucas de Oliveira | 50040731 |
| Clara Costa Gonçalves | 50038303 |
| Kaio da Silva Oliveira | 48926086 |
| Vinicius do Nascimento Silva | 49787098 |
| Alefe Richard Silva | 49884816 |
| João Victor de Almeida Ferreira | 049704524 |
| Ayssa Baestero dos Santos | 49030230 |
| Nicolas Silva Marcos | 49175564 |
| Jesus David Casanova Molano | 49410091 |

## 2. Caracterização da empresa

A empresa escolhida e então criada é a **Hold Fit Atividades de Condicionamento Físico LTDA**, uma academia pequena com intenção de crescimento, foi aberta em 10/02/2023 sendo sediada na Zona Leste. 

Por ser uma academia de bairro, se encontra em uma situação de gestão antiga e complicada. Fazendo uso de planilhas, documentos espalhados e decisões apenas pelo diálogo, a Hold Fit decidiu dar o próximo passo e montar um sistema para gerenciar toda a empresa, focando na eficiência de controle dos alunos e professores, além de dar suporte a questões financeiras.

Tem como principais clientes atuais adultos de 20 a 40 anos, porém dispõe, também, de jovens entre 16 e 18 anos, além de senhores que buscam atividades mais leves e com menos exigência física.

Para gerenciar todos estes aspectos, a empresa tem como principais setores os professores, que são responsáveis por dar aulas e ajudar os frequentantes, e os fornecedores, dos quais existem dois tipos: aqueles que fornecem as máquinas, equipamentos e todos os produtos necessários, e os que fornecem serviço de manutenção às máquinas e equipamentos.

Além dos setores citados acima que são responsáveis pela garantia do serviço prestado na academia, possuímos também toda a parte financeira (pagamentos a receber, a efetuar e a conta onde o controle geral é feito).

É importante, dentro da empresa, a possibilidade de professores serem alunos; seja ele aluno, professor ou funcionário, todos devem ter cadastros no sistema, mudando apenas as formas de acesso. A academia, enquanto estabelecimento, deve possuir um CREF cadastrado no sistema.

---

## 3. Justificativa da Escolha do Negócio

A Hold Fit foi escolhida para o projeto pois foi identificado falhas na estrutura da empresa e em sua gestão de informações, o que é ideal para o desenvolvimento de um sistema.

Primeiramente, a empresa possui processos organizados e válidos que devem ser analisados para um sistema funcional, como, por exemplo, a gestão de frequência de alunos e a verificação de credenciais técnicas (CREF) de professores, entre outros.

Segundamente, é importante ressaltar a existência clara da necessidade de integração, pois é preciso conectar o setor financeiro com o controle de acesso diário, além de unificar o cadastro de usuários que podem atuar simultaneamente como professores e alunos.

Em resumo, este cenário justifica perfeitamente a aplicação de um sistema ERP, tornando a Hold Fit um estudo de caso altamente adequado para a modelagem de dados relacionais e centralização operacional.


---

## 4. Problemas e Necessidades Identificados

A tabela a seguir correlaciona os problemas operacionais e de gestão identificados na Hold Fit com suas respectivas consequências para o negócio:

| Problema | Consequência |
| :--- | :--- |
| **Redundância e descentralização no cadastro de alunos** (informações em múltiplas planilhas e papéis) | Divergência de dados cadastrais, perda de histórico de frequência/treinos e elevado retrabalho na consulta de alunos. |
| **Preenchimento manual de dados e ausência de validação** (ex: CREF de professores e responsáveis técnicos) | Erros de digitação, omissão de campos obrigatórios e risco legal por falta de comprovação de habilitação técnica. |
| **Dispersão e falta de integração dos dados financeiros** (contas a pagar e receber em planilhas separadas) | Cobranças indevidas, alunos inadimplentes com acesso liberado, pagantes bloqueados por engano e falta de visão de caixa. |
| **Falta de categorização das despesas e fornecedores** (mistura de salários, produtos e manutenção de máquinas) | Descontrole nos prazos de manutenção preventiva, pagamentos em duplicidade e dificuldade de mapear os maiores custos. |
| **Ausência de integração entre o setor financeiro e o controle de acesso** | Impossibilidade de aplicar a regra de bloqueio diário automático (até 23:59) para inadimplentes ou demitidos. |
| **Incapacidade de gerenciar múltiplos papéis de um usuário** (ex: professor que também é aluno) | Criação de cadastros duplicados no sistema, gerando conflitos de permissões de acesso e erros no controle de mensalidades. |
| **Tomada de decisão baseada em processos informais e planilhas isoladas** | Impossibilidade de gerar relatórios gerenciais confiáveis para acompanhar a taxa de evasão de alunos e planejar a expansão. |

---

## 5. Processos de Negócio

### 5.1. Processo de Cadastro e Matrícula de Aluno
* **Quem participa?** Pessoa (futuro aluno) e Sistema.
* **O que inicia o processo?** A pessoa procura a academia com o interesse de se matricular.
* **O que acontece?** A pessoa fornece os dados pessoais, realiza o cadastro e é vinculada às aulas e planos subsequentes.
* **Qual informação é gerada?** Ficha cadastral do aluno, número de matrícula e status do perfil.
* **Qual é o resultado?** Aluno cadastrado e apto a frequentar as dependências e aulas da academia.

### 5.2. Processo de Contratação e Alocação de Funcionário
* **Quem participa?** Gestão da academia e o Funcionário.
* **O que inicia o processo?** A necessidade de preencher uma vaga em determinado departamento da academia.
* **O que acontece?** Definição do departamento e cargo, validação de documentos e contratação do funcionário.
* **Qual informação é gerada?** Registro de funcionário, vinculação de cargo/departamento e credenciais de acesso ao sistema.
* **Qual é o resultado?** Funcionário integrado à estrutura operacional da empresa.

### 5.3. Processo de Gestão de Turmas e Aulas (Corpo Técnico)
* **Quem participa?** Professor (Mentor), Alunos e Setor Operacional.
* **O que inicia o processo?** A validação do CREF do professor e a definição da grade de modalidades oferecidas.
* **O que acontece?** O professor licenciado assume uma modalidade, a turma é criada no sistema e os alunos são enturmados.
* **Qual informação é gerada?** Vinculação CREF-Professor, grade horária e lista de presença/frequência da turma.
* **Qual é o resultado?** Aulas ministradas sob responsabilidade técnica com alunos acompanhados.

### 5.4. Processo de Contas a Pagar (Despesas e Maquinário)
* **Quem participa?** Setor Financeiro e Fornecedores (de equipamentos e serviços de manutenção).
* **O que inicia o processo?** A aquisição de novas máquinas, a realização de manutenção ou o vencimento de contas operacionais.
* **O que acontece?** Lançamento da obrigação financeira, conferência da entrega do produto/serviço e realização do pagamento.
* **Qual informação é gerada?** Registro de saída financeira, histórico de manutenção de equipamentos e comprovantes de pagamento.
* **Qual é o resultado?** Fornecedores pagos, equipamentos operacionais e obrigações financeiras quitadas.

### 5.5. Processo de Contas a Receber (Mensalidades)
* **Quem participa?** Aluno e Setor Financeiro.
* **O que inicia o processo?** O vencimento da mensalidade ou plano contratado pelo aluno.
* **O que acontece?** O aluno efetua o pagamento da mensalidade e o setor financeiro dá baixa no título.
* **Qual informação é gerada?** Recibo de pagamento, atualização do status financeiro do aluno (adimplente/inadimplente) e movimentação de caixa.
* **Qual é o resultado?** Receita confirmada para a empresa e liberação automática do acesso do aluno até a catraca/sistema.

---
## 6. Requisitos Funcionais (RF)

| Código | Nome | Descrição |
| :--- | :--- | :--- |
| **RF01** | Gestão de Usuários e Pessoas | O sistema deve permitir o cadastro e gerenciamento de pessoas (alunos, professores e funcionários), possibilitando que um mesmo cadastro assume múltiplos papéis (ex.: professor que também é aluno). |
| **RF02** | Gestão de Planos e Matrículas | O sistema deve permitir a realização e o cancelamento de matrículas de alunos associadas aos planos oferecidos pela academia. |
| **RF03** | Gestão de Turmas e Grade de Aulas | O sistema deve permitir o cadastramento de modalidades, turmas, horários e a vinculação de professores e alunos a essas turmas. |
| **RF04** | Controle de Acesso | O sistema deve consultar o status do aluno/funcionário e validar a liberação de acesso às dependências da academia. |
| **RF05** | Gestão de Contas a Receber | O sistema deve registrar os recebimentos de mensalidades e pagamentos avulsos, demonstrando os lançamentos futuros. |
| **RF06** | Gestão de Contas a Pagar e Fornecedores | O sistema deve cadastrar fornecedores (equipamentos e serviços de manutenção) e registrar as despesas operacionais e pagamentos da empresa. |
| **RF07** | Alertas de Manutenção Preventiva | O sistema deve notificar o gestor sobre os prazos de manutenção preventiva dos equipamentos e maquinários. |
| **RF08** | Painel e Relatórios Financeiros | O sistema deve exibir o saldo atual em caixa, o cálculo da receita consolidada e relatórios de alunos inadimplentes. |
| **RF09** | Notificação de Cobrança | O sistema deve disponibilizar relatórios de inadimplência e permitir o envio de notificações de cobrança utilizando os dados de contato cadastrados do aluno. |
| **RF10** | Cadastrar Dependente | O sistema deve permitir o cadastro de um dependente vinculando-o obrigatoriamente a um Responsável ativo existente no sistema. |
| **RF11** | Coletar Autorização do Responsável | O sistema deve disponibilizar um mecanismo (aceite digital, checkbox assinado ou flag) onde o Responsável confirma e autoriza a inclusão do dependente. |
| **RF12** | Atribuir Débitos ao Responsável | O sistema deve direcionar automaticamente qualquer lançamento financeiro, conta a pagar ou cobrança gerada por/para o dependente diretamente para a conta/cadastro do Responsável. |
| **RF13** | Validar Idade para Acesso Físico | O sistema de controle de acesso (catracas/credenciamento) deve consultar a data de nascimento do dependente e verificar se a idade é igual ou superior a 14 anos antes de liberar a entrada no ambiente de trabalho. |
| **RF14** | Bloquear Cadastro Sem Autorização | O sistema deve impedir a gravação e a ativação do cadastro do dependente caso a autorização do responsável não tenha sido confirmada. |

## 7. Requisitos Não Funcionais (RNF)

| Código | Nome | Descrição |
| :--- | :--- | :--- |
| **RNF01** | Restrição de Acesso | O sistema deverá restringir o acesso às funcionalidades conforme o perfil de usuário, como administrador, professor e demais perfis autorizados. |
| **RNF02** | Proteção aos Dados Pessoais | Os dados pessoais tratados pelo sistema deverão possuir mecanismos de proteção e controle de acesso compatíveis com a LGPD. |
| **RNF03** | Liberação de Catraca | A operação de liberação da catraca deverá apresentar tempo de resposta inferior a 1 segundo em condições normais de operação. |
| **RNF04** | Histórico das operações financeiras | O sistema deverá manter histórico/auditoria das operações financeiras relevantes, incluindo cancelamentos e estornos. |
| **RNF05** | Chaves Estrangeiras | As tabelas relacionadas do banco de dados deverão utilizar chaves estrangeiras com regras explícitas de atualização e deleção, evitando exclusões acidentais. |
| **RNF06** | Autenticação para Acesso | O sistema deverá exigir autenticação para acesso às funcionalidades restritas. |
| **RNF07** | Credenciais de Acesso | O sistema deverá proteger credenciais de acesso, armazenando-as de forma segura e não em texto puro. |
| **RNF08** | Cópias de Segurança | O sistema deverá realizar cópias de segurança periódicas dos dados, com procedimento definido de restauração. |
| **RNF09** | Integridade dos Dados de Cadastro | O sistema deverá preservar a integridade e consistência dos dados durante operações de cadastro, alteração, pagamento e cancelamento. |
| **RNF10** | Mensagem de Erro | O sistema deverá disponibilizar mensagens claras de erro e confirmação para operações realizadas pelos usuários. |
| **RNF11** | Manutenção do Banco de Dados | O sistema deverá permitir a manutenção do banco de dados sem comprometer a integridade dos registros existentes. |
| **RNF12** | Desempenho | O tempo de resposta da consulta de validação de idade e permissão de entrada no ambiente de trabalho deve ser inferior a 1 segundo por tentativa de acesso/check-in. |
| **RNF13** | Integridade / Segurança | A associação entre a tabela de Dependente e Responsável deve ser garantida por uma chave estrangeira (FK_Responsavel) com restrição NOT NULL no banco de dados, impedindo registros órfãos. |
| **RNF14** | Conformidade Legal / LGPD | Os dados pessoais do dependente (especialmente data de nascimento e identificadores) devem possuir controle de acesso restrito e ser tratados segundo os termos de consentimento do responsável. |
| **RNF15** | Usabilidade / Rastreabilidade | O sistema deve manter um log de auditoria indicando a data, hora e ID do responsável no momento em que a permissão/autorização do dependente foi registrada. |


## 8. Regras de Negócio e Operacionais (RN)

| Código | Nome | Descrição |
| :--- | :--- | :--- |
| **RN01** | Documento Oficial Obrigatório | O cadastro de qualquer pessoa no sistema exige obrigatoriamente a apresentação de um documento oficial de identificação válido (CPF ou RNM). |
| **RN02** | Validação Profissional do Corpo Técnico (CREF) | Para cadastrar-se como professor, é obrigatória a apresentação do número do CREF válido, com a indicação da categoria (G - Graduado, P - Provisionado ou AE - Atividade Específica). |
| **RN03** | Responsável Técnico (RT) | O sistema deve exigir a indicação de pelo menos um professor cadastrado como Responsável Técnico (RT) da academia. |
| **RN04** | Registro Institucional do CREF | O sistema deve manter cadastrado o número do CREF ativo do estabelecimento (HoldFit). |
| **RN05** | Bloqueio Diário de Acesso por Inadimplência ou Demissão | Em caso de inadimplência do aluno ou demissão de funcionário/professor, o acesso às dependências da academia deve ser bloqueado automaticamente no próprio dia, impreterivelmente até às 23:59, sendo reativado apenas mediante a quitação do débito ou reativação do cadastro. |
| **RN06** | Restrição de Plano Diário para Inadimplentes | O sistema deve impedir que alunos com pendências financeiras adquiram diárias sem antes quitar o débito pendente. |
| **RN07** | Tabela de Planos e Políticas de Desconto | O sistema deve aplicar as seguintes regras de precificação e desconto sobre a mensalidade base (R$ 120,00): Diário: Cobrança por dia avulso. Mensal (1 mês): R$120,00/mês. Trimestral (3 meses): R$108,00/mês (10% de desconto no valor base). Anual (12 meses): R$96,00/mês (20% de desconto no valor base). |
| **RN08** | Vínculo Organizacional | Todo funcionário cadastrado deve estar obrigatoriamente associado a um departamento e a um cargo específico. |
| **RN09** | Manutenção do Período Pago no Cancelamento | A interrupção de cobranças futuras não pode cancelar ou interferir no prazo de acesso das mensalidades já pagas pelo aluno. |
| **RN10** | Acesso Restrito à Agenda de Aulas | O mapeamento semanal e a grade diária de aulas devem ser visíveis e gerenciáveis exclusivamente por usuários com perfil de "Professor" ou "Administrador". |
| **RN11** | Exigência de Autorização do Responsável | O cadastro e a inclusão da entidade Dependente só podem ser efetuados mediante autorização formal prévia e permissão concedida por um Responsável (Titular) devidamente cadastrado e ativo. |
| **RN12** | Atribuição de Responsabilidade Financeira | Toda e qualquer cobrança, fatura, mensalidade ou conta a pagar gerada a partir das atividades, consumo ou serviços vinculados ao Dependente será direcionada e atribuída exclusivamente ao seu Responsável Legal. |
| **RN13** | Idade Mínima para Acesso ao Ambiente de Trabalho | Para que o Dependente tenha permissão de acesso e circulação no ambiente de trabalho da empresa/organização, ele deve possuir a idade mínima de 14 anos. |


---

## 9. Restrições e Políticas Organizacionais

### 9.1. Políticas de Controle de Acesso e Permissões
* **Alteração e Concessão de Perfis:** Apenas usuários com perfil Administrador ou Gestor possuem autorização para alterar o nível de acesso de um usuário (ex.: promover um aluno a professor), cadastrar novos funcionários e registrar o desligamento/demissão de colaboradores.
* **Gestão da Grade de Aulas:** O mapeamento semanal e o gerenciamento de turmas são de acesso exclusivo de Professores e Administradores. Alunos possuem permissão apenas para consultar as turmas nas quais estão devidamente matriculados.
* **Consulta de Dados Financeiros:** A visualização do caixa geral, relatórios de faturamento e contas a pagar aos fornecedores é restrita exclusivamente ao Setor Financeiro e aos Administradores.

### 9.2. Políticas Financeiras e Condições de Pagamento
* **Tabela Rígida de Descontos:** Os descontos aplicados nos planos de adesão são fixos e calculados sobre o valor base mensal de R$ 120,00:
  * **Plano Mensal (1 mês):** R$ 120,00/mês (valor integral).
  * **Plano Trimestral (3 meses):** R$ 108,00/mês (10% de desconto no valor base).
  * **Plano Anual (12 meses):** R$ 96,00/mês (20% de desconto no valor base).
* **Aprovação de Exceções:** Qualquer concessão de desconto ou condição financeira fora desta tabela predefinida exige aprovação expressa do Administrador.
* **Regra para Plano Diário:** A cobrança por dia avulso possui valor fixado individualmente e não aceita a aplicação de descontos cumulativos referentes aos planos recorrentes.

### 9.3. Restrições de Inadimplência e Cancelamento
* **Prazo Limite para Bloqueio de Acesso:** Em casos de inadimplência do aluno ou desligamento de colaboradores, o bloqueio do acesso na catraca e nas dependências da academia deve ser efetivado automaticamente impreterivelmente até às 23:59 do próprio dia.
* **Proibição de Compras por Inadimplentes:** O sistema deve impedir que alunos com pendências financeiras adquiram diárias ou novos serviços avulsos antes da quitação total dos débitos pendentes.
* **Regra de Cancelamento e Prazos Pagos:** A solicitação de cancelamento de plano interrompe a geração de cobranças futuras, mas não revoga o direito de acesso do aluno durante o período que já foi devidamente pago.

### 9.4. Restrições Regulatórias e de Habilitação Profissional
* **Exigência do CREF para Docência:** É expressamente proibido cadastrar um funcionário no papel de "Professor" sem a validação e o registro de seu número de CREF profissional ativo.
* **Obrigatoriedade de Responsável Técnico (RT):** O sistema deve exigir que pelo menos um professor ativo cadastrado seja designado como Responsável Técnico (RT) da unidade.
* **Unicidade de Cadastro por Documento Oficial:** Toda pessoa física (aluno, professor ou funcionário) deve ser cadastrada exclusivamente via CPF ou RNM. O sistema impede a criação de cadastros duplicados para um mesmo documento.
---

## 10 Entidades e Atributos

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

## 11. Relacionamentos e Cardinalidades

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

## 12. Justificativas Técnicas das Decisões

Durante o desenvolvimento da modelagem do banco de dados da Hold Fit, foram tomadas algumas decisões relacionadas à estrutura das entidades, definição dos atributos, escolha das chaves primárias e estrangeiras e estabelecimento dos relacionamentos entre as entidades. Essas decisões foram baseadas nos processos de negócio, requisitos e regras de negócio definidos anteriormente, buscando representar de forma organizada as principais informações utilizadas pela academia.

### 12.1. Entidades e Atributos
A definição das entidades foi realizada a partir dos principais elementos envolvidos nos processos da Hold Fit. Foram consideradas as pessoas que utilizam ou fazem parte da academia, a estrutura organizacional, as atividades oferecidas, os equipamentos, os fornecedores e os processos financeiros.

A entidade PESSOA, por exemplo, foi definida como uma entidade forte e representa o cadastro principal das pessoas relacionadas à academia. Nela estão armazenadas informações como CPF, nome, data de nascimento, endereço, telefone, e-mail e gênero. A utilização dessa entidade permite centralizar os dados pessoais e possibilita que uma mesma pessoa possa assumir diferentes papéis dentro do sistema.

Dessa forma, a escolha das entidades e atributos buscou separar as informações de acordo com sua finalidade, evitando concentrar todos os dados em uma única estrutura e permitindo representar os diferentes processos apresentados no projeto.

### 12.2. Escolha de PKs
A escolha das chaves primárias foi realizada buscando utilizar identificadores capazes de diferenciar cada registro dentro de sua respectiva entidade.

A utilização dessas chaves permite identificar os registros e manter a ligação entre as diferentes partes do sistema, reduzindo a possibilidade de duplicidade e facilitando a organização dos dados.

### 12.3. Relacionamentos e Cardinalidades
Os relacionamentos foram definidos considerando os processos de negócio e a forma como as entidades participam das atividades da Hold Fit. As cardinalidades foram utilizadas para representar quantas ocorrências de uma entidade podem estar relacionadas a outra.

Foi estruturado da seguinte forma pois, assim, as cardinalidades definidas procuram representar os vínculos existentes entre as entidades de acordo com os processos da academia, mantendo a estrutura necessária para o controle de alunos, funcionários, professores, aulas, fornecedores e informações financeiras.
