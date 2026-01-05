
# Instruções de uso de chaves PGP/GPG

Video de apoio: `https://www.youtube.com/watch?v=s-QwOTsy2o0`

Aborda procedimentos comuns como:

- Criar par de chaves PGP/GPG

```bash
gpg --full-generate-key

```

- Importar chave pública

```bash
gpg --import PGP_public_key.asc

// ou

gpg --import "D:/programas/SECRET.asc"


```
- verificar assinatura digital

```bash
gpg --verify "Sua_assinatura.exe.sig" "Seu_arquivo.exe"

```
- Outro exemplo para verificar assinatura digital:

```bash
gpg --verify "Assinatura.asc" "Seu_arquivo.exe"

```

- Ver chaves públicas importadas

```bash
gpg --list-keys

```

- Editar confiança de chave

```bash
gpg --edit-key 5069A233D55A0EEB104A5FC3821ACD02680D16DE

```

No prompt do GPG:
```bash
trust
5
y
quit
```

# 🔐 Tutorial Completo: Usando Chaves GPG com GitHub

1️⃣ Verificar se você já tem uma chave GPG

No terminal:

```bash
gpg --list-secret-keys --keyid-format=long
```

Se aparecer algo assim:
```bash
sec   rsa4096/ABCD1234EFGH5678 2024-01-01 [SC]
      Key fingerprint = XXXX XXXX XXXX XXXX
uid   [ultimate] Seu Nome <pessoal@email.com>
```

→ ótimo, você já tem chave.

Se aparecer nada, você precisa criar ou importar uma chave (veja passo 2).

2️⃣ Criar ou importar uma chave GPG

🔹 A) Criar nova chave
```bash
gpg --full-generate-key
```

Escolha:

Tipo: RSA and RSA

Tamanho: 4096

Expiração: sua escolha (ou sem expirar)

Nome e email: seu email principal

🔹 B) Importar chave existente

Se você já tinha uma chave em outro PC:


```bash
gpg --import privatekey.asc
```

Depois verifique com:

```bash
gpg --list-secret-keys --keyid-format=long
```
3️⃣ Adicionar múltiplos emails à chave (opcional)

O KEY_ID é a parte depois da barra na saída do passo 1 (ex: ABCD1234EFGH5678).
Checar seu KEY_ID:
```bash
gpg --list-secret-keys --keyid-format=long
```
você verá algo como:
```bash
sec   rsa4096/ABCD1234EFGH5678 2024-01-01 [SC]
      Key fingerprint = XXXX XXXX XXXX XXXX
uid   [ultimate] Seu Nome <
```
onde ABCD1234EFGH5678 é o KEY_ID.

Se você quer manter email pessoal e adicionar outro por exemplo do trabalho:

```bash
gpg --edit-key SEU_KEY_ID
````

No prompt do GPG:
```bash
gpg> adduid
Real name: Seu Nome
Email address: trabalho@empresa.com
Comment: (opcional)
gpg> save
```

Verifique:

```bash
gpg --list-keys
```

Deve mostrar todos os emails (UIDs).

4️⃣ Exportar e adicionar chave pública ao GitHub

Exportar chave pública em formato ASCII:

```bash
gpg --armor --export SEU_KEY_ID
```

Copie todo o conteúdo.

No GitHub:

Settings → SSH and GPG keys → New GPG key

Cole a chave pública

Salve

Agora o GitHub pode verificar seus commits.

5️⃣ Configurar Git para usar a chave
🔹 Informar qual chave usar

```bash
git config --global user.signingkey SEU_KEY_ID
```
```bash
git config --global gpg.program gpg
```

🔹 Escolher email para commits

Global (todos os repositórios):

```bash
git config --global user.email "email@da-chave.com"
```


Por repositório (se quiser email diferente):

```bash
git config user.email "outro@email.com"
```

🔹 Ativar assinatura automática de commits

```bash
git config --global commit.gpgsign true
```

6️⃣ Configuração extra no Windows / Git Bash

Para evitar erros de “gpg failed to sign the data”:

```bash
export GPG_TTY=$(tty)
```


Coloque no ~/.bashrc ou ~/.bash_profile para não precisar digitar toda hora.

7️⃣ Testar commits assinados

Faça um commit:

```bash
git commit -m "Teste de commit assinado"
```
Todos os commits agora serão assinados automaticamente.

Se quiser desativar assinatura automática:

```bash
git config --global commit.gpgsign false
```
aí para assinar commits manualmente, específicos use:

```bash
git commit -S -m "mensagem"
```

Se pedir senha da chave → correto!

No GitHub → commit deve aparecer como ✅ Verified

8️⃣ Assinar tags (opcional, recomendado para releases)
```bash
git tag -s v1.0.0 -m "Release v1.0.0"
git push --tags
```

GitHub mostrará a tag como Verified.

9️⃣ Dicas importantes

🔹 Uma chave pode ter vários emails. Todos podem assinar commits.

🔹 Não crie várias chaves sem necessidade — use UIDs para separar emails.

🔹 Backup da chave privada é essencial (por exemplo, em pendrive criptografado).

🔹 Para commits antigos, se mudar email, precisa de git rebase (cuidado).

🔹 Se usar GitHub CLI (gh), ele detecta automaticamente chaves GPG.