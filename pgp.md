
# Instruções de uso de chaves PGP/GPG

Video de apoio: `https://www.youtube.com/watch?v=s-QwOTsy2o0`

Aborda procedimentos comuns como:

- Importar chave pública

```bash
gpg --import PGP_public_key.asc

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