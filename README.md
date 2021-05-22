# UBUNTU: o que fazer depois de formatar?
Lista de tarefas para executar após a instalação do Ubuntu no computador. <br/>
Versão testada: Ubuntu 18.04.5 LTS

<br/>

## 1 ➜ BAIXAR PACOTES .DEB OU SNAP
**VS Code:** https://code.visualstudio.com/download/ <br/> 
**PowerShell:** https://github.com/PowerShell/PowerShell#get-powershell <br/> 
**Spotify:** https://www.spotify.com/br/download/linux/ <br/>
**Google Chrome:** https://www.google.com/chrome/browser/desktop/

<br/>

## 2 ➜ EXECUTAR COMANDOS NO TERMINAL
	sudo apt-get update && 

	# NÃO É MAIS NECESSÁRIO # sudo apt purge ubuntu-web-launchers -y && 
	sudo apt install ubuntu-unity-desktop -y && 

	sudo apt-get update && 

	sudo apt-get install plank -y && 
	sudo apt-get install libreoffice-style-sifr -y && 
	sudo apt-get install python3-pip -y && 
	sudo apt-get install software-properties-common -y && 
	sudo apt-get install ubuntu-restricted-extras -y && 
	sudo apt-get install unace unrar zip unzip p7zip-full p7zip-rar sharutils rar -y && 
	sudo apt-get install unity-tweak-tool -y && 
	sudo apt-get install bleachbit -y && 
	sudo apt-get install git-all -y && 
	sudo apt install numix-gtk-theme numix-icon-theme -y && 
	sudo apt install curl -y && 
	sudo apt install nautilus-admin -y && 

	sudo apt-get update && 

	sudo add-apt-repository ppa:danielrichter2007/grub-customizer -y && 
	sudo add-apt-repository ppa:slimbook/slimbook -y && 
	sudo add-apt-repository ppa:qbittorrent-team/qbittorrent-stable -y && 
	sudo add-apt-repository ppa:inkscape.dev/stable -y && 
	sudo add-apt-repository ppa:plushuang-tw/uget-stable -y && 
	sudo add-apt-repository ppa:rvm/smplayer -y && 

	sudo apt-get update && 

	sudo apt-get install grub-customizer -y && 
	sudo apt-get install slimbookbattery -y && 
	sudo apt-get install qbittorrent -y && 
	sudo apt-get install inkscape -y && 
	sudo apt-get install uget -y && 
	sudo apt-get install smplayer smplayer-themes smplayer-skins -y && 
	sudo apt-get install mpv -y

> Basta copiar todas as linhas de comando acima e juntá-las em uma única linha no Sublime Text ou VS Code com o atalho `CTRL + J`. Assim será possível colocar para rodar todos comandos de uma só vez no terminal.

<br/>

## 3 ➜ CONFIGURAÇÕES
### 3.1 – Plank:
Baixar temas: https://github.com/kennyh7279/plank-themes

|  Configurações   |             …             |
|       ---        |            ---            |
|  Tema:           |  Shade                    |
|  Ícones:         |  68                       |
|  Zoom:           |  125                      |

>**Ordem:** Arquivos, Terminal, Spotify, Firefox, Chrome, VS Code, Writer, Calculadora, Monitor do Sistema, Unity Tweak, Configuraçes do Sistema

<br/>

### 3.2 – Fontes do Sistema:
|  Configurações        |            …            |
|          ---          |           ---           |
|  Fonte padrão:        |  Inter Regular, 12      |
|  Fonte de documento:  |  Inter Regular, 12      |
|  Fonte monoespaçada:  |  Maax Mono Regular, 13  |
|  Fonte de título:     |  Inter Medium, 12       |
|          ---          |           ---           |
|  Suavização:          |  RGBA                   |
|  Hinting:             |  Médio                  |

<br/>

### 3.3 – Spotify:
	sudo gedit /usr/share/applications/spotify.desktop
>**Substituir:** Exec=spotify %U <br/>
>**Por:** Exec=spotify %U --force-device-scale-factor=1.25

<br/>

### ~3.4 – Firefox (não é mais necessário):~
	about:config
>~**Substituir:** layout.css.devPixelsPerPx; -1~ <br/>
>~**Por:** layout.css.devPixelsPerPx; 1.25~

<br/>

### ~3.5 – Google Chrome (não é mais necessário):~
	sudo gedit /usr/share/applications/google-chrome.desktop
>~**Substituir:** Exec=/usr/bin/google-chrome-stable %U~ <br/>
>~**Por:** Exec=/usr/bin/google-chrome-stable --force-device-scale-factor=1.175 %U~

<br/>

### 3.6 – VS Code

	'Code Saver', 'Apercu Pro Mono', 'Anonymous Pro Minus', 'Droid Sans Mono', 'monospace', monospace, 'Droid Sans Fallback'

<br/>

### ~3.7 – Sumblime Text~

~{
"color_scheme": "Packages/Panda Syntax Sublime/Panda/panda-syntax.tmTheme",
"font_face": "Anonymous Pro Minus",
"font_size": 12,
"ignored_packages":
[
"Vintage"
],
"theme": "Adaptive.sublime-theme",
"ui_scale": 1.5
}~

<br/>

## 4 ➜ DICAS

### 4.1 – Abrir pastas como Administrador:
	sudo nautilus /usr/share/icons
> Edite a parte `/usr/share/icons` no comando acima, caso queira acessar outro diretório.

<br/>

### 4.2 – Desmontar a partição do Windows estando logado no Ubuntu:
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
> Edite a parte `“$USER”` no comando acima e digite o seu nome de usuário no Ubuntu (sem aspas).
- Fonte: http://askubuntu.com/questions/288513/cant-move-files-to-the-trash

<br/>

### 4.5 – Recuperar o GRUB perdido após uma atualização do Windows (dual boot):
	bcdedit /set "{bootmgr}" path \EFI\ubuntu\grubx64.efi
> A partir do Windows, rodar o comando acima no PowerShell como Administrador.
- Fonte: https://askubuntu.com/questions/655011/windows-10-upgrade-kills-grub-and-boot-repair-doesnt-help

<br/>
