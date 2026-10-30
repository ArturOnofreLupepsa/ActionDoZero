# ActionDoZero 🚀

Repositório criado para fins de estudo, automação e implementação de GitHub Actions do zero. Este projeto contém diferentes fluxos de trabalho (*workflows*) automatizados para CI/CD, testes, lint ou tarefas personalizadas.

---

## 📋 Índice

- [Visão Geral](#visão-geral)
- [Como Utilizar](#como-utilizar)
- [Lista de Actions (Workflows)](#-lista-de-actions-workflows)
- [Contribuição](#contribuição)

---

## 🔍 Visão Geral

Cada arquivo localizado na pasta `.github/workflows/` representa uma rotina automatizada executada pelo GitHub Actions mediante gatilhos específicos (como `push`, `pull_request`, ou acionamentos manuais `workflow_dispatch`).

---

## ⚙️ Lista de Actions (Workflows)

Abaixo estão descritas as actions disponíveis neste repositório e a função de cada uma:

### 1. [Nome da Action 1 - ex: CI Pipeline] (`ci.yml`)
* **O que faz:** Realiza a integração contínua do projeto a cada novo `push` ou `pull_request` na branch principal.
* **Gatilho (*Trigger*):** `push` nas branches `main`/`master`.
* **Passos principais:**
  - Faz o checkout do código.
  - Configura o ambiente/linguagem (ex: Node.js, Python, etc.).
  - Instala as dependências.
  - Executa os testes automatizados.

### 2. [Nome da Action 2 - ex: Lint & Code Quality] (`lint.yml`)
* **O que faz:** Verifica os padrões de código, formatação e boas práticas utilizando ferramentas de linting.
* **Gatilho (*Trigger*):** `pull_request` voltado para a branch `main`.
* **Passos principais:**
  - Analisa arquivos em busca de erros de sintaxe ou violações de estilo.
  - Reporta falhas diretamente no painel do Pull Request caso encontre inconsistências.

### 3. [Nome da Action 3 - ex: Deploy Automático] (`deploy.yml`)
* **O que faz:** Automatiza o processo de publicação/deploy da aplicação em um ambiente de homologação ou produção.
* **Gatilho (*Trigger*):** Criação de uma nova `release` ou `push` bem-sucedido na branch de produção.
* **Passos principais:**
  - Constrói o artefato de build.
  - Autentica no serviço de hospedagem/nuvem.
  - Realiza o deploy efetivo.

*(Nota: Caso sua estrutura possua actions personalizadas baseadas em Docker ou JavaScript composite actions na raiz, você pode listá-las aqui detalhando seus inputs e outputs).*

---

## commits "name: Gerar Changelog"

          # Configura o nome do usuário do Git que fará o commit (nome padrão do bot)
          git config user.name "github-actions[bot]"
          # Configura o email oficial de sistema do bot do GitHub Actions
          git config user.email "41898282+github-actions[bot]@users.noreply.github.com"

          # Coloca o arquivo CHANGELOG.md modificado na área de preparação do Git (staging)
          git add CHANGELOG.md

          # "git diff --cached --quiet" verifica de forma silenciosa se houve alguma mudança real no arquivo.
          # Se o arquivo estiver idêntico ao que já existia (nenhum commit novo), a condição é verdadeira.
          if git diff --cached --quiet; then
            echo "Nenhuma alteracao no Changelog."
          else
            # Se houve mudança, cria o commit de fato. 
            # A tag "[skip ci]" na mensagem é crucial: ela avisa ao GitHub para NÃO disparar este workflow de novo por causa deste commit.
            git commit -m "docs(changelog): atualiza changelog [skip ci]"
            # Envia as alterações (o commit) de volta para o repositório online
            git push

---

## 🛠️ Como Utilizar

Para testar ou clonar este repositório em sua máquina:

```bash
# Clone o repositório
git clone [https://github.com/ArturOnofreLupepsa/ActionDoZero.git](https://github.com/ArturOnofreLupepsa/ActionDoZero.git)

# Acesse a pasta do projeto
cd ActionDoZero


Integrantes do grupo:
Artur Vinicius Onofre Lupepsa RA20258
Bruno Januário RA250276
