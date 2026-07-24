# Guia de comandos — Tag aula-02

Siga na ordem. Rode isso dentro do repositório do grupo (clonado do GitHub).

## 1. Copiar os arquivos prontos para o repositório

Copie para a raiz do seu repositório:
- `src/` (pasta vazia, com .gitkeep)
- `db/migrations/` (pasta vazia, com .gitkeep)
- `docs/REQUISITOS.md` (edite o conteúdo para o projeto real do grupo!)
- `tests/` (pasta vazia, com .gitkeep)
- `.gitignore`
- `.env.example`

## 2. Criar branch, commitar e abrir PR

```bash
git checkout -b docs/requisitos

git add docs/REQUISITOS.md src/.gitkeep db/migrations/.gitkeep tests/.gitkeep .gitignore .env.example
git commit -m "docs: adiciona REQUISITOS.md e estrutura de pastas

Closes #1"

git push -u origin docs/requisitos
```

Depois, no GitHub (ou via `gh`), abra o Pull Request:

```bash
gh pr create --title "docs: REQUISITOS.md e estrutura inicial" \
  --body "Closes #1" \
  --base main --head docs/requisitos
```

> Peça para outro integrante do grupo **revisar e aprovar** o PR (isso conta como "PR revisado"). Depois disso, faça o merge:
```bash
gh pr merge --merge
```

## 3. Criar as issues de backlog (mínimo 8)

Exemplos de issues que você pode adaptar ao projeto do grupo:

```bash
gh issue create --title "Configurar ambiente de desenvolvimento" --body "Instalar dependências e configurar .env local" --assignee @me
gh issue create --title "Modelar banco de dados" --body "Criar diagrama ER e primeiras migrations"
gh issue create --title "Implementar cadastro de usuário" --body "Endpoint/tela de cadastro"
gh issue create --title "Implementar login/autenticação" --body "Fluxo de login e sessão/token"
gh issue create --title "Criar CRUD principal do domínio" --body "Funcionalidade central do sistema"
gh issue create --title "Escrever testes automatizados" --body "Cobrir principais fluxos com testes"
gh issue create --title "Configurar CI básico" --body "Rodar testes automaticamente a cada push"
gh issue create --title "Documentar API/endpoints" --body "Atualizar docs/ com detalhes técnicos"
```

Depois, crie um **Project (Board)** no GitHub (aba "Projects" do repositório), adicione essas issues a ele e defina um responsável (assignee) para cada uma.

## 4. Garantir commits de todos os integrantes

Cada integrante precisa ter pelo menos 1 commit. Exemplo simples (cada um roda no seu ambiente):

```bash
git checkout main
git pull
git checkout -b feat/nome-do-integrante
echo "# Contribuição de [Nome]" >> docs/REQUISITOS.md
git add docs/REQUISITOS.md
git commit -m "docs: pequena contribuição de [Nome]"
git push -u origin feat/nome-do-integrante
```
Depois é só abrir e mergear um PR rápido para cada um (ou mergear direto se o grupo preferir, dependendo da regra da aula).

## 5. Criar e publicar a tag aula-02

```bash
git checkout main
git pull

git tag -a aula-02 -m "Entrega aula-02: estrutura inicial + REQUISITOS.md"
git push origin aula-02
```

## 6. Criar a Release v0.1.0

```bash
gh release create v0.1.0 --title "v0.1.0" --notes "Primeira entrega do projeto: estrutura de pastas (src/, db/migrations/, docs/, tests/), REQUISITOS.md definido via PR revisado, board com backlog inicial (8+ issues) e responsáveis definidos, .gitignore e .env.example configurados."
```

Ou pela interface web: **Releases → Draft a new release → escolha a tag `aula-02` (ou crie a tag v0.1.0) → preencha a descrição → Publish**.

---

## Checklist final antes de entregar

- [ ] `docs/REQUISITOS.md` mergeado via PR revisado (fecha #1)
- [ ] Estrutura de pastas completa (`src/`, `db/migrations/`, `docs/`, `tests/`, `.gitignore`, `.env.example`)
- [ ] Board com ≥ 8 issues e responsáveis definidos
- [ ] Tag `aula-02` publicada com push
- [ ] Release v0.1.0 com descrição
- [ ] Cada integrante com pelo menos 1 commit
