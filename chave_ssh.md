# 🔐 Configuração de Chave SSH (Windows + GitHub)

Este guia descreve o processo completo para criar, configurar e validar uma chave SSH para autenticação no GitHub, seguindo boas práticas desde o início.

---

## 📌 Objetivo

Permitir autenticação segura com o GitHub sem uso de usuário/senha, utilizando criptografia assimétrica (SSH).

---

## 🧱 Pré-requisitos

- Git instalado
- OpenSSH disponível (`ssh -V`)
- Conta no GitHub

---

## 📁 Estrutura esperada

As chaves ficam no diretório:

C:\Users\SEU_USUARIO.ssh


---

## 🔑 1. Criar diretório `.ssh` (se não existir)

```
mkdir $env:USERPROFILE\.ssh
```

🔐 2. Gerar a chave SSH (padrão recomendado)
```
ssh-keygen -t ed25519 -C "seu-usuario-maquina" -f C:\Users\SEU_USUARIO\.ssh\id_ed25519_nome
```

Durante o processo:

- Pressione Enter para confirmar o caminho

- Defina uma passphrase (recomendado)

📂 3. Arquivos gerados

id_ed25519_ultron        → chave privada (NUNCA compartilhar)
id_ed25519_ultron.pub    → chave pública (usar no GitHub)

📋 4. Copiar chave pública
```
Get-Content C:\Users\SEU_USUARIO\.ssh\id_ed25519_nome.pub
```
Copie toda a linha gerada.

🌐 5. Adicionar no GitHub

- Acesse: Settings → SSH and GPG Keys

- Clique em: New SSH key

- Preencha:

  - Title: nome identificável (ex: ultron)

  - Key type: Authentication Key

  - Key: cole a chave pública

- Clique em Add SSH key

⚙️ 6. Configurar o SSH (config)

Crie o arquivo:

C:\Users\SEU_USUARIO\.ssh\config


Conteúdo:

Host github.com
  HostName github.com
  User git
  IdentityFile C:\Users\SEU_USUARIO\.ssh\id_ed25519_ultron
  IdentitiesOnly yes

🧪 7. Testar conexão
ssh -T git@github.com

Resultado esperado:
Hi <seu-usuario>! You've successfully authenticated, but GitHub does not provide shell access.

📦 8. Clonar repositórios (usando SSH)
git clone git@github.com:SEU_USUARIO/REPOSITORIO.git

