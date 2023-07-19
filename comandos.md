Dicas e comandos Windows

- Verificar sistema e arquivos corrompidos:

```bash
sfc /scannow
```
- 2° método:

```bash
Dism/Onine/Cleanup-Image/ScanHealth
```

- 3° método:

```bash
Dism/Onine/Cleanup-Image/RestoreHealth
```

- Descobrir erros de sistema
```bash
// Win + R e digite:

perfmon/rel
```
---
- Melhorar desempenho:

LINHAS EM DETALHES: 

- Regedit

```bash
Windows + R digite regedit
```

- Atalho gerenciamento de disco: 

```bash
diskmgmt.msc
```

HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Control
4gb ram - 4194304
6gb ram - 6291456
8gb ram - 8388608
12gb ram - 12582912
16gb ram - 16777216
24gb ram - 25165824
32gb ram - 33554432
64gb ram - 67108864

HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Session Manager\Memory Management

alterar o arquivo: featureSettings hexadecimal: 1
criar novo arquivo DWORLD(32bits) nome: FeatureSettingsOverride hexadecimal: 3
FeaturesSettingsOverrideMask 3

HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\DriverSearching
 colocar: 0

HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\PolicyManager\default\ApplicationManagement\AllowGameDVR
value 0

HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power
 
pasta power  - neova pasta - nova key  PowerThrottling
dword32 :  PowerThrottlingOff 1 hexa

HKEY_CURRENT_USER\System\GameConfigStore
windowsCompatible to 1
behaviorMode 0
delete children and parents

HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Multimedia\SystemProfile\Tasks\Games
system e network performance
8 
6
High
High

HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Multimedia\SystemProfile
ffffffff faça 8
systemresponsiveness, 0

HKEY_CURRENT_USER\Control Panel\Desktop
windows mais responsivo e mais rápido 
MenuShowDelay 0

HKEY_CURRENT_USER\Control Panel\Accessibility\MouseKeys
flags 0
HKEY_CURRENT_USER\Control Panel\Accessibility\StickyKeys
flags 0
HKEY_CURRENT_USER\Control Panel\Accessibility\Keyboard Response
flags 0
HKEY_CURRENT_USER\Control Panel\Accessibility\ToggleKeys
flags 0

HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Schedule\Maintenance
serviço de manutenção 
new -  dword32 -  MaintenanceDisabled 1 hexa

Video explicando a configuração dos dados acima: http://bit.ly/3LmJXuuri

---

- Criar pasta invisível:

```bash
Crie uma pasta qualquer e renomeie com : ALT+0160
Clique com o botão direito na pasta, --> propriedades --->Peronalizado---> Alterar ícone ---> escolher o ícone vazio.
```

- Reabrir abas fechadas:

```bash
Ctrl + Shift + T
```

- Digitar por voz:

```bash
Windows + H
```

- Tirar print da tela:

```bash
Ctrl + Shift + S
```
 - Comandos de configurações:
```bash
Windows + R digite msconfig
```
&
```bash
Windows + R digite gpedit.msc
```

- Limpar endereços de histórico de navegação de aba anônima e normal:
Abra o CMD e digite:

```bash
ipconfig/displaydns
```

- Melhora o desenpenho apagando arquivos temporários:

```bash
Windows + R digite %temp%
```

Só apagar os arquivo temporários.

- Antivírus do windows, corrigir ameaças:

```bash
Windows + R digite MRT
```

- Atualizar todos os softwares instalado na máquina de uma vez:
Abra o CMD e digite:

```bash
WINGET UPGRADE
```

- Tipos do CMD

Alterar pra cor da fonte verde:

```bash
color -a
```

- Lista alfabética dos nomes de arquivo correspondentes em cada diretório:

```bash
dir/s
```

- Ver itens copiados:

```bash
Windows + V
```
- Corrigir erros em uma unidade de disco:
```bash
# Substitua o e: pela unidade de disco desejada.
chkdsk e: /f
```
- Verificar tamanho da memória ram do aparelho:
- 
```bash
wmic memorychip get Capacity
```



