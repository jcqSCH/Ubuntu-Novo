# UBUNTU: o que fazer depois de formatar?
Lista de tarefas para executar após a instalação do Kubuntu no computador. <br/>
Versão testada: Ubuntu 18.04.3 LTS

<br/>

## 1 ➜ BAIXAR PACOTES .DEB OU SNAP
**VS Code:** https://code.visualstudio.com/download/ <br/> 
**Spotify:** https://www.spotify.com/br/download/linux/ <br/>
**Google Chrome:** https://www.google.com/chrome/browser/desktop/

<br/>

## 2 ➜ EXECUTAR COMANDOS NO TERMINAL
	sudo apt-get update && 

	sudo apt install ubuntu-unity-desktop -y && 
	sudo apt purge ubuntu-web-launchers -y && 

	sudo apt-get update && 

	sudo apt-get install kde-l10n-ptbr -y && 
	sudo apt-get install libreoffice-l10n-pt-br -y && 
	sudo apt-get install libreoffice-style-sifr -y && 
	sudo apt-get install software-properties-common -y && 
	sudo apt-get install kubuntu-restricted-extras -y && 
	sudo apt-get install unace unrar zip unzip p7zip-full p7zip-rar sharutils rar -y && 
	sudo apt-get install bleachbit -y && 
	sudo apt-get install git-all -y && 

	sudo apt-get update && 

	sudo add-apt-repository ppa:danielrichter2007/grub-customizer -y && 
	sudo add-apt-repository ppa:nemh/systemback -y && 
	sudo add-apt-repository ppa:docky-core/stable -y && 
	sudo add-apt-repository ppa:numix/ppa -y && 
	sudo add-apt-repository ppa:qbittorrent-team/qbittorrent-stable -y && 
	sudo add-apt-repository ppa:inkscape.dev/stable -y && 
	sudo add-apt-repository ppa:rvm/smplayer -y && 

	sudo apt-get update && 

	sudo apt-get install grub-customizer -y && 
	sudo apt-get install systemback -y && 
	sudo apt-get install plank -y && 
	sudo apt-get install numix-kde-theme numix-icon-theme-circle numix-icon-theme-square -y && 
	sudo apt-get install qbittorrent -y && 
	sudo apt-get install inkscape -y && 
	sudo apt-get install smplayer smplayer-themes smplayer-skins -y && 
	sudo apt-get install mpv -y

> Basta copiar todas as linhas de comando acima e juntá-las em uma única linha no Sublime Text ou VS Code com o atalho `CTRL + J`. Assim será possível colocar para rodar todos comandos de uma só vez no terminal.

<br/>

## 3 ➜ CONFIGURAÇÕES
### 3.1 – Plank:
Baixar temas: https://github.com/KenHarkey/plank-themes/archive/master.zip

|  Configurações   |             …             |
|       ---        |            ---            |
|  Tema:           |  Shade                    |
|  Ícones:         |  68                       |
|  Zoom:           |  125                      |

>**Ordem:** Dolphin, Terminal, Spotify, Firefox, Chrome, VS Code, KCalc, Writer, Impress, KSysGuard, System Settings

<br/>

### 3.2 – Fontes do Sistema:
|  Configurações   |             …             |
|       ---        |            ---            |
|  Geral:          |  Segoe WP 14              |
|  Largura fixa:   |  Courier 10 Pitch 16      |
|  Pequena:        |  Segoe WP 13              |
|  Barra:          |  Segoe WP 13              |
|  Menu:           |  Segoe WP 14              |
|  Título:         |  Segoe WP 14 ( negrito )  |
|        …         |             …             |
|  Anti-aliasing   | Habilitado, RGB, Leve     |

<br/>

### 3.3 – Barra Superior:
>**Ordem:** Menu de Aplicativos, Gerenciador de Tarefas com Ícones, Lixeira, Área de Notificação, Bloquear/Encerrar, Relógio, Área de Trabalho

<br/>

### 3.4 – Spotify:
	sudo kate /usr/share/applications/spotify.desktop
>**Substituir:** Exec=spotify %U <br/>
>**Por:** Exec=spotify %U --force-device-scale-factor=1.25

<br/>

### 3.5 – Firefox:
	about:config
>**Substituir:** layout.css.devPixelsPerPx; 1 <br/>
>**Por:** layout.css.devPixelsPerPx; 1.25

<br/>

### 3.6 – Google Chrome:
	sudo kate /usr/share/applications/google-chrome.desktop
>**Substituir:** Exec=/usr/bin/google-chrome-stable %U <br/>
>**Por:** Exec=/usr/bin/google-chrome-stable --force-device-scale-factor=1.175 %U

<br/>

## 4 ➜ DICAS

### 4.1 – Abrir pastas como Administrador:
	kdesudo dolphin /usr/share/icons
> Edite a parte `/usr/share/icons` no comando acima, caso queira acessar outro diretório.

<br/>

### 4.2 – Desmontar a partição do Windows estando logado no Kubuntu:
	mount -o ro /dev/sda2
> Edite a parte `sda2` no comando acima se essa não for a partição em que seu Windows está instalado.
- Fonte: http://askubuntu.com/questions/335909/error-mounting-dev-sda2-at-media

<br/>

### 4.3 – Conferir o driver de vídeo instalado:
	lspci -k | grep -EA3 'VGA|3D|Display'
> O comando `VGA|3D|Display` busca as instalações dos respectivos drivers `INTEL|NVIDIA|AMD`, se existirem.

<br/>

### 4.4 – Corrigir bug da lixeira que não permite excluir arquivos:
	sudo chown -R “$USER” ~/.local/share/Trash
> Edite a parte `“$USER”` no comando acima e digite o seu nome de usuário no Kubuntu (sem aspas).
- Fonte: http://askubuntu.com/questions/288513/cant-move-files-to-the-trash
