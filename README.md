# 🖥️ Guia Básico de Comandos de Terminal (Linux)

Este repositório contém comandos básicos de terminal para sistemas Linux, com descrições simples e objetivas. A ideia é servir como referência rápida no dia a dia.

---

## 📁 Navegação de Diretórios

| Comando | Descrição |
|--------|----------|
| `pwd` | Mostra o diretório atual |
| `ls` | Lista arquivos e diretórios |
| `ls -l` | Lista detalhada |
| `ls -a` | Inclui arquivos ocultos |
| `cd nome` | Entra em um diretório |
| `cd ..` | Volta um nível |
| `cd ~` | Vai para o diretório home |

---

## 📂 Manipulação de Arquivos e Diretórios

| Comando | Descrição |
|--------|----------|
| `mkdir nome` | Cria um diretório |
| `rm arquivo` | Remove um arquivo |
| `rm -r pasta` | Remove diretório recursivamente |
| `cp origem destino` | Copia arquivos ou diretórios |
| `mv origem destino` | Move ou renomeia |
| `touch arquivo` | Cria um arquivo vazio |

---

## 📄 Visualização de Arquivos

| Comando | Descrição |
|--------|----------|
| `cat arquivo` | Mostra conteúdo completo |
| `less arquivo` | Visualização paginada |
| `head arquivo` | Primeiras linhas |
| `tail arquivo` | Últimas linhas |

---

## 🔍 Busca

| Comando | Descrição |
|--------|----------|
| `find . -name "arquivo"` | Busca arquivos |
| `grep "texto" arquivo` | Busca texto dentro de arquivo |
| `grep -r "texto" .` | Busca recursiva |

---

## ⚙️ Permissões

| Comando | Descrição |
|--------|----------|
| `chmod 755 arquivo` | Altera permissões |
| `chown user:group arquivo` | Altera dono |

---

## 📦 Gerenciamento de Pacotes (Ubuntu/Debian)

| Comando | Descrição |
|--------|----------|
| `sudo apt update` | Atualiza lista de pacotes |
| `sudo apt upgrade` | Atualiza sistema |
| `sudo apt install pacote` | Instala pacote |
| `sudo apt remove pacote` | Remove pacote |

---

## 🧠 Dicas

- Use `Tab` para autocompletar comandos e caminhos
- Use `Ctrl + C` para interromper processos
- Use `history` para ver comandos anteriores

---

## 🚧 Em construção

Este guia será expandido com:
- Comandos avançados
- Scripts úteis
- Boas práticas
