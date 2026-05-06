# Documento de Estratégia de Versionamento: GitHub Flow

### 1. Introdução
A estratégia escolhida para o versionamento foi o GitHub Flow, porque ele é fácil de usar e focado em entrega contínua. Ele usa branches de curta duração para novas funcionalidades ou correções, e as integra rapidamente à branch principal após validação automatizada e revisão por pares.

### 2. Estrutura de Branches
O repositório funciona com uma estrutura simplificada para evitar complexidade e atrasos nas entregas:

| Tipo de Branch | Padrão de Nomenclatura | Origem | Destino | Regra Principal |
| :--- | :--- | :--- | :--- | :--- |
| **Principal** | `main` | - | - | Código sempre testado, estável e pronto para produção. Nunca aceita commits diretos. |
| **Funcionalidade** | `feature/nome-da-tarefa` | `main` | `main` | Branch temporária e de curta duração para desenvolver novas tarefas ou melhorias. |
| **Correção** | `fix/descrição-do-bug` | `main` | `main` | Branch temporária dedicada à resolução de problemas identificados. |

### 3. Fluxo de Trabalho
O ciclo de vida de qualquer alteração no código segue estes passos rigorosos:

| Etapa | Ação do Desenvolvedor / Sistema | Objetivo |
| :--- | :--- | :--- |
| **1. Criação** | Criar branch local a partir da `main` atualizada. | Isolar o ambiente para a nova funcionalidade ou correção. |
| **2. Desenvolvimento** | Fazer alterações e commitar. | Registrar o progresso com mensagens claras de commit. |
| **3. Pull Request** | Abrir PR apontando para a `main`. | Iniciar a discussão e o processo de integração. |
| **4. Validação (CI)** | GitHub Actions roda automaticamente. | Executar testes e lint para garantir que o código não quebra o sistema. |
| **5. Revisão** | Par do time analisa o PR. | Garantir a qualidade do código através da aprovação de outro membro. |
| **6. Merge** | Realizar o merge e deletar a branch. | Integrar o código aprovado à `main` e manter o repositório limpo. |

### 4. Políticas de Pull Request e Merge
Para garantir a integridade do código, aplicamos as seguintes regras:
* **CI Green:** Nenhum merge é permitido se os testes automatizados falharem.
* **Revisão Obrigatória:** Todo Pull Request deve ter a aprovação de ao menos um par.
* **Histórico Limpo:** Encorajamos o uso de *Squash and Merge* para manter o histórico da branch `main` limpo.

### 5. Critérios de Revisão
Os revisores devem observar os seguintes pontos antes da aprovação:
* **Funcionalidade:** O código cumpre o que foi proposto?
* **Cobertura de Testes:** Foram adicionados ou atualizados testes para a nova funcionalidade?
* **Qualidade e Padronização:** O código segue os padrões definidos pelo projeto?
* **Segurança:** Há exposição de chaves de API, senhas ou vulnerabilidades óbvias?

### 6. Política de Versionamento
Adotamos o Semantic Versioning 2.0.0 para a gestão de tags e releases. Seguimos o formato `MAJOR.MINOR.PATCH`:

| Tipo | Incremento | Quando usar? | Exemplo de Mudança (de `1.2.3`) |
| :--- | :--- | :--- | :--- |
| **PATCH** | `x.x.PATCH` | Correções de bugs que não afetam funcionalidades. | Passa para `1.2.4` |
| **MINOR** | `x.MINOR.0` | Adição de novas funcionalidades retrocompatíveis. | Passa para `1.3.0` |
| **MAJOR** | `MAJOR.0.0` | Mudanças drásticas incompatíveis com versões anteriores. | Passa para `2.0.0` |
