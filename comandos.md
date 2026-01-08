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

- 4° método - Verificar e corrigir erros em uma unidade de disco específica:

```bash
chkdsk F: /f /r
```
O que faz:

/f corrige erros

/r tenta recuperar setores defeituosos

---
- Descobrir erros de sistema
```bash
// Win + R e digite:

perfmon/rel
```

- Alterar letra da unidade de disco:
```bash
Win + X
```
Depois → Gerenciamento de Disco
Clique com o botão direito → Alterar letra da unidade

Remova e adicione uma nova letra, clique com o botão direito → Alterar letra da unidade

Remova e adicione uma nova letra asua preferência.

---
- Melhorar desempenho:

Linhas em detalhes para melhorar o desempenho do Windows 10/11 para jogos e uso geral.: 

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

```bash
wmic memorychip get Capacity
```
- Apagar a pasta node_modules de um projeto
```bash
rm -rf /node_modules
```

- Verificar chave de arquivo

```bash
CertUtil -hashfile C:\Users\Seu-usuario\Downloads\seu-arquivo.exe SHA256
```

- Reportar estado da bateria
  
  ```bash
  # No Cmd digite
  powercfg batteryreport
  ```
- Saber qual windows está instalado

Pressione `Win + R`

Digite: `winver`

 - Se o Hyper-V não aparecer (ativar)

Às vezes ele vem desativado.

Pressione `Win + R`

Digite:optionalfeatures

Marque:

☑ Hyper-V

☑ Ferramentas de Gerenciamento

☑ Plataforma Hyper-V

Clique em OK

Reinicie o computador.

Depois disso, procure de novo por Gerenciador do Hyper-V.

---

- Comandos de captura de tela
  
`Windows + Alt + R` → Inicia ou para a gravação de tela.

`Windows + G` → Abre a Xbox Game Bar

`Windows + Print Screen` → Captura a tela inteira e salva automaticamente a imagem na pasta Imagens > Capturas de Tela. Você verá um breve escurecimento da tela como confirmação. 

`Windows + Shift + S` → Abre a Ferramenta de Captura, permitindo que você selecione uma parte específica da tela. Após a captura, a imagem é copiada para a área de transferência, e você pode colá-la em um editor de imagens ou documento. 
`Alt + Print Screen` → Captura apenas a janela ativa, ignorando a barra de tarefas. A imagem é copiada para a área de transferência e pode ser colada em um aplicativo de edição. 

`Print Screen (PrtSc)` → Captura a tela inteira e copia a imagem para a área de transferência. Você precisará colar a imagem em um aplicativo como Paint para salvá-la.

---
## Backup de drivers instalados no Windows, em caso de formatação, você pode restaurá-los facilmente.

1 - Pressione a tecla windows, digite CMD e vai na opção de executar como administrador;
2 - Vá até a pasta raiz do usuário, conhecida como unidade C, utilizando o comando "c..", até chegar na unidade C;
3 - Criar uma pasta para armazenar os drivers, utilizando o comando `mkdir BKP_DRIVERS` (BKP_DRIVRES - é o nome dado a pasta);
4 - Copiar e colar no CMD o seguinte comando:
```bash 
dism /online /export-driver /destination:C:\BKP_DRIVERS
```
5 - Aguarde o processo ser concluído, e verifique na unidade C a pasta BK

6 - DRIVERS, onde estarão todos os drivers salvos.
Pronto! Agora você tem um backup completo dos drivers do seu sistema.

7 - Para restaurar os drivers após a formatação, siga estes passos:
- Pressione a tecla windows, digite CMD e vá na opção de executar como administrador;   

- Vá até a pasta onde os drivers estão salvos, utilizando o comando "cd C:\BKP_DRIVERS";
- 
- Forma 1:
- Copiar e colar no CMD o seguinte comando:

```bash
dism /online /add-driver /driver:C:/Users/VAIO/drivers_vaio /recurse
```
- Forma 2:
Instalar manualmente pelo Gerenciador de Dispositivos

Útil se apenas um dispositivo estiver sem driver.

Pressione Win + X → Gerenciador de Dispositivos

Clique com o botão direito no dispositivo com erro ⚠️

Atualizar driver

Procurar drivers no computador

Selecione a pasta onde os drivers estão salvos(exemplo abaixo):

```bash
C:\Users\VAIO\drivers_vaio

```

Marque “Incluir subpastas”

Avançar.

- Forma 3:
Usando PowerShell

Alternativa moderna ao DISM:

Abra o PowerShell como Administrador e execute:

```bash
pnputil /add-driver C:\Users\VAIO\drivers_vaio\*.inf /subdirs /install
```

Finalize e reinicie o computador.

---