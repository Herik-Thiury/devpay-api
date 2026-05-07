# DevPay

O **DevPay** é um sistema back-end desenvolvido em [NestJS](https://nestjs.com/) para o gerenciamento de clientes, produtos, pedidos e pagamentos.

Além do seu propósito funcional, este repositório atua como um **estudo de caso para a implementação de práticas de DevOps**, focando na redução de *toil* (trabalho manual repetitivo), previsibilidade de entregas e integração contínua.

---

## Tecnologias Utilizadas

* **[Node.js](https://nodejs.org/) & [TypeScript](https://www.typescriptlang.org/)** - Base da aplicação.
* **[NestJS](https://nestjs.com/)** - Framework modular para a construção da API.
* **[Jest](https://jestjs.io/)** - Framework de testes automatizados (Unitários e E2E).
* **[GitHub Actions](https://github.com/features/actions)** - Automação do pipeline de CI/CD.

---

##  Práticas de DevOps Adotadas

Este projeto implementa rigorosamente as seguintes práticas de Engenharia de Software e DevOps para a avaliação parcial:

### 1. Integração Contínua (CI)
Foi configurado um pipeline automatizado (`.github/workflows/ci.yml`) que é acionado a cada *push* ou *Pull Request* para a branch `main`. O pipeline garante que:
* As dependências sejam instaladas corretamente.
* A análise estática de código (Lint) seja aprovada.
* O build da aplicação seja executado sem erros.
* A suíte de testes automatizados passe com sucesso.

A cada push ou pull request, o workflow definido em .github/workflows/ci.yml é acionado
para validar o build, executar o linting e garantir que todos os testes passem antes da
integração no branch principal.

### 2. Estratégia de Versionamento: GitHub Flow
Adotamos o **GitHub Flow** para garantir entregas rápidas e contínuas:
* Uso de **branches curtas** (`feature/`, `fix/`).
* Proteção da branch `main` (bloqueio de commits diretos).
* É necessário ter **Pull Requests** com revisão por pares.
* Exigência de pipeline verde (*CI Green*) para a aprovação de merges.
* Prática de **Squash and Merge** para manter o histórico da branch principal limpo.

>> *Para mais detalhes, consulte o [Documento de Estratégia de Versionamento](STRATEGY%20VERSIONING%20.md) e a [Justificativa Técnica]() elaborados pela equipe.*

---

## Como Executar o Projeto

### Pré-requisitos
Certifique-se de ter o **Node.js** (versão 18+ recomendada) e o **npm** instalados em sua máquina.

### Instalação

```bash
# Clone este repositório
$ git clone https://github.com/Herik-Thiury/devpay-api.git

# Acesse a pasta do projeto
$ cd devpay-api

# Instale as dependências
$ npm install

# Modo de desenvolvimento
$ npm run start

# Ambiente de desenvolvimento
$ npm run start:dev

# Modo de produção
$ npm run start:prod

# Qualidade e Testes (Unitários)
$ npm run test 

```
