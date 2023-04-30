
# Formatação de qualquer "pendrive" pelo CMD do win

abra o CMD e digite:
diskpart

Digite:

list disk

- Selecione o disco qu deseje formatar:
  
select disk número

- formate com o comando:
```bash
clean
```
- veja se foi formatado usando, omparando o tamanho toal com o livre:
 ```bash
list disk
```
- Crie uma partição primária:
```bash
create partition primary
```
- Format a particição com o tipo:
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