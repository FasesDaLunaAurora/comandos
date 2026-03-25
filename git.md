# 🔧 Guia Básico de Comandos Git

Este repositório contém comandos essenciais do Git para controle de versão. Serve como referência rápida para uso no dia a dia.

---

## 📦 Inicialização

| Comando | Descrição |
|--------|----------|
| `git init` | Inicializa um repositório local |
| `git clone url` | Clona um repositório remoto |

---

## 📁 Status e Monitoramento

| Comando | Descrição |
|--------|----------|
| `git status` | Mostra o estado atual do repositório |
| `git log` | Histórico de commits |
| `git log --oneline` | Histórico resumido |
| `git diff` | Mostra diferenças não commitadas |

---

## ➕ Adição e Commit

| Comando | Descrição |
|--------|----------|
| `git add arquivo` | Adiciona arquivo ao stage |
| `git add .` | Adiciona tudo ao stage |
| `git commit -m "mensagem"` | Cria um commit |
| `git commit -am "mensagem"` | Add + commit (arquivos rastreados) |

---

## 🔄 Branches

| Comando | Descrição |
|--------|----------|
| `git branch` | Lista branches |
| `git branch nome` | Cria nova branch |
| `git checkout nome` | Troca de branch |
| `git checkout -b nome` | Cria e troca |
| `git switch nome` | Alternativa moderna ao checkout |

---

## 🔀 Merge e Rebase

| Comando | Descrição |
|--------|----------|
| `git merge branch` | Mescla branch atual com outra |
| `git rebase branch` | Reaplica commits sobre outra base |

---

## 🌐 Repositórios Remotos

| Comando | Descrição |
|--------|----------|
| `git remote add origin url` | Adiciona repositório remoto |
| `git remote -v` | Lista remotos |
| `git push origin branch` | Envia commits |
| `git pull` | Atualiza repositório local |
| `git fetch` | Baixa alterações sem aplicar |

---

## 🧹 Desfazendo alterações

| Comando | Descrição |
|--------|----------|
| `git restore arquivo` | Desfaz alterações locais |
| `git reset arquivo` | Remove do stage |
| `git reset --hard` | Volta ao último commit (perigoso) |
| `git revert commit` | Cria commit que desfaz outro |

---

## 🏷️ Tags

| Comando | Descrição |
|--------|----------|
| `git tag` | Lista tags |
| `git tag nome` | Cria tag |
| `git push origin nome` | Envia tag |

---

## 🧠 Dicas

- Commits devem ser pequenos e descritivos
- Evite usar `git push -f` sem saber exatamente o que está fazendo
- Prefira `git switch` e `git restore` (mais claros que `checkout`)
- Use branches para qualquer mudança relevante

---

## 🚧 Em construção

Este guia será expandido com:
- Fluxos de trabalho (Git Flow, Trunk Based)
- Resolução de conflitos
- Boas práticas profissionais
