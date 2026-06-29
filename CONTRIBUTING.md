# Contribuindo com task_manager

Olá! 👋 Seja muito bem-vindo(a) ao projeto task_manager. Este repositório é um espaço aberto para aprender, colaborar e melhorar um gerenciador de tarefas com a comunidade. Nossa ideia é manter um ambiente acolhedor, profissional e fácil de contribuir, inclusive para quem está começando no GitHub e no desenvolvimento.

Este documento reúne as principais diretrizes para você participar de forma organizada e tranquila.

## Índice

- [Como Começar](#como-começar)
- [Fluxo de Contribuição](#fluxo-de-contribuição)
- [Convenções](#convenções)
- [Tipos de Commit](#tipos-de-commit)
- [Checklist de Pull Request](#checklist-de-pull-request)
- [Perguntas Frequentes](#perguntas-frequentes-faqs)
- [Rodapé](#rodapé)

---

## Como Começar

### Pré-requisitos

Antes de contribuir, certifique-se de ter instalado:

- Git
- Uma conta no GitHub
- Python 3.8+ (a versão 3.10 ou 3.11 é recomendada)

Se você ainda não tiver o Git configurado, pode usar os comandos abaixo para definir seu nome e e-mail:

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seuemail@example.com"
```

### 1. Faça o fork do repositório

No GitHub, abra a página do repositório e clique em “Fork”. Isso cria uma cópia do projeto na sua conta.

Depois, acesse o seu fork e copie o URL remoto.

### 2. Clone o fork para sua máquina

```bash
git clone https://github.com/SEU_USUARIO/task_manager.git
cd task_manager
```

### 3. Configure o remote upstream

O remote upstream aponta para o repositório original. Isso facilita manter seu fork atualizado.

```bash
git remote -v
git remote add upstream https://github.com/OWNER/task_manager.git
git remote -v
```

> ⚠️ Se o remote upstream já existir, use o comando abaixo para atualizar o endereço:

```bash
git remote set-url upstream https://github.com/OWNER/task_manager.git
```

---

## Fluxo de Contribuição

A seguir, veja o fluxo principal para enviar uma contribuição com segurança e organização.

### 1. Escolher uma issue

Antes de começar, confira as issues abertas e escolha uma que faça sentido para você. Se estiver começando, prefira tarefas marcadas como “good first issue” ou “beginner-friendly”.

Você pode comentar na issue para dizer que vai trabalhar nela, evitando duplicidade.

### 2. Criar uma branch

Sempre crie uma branch específica para a sua mudança.

Exemplos de nomes:

```bash
git checkout -b feature/adicionar-prioridade
# ou
git checkout -b fix/corrigir-validacao
# ou
git checkout -b docs/atualizar-readme
# ou
git checkout -b refactor/organizar-crud
```

### 3. Fazer as mudanças

Mantenha as alterações focadas no que foi proposto. Evite misturar correções, refatorações e novas funcionalidades em um único commit, a menos que seja realmente necessário.

### 4. Fazer commit com mensagem bem formatada

Use mensagens claras e objetivas.

```bash
git add .
git commit -m "feat: adicionar campo de prioridade à tarefa"
```

### 5. Fazer push da branch

```bash
git push -u origin feature/adicionar-prioridade
```

### 6. Abrir um Pull Request

No GitHub, clique em “Compare & pull request”. Escolha a branch do seu fork como origem e a branch principal do repositório original como destino.

### 7. Descrever o Pull Request corretamente

Um bom PR explica o que foi feito, por que foi feito e como validar.

Estrutura recomendada:

- Resumo da mudança
- Motivação
- Alterações principais
- Como testar
- Issue relacionada

Exemplo:

```md
## Resumo
Adicionei um campo de prioridade às tarefas.

## Motivo
Melhorar a organização das tarefas por urgência.

## Alterações
- Adicionei o campo `priority` ao modelo
- Atualizei o schema de entrada
- Ajustei a documentação

## Testes
- Executei a aplicação localmente
- Validei os endpoints no Swagger
```

---

## Convenções

### Estrutura de branches

Use nomes curtos, em minúsculas e com hífen:

- `feature/` — novas funcionalidades
- `fix/` — correções de bugs
- `docs/` — atualização de documentação
- `refactor/` — reorganização de código
- `test/` — testes
- `chore/` — manutenção e ajustes menores

Exemplos:

```bash
git checkout -b feature/adicionar-filtro
```

### Formato de mensagens de commit

O padrão recomendado é:

```text
tipo(escopo): descrição
```

Exemplos:

```bash
git commit -m "feat(tasks): adicionar campo de prioridade"
git commit -m "fix(users): corrigir validação de e-mail"
git commit -m "docs(readme): atualizar instruções de instalação"
```

### Exemplos de bons e maus commits

Bons commits:

- `feat(tasks): adicionar status de conclusão`
- `fix(api): corrigir erro ao deletar tarefa`
- `docs(readme): incluir passo a passo para Windows`

Commits que podem melhorar:

- `arrumei coisa`
- `update`
- `teste`
- `fix bug`

Mensagens vagas dificultam a revisão e o histórico do projeto.

### Estilo de código

Para manter o código consistente:

- Use indentação de 4 espaços em Python
- Siga o estilo PEP 8 sempre que possível
- Prefira nomes claros e descritivos para funções e variáveis
- Use `snake_case` para funções e variáveis
- Use `CamelCase` apenas quando o padrão do projeto exigir
- Comente apenas quando necessário, sem exagerar
- Evite código duplicado e mudanças desnecessárias

---

## Tipos de Commit

Os tipos abaixo ajudam a entender rapidamente a intenção da alteração:

- `feat` — nova funcionalidade
- `fix` — correção de bug
- `docs` — atualização ou criação de documentação
- `style` — formatação, ajustes visuais ou organização sem alterar lógica
- `refactor` — refatoração sem mudança de comportamento externo
- `test` — inclusão ou ajuste de testes
- `chore` — manutenção, configuração e tarefas auxiliares

Exemplos práticos:

```bash
git commit -m "feat: adicionar filtro por status"
git commit -m "fix: corrigir erro ao salvar tarefa vazia"
git commit -m "docs: melhorar guia de contribuição"
```

---

## Checklist de Pull Request

Antes de enviar seu PR, faça estas validações:

- [ ] O código foi testado localmente
- [ ] A aplicação roda sem erros
- [ ] A mudança está relacionada à issue escolhida
- [ ] A documentação foi atualizada, se necessário
- [ ] Não há prints de debug ou código comentado desnecessário
- [ ] A branch possui um nome claro e objetivo
- [ ] A mensagem do commit está bem escrita

### Como sincronizar com a branch principal

Antes de abrir o PR, é uma boa prática manter sua branch atualizada com a `main`.

```bash
git fetch upstream
git checkout main
git merge upstream/main
git checkout sua-branch
git merge main
```

### Como resolver conflitos

Se aparecerem conflitos:

1. Abra os arquivos marcados como conflitantes
2. Ajuste as partes necessárias
3. Adicione os arquivos resolvidos
4. Continue o merge ou o rebase

```bash
git add <arquivo>
git commit
```

> ⚠️ Se o conflito parecer complicado, peça ajuda na issue ou no PR. Não precisa resolver sozinho se estiver inseguro(a).

---

## Perguntas Frequentes (FAQs)

### Como sincronizar meu fork com o repositório original?

```bash
git fetch upstream
git checkout main
git merge upstream/main
git push origin main
```

### Como desfazer commits?

Se quiser remover o último commit, mas manter as alterações no seu computador:

```bash
git reset --soft HEAD~1
```

Se quiser apagar o commit e também descartar as mudanças:

```bash
git reset --hard HEAD~1
```

### Como atualizar minha branch com mudanças da main?

```bash
git fetch upstream
git checkout sua-branch
git merge upstream/main
```

### Como fazer correções após o PR ser rejeitado?

Não se preocupe. Correções são parte normal do processo. Faça as alterações, crie um novo commit e envie com push novamente. O PR será atualizado automaticamente.

```bash
git add .
git commit -m "fix: corrigir pontos levantados na revisão"
git push
```

---

## Rodapé

Obrigado por investir seu tempo em melhorar este projeto. Cada contribuição, mesmo a menor, ajuda a tornar o task_manager melhor para a comunidade. Se tiver dúvidas, não hesite em abrir uma issue ou comentar em uma discussão — qualquer pergunta é válida, especialmente quando o objetivo é aprender.

### Links úteis

- [README](README.md)
- [Issues](https://github.com/OWNER/task_manager/issues)
- [Pull Requests](https://github.com/OWNER/task_manager/pulls)

### Data

Última atualização: 29/06/2026
