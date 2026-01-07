
# Formatação de qualquer "pendrive" pelo CMD do win

abra o CMD e digite:
```bash
diskpart
```
Digite:
```bash
list disk
```

- Selecione o disco que deseje formatar:
```bash 
select disk número
```
- Formate com o comando:
```bash
clean
```
- Veja se foi formatado usando, comparando o tamanho total com o livre:
 ```bash
list disk
```
- Crie uma partição primária:
```bash
create partition primary
```
- Formate a particição com o tipo:
```bash
format fs=ntfs quick
```
- Pode ser de outro formato também:
```bash
format fs=fat32 quick
```
- Vincule uma letra ao disco formatado:
```bash
assign
```
---
## Outros:

- Ver partição:
```bash
select disk número
```
- Listar partição:
```bash
list partition
```
- Sair do diskpart
```bash
exit
```

- Criar partição de tamanho específico
```bash
create partition secundary size=4096
```
- Listar partições
```bash
list partition
```
- Deletar partições
```bash
delete partition
```
