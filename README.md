# ScanRede

ShellScrip para verificar a quantidade de dispositivos conectados na rede

```
#!/bin/bash
#
#===============================================================================
#
# File...........: scanrede.sh
# Title..........: ScanRede
# Program........: Shell Code -  GNU/Linux
#
# Description....: Verifica o numero de dispositivos na rede
#
# Copyright......: Copyright(c) 2024 / @Diego.Casagranda - HackLab
# License........: GNU GENERAL PUBLIC LICENSE - Version 3, 29 June 2007
#
# Author.........: Diego Casagranda
# E-Mail.........: diego.casagranda@mail.ru
#
# Dependency.....: nmap
#
# Date...........: 05/06/2024
# Update.........: None
#
# Version........: 0.1.0
#
#===============================================================================
#
# ###########
# # History #
# ###########
#
#     05/06/2024 : Criação do codigo
#
#===============================================================================

# pega o numero de dispositivos na rede 192.168.0.1
dispositivos=`nmap -sP 192.168.0.1/24 | tail -n1 | awk '{print $6}' | tr -d '()' `

# String para exibição na tela
numero_dispositivos="Atualmente existem $dispositivos dispositivos conectados a sua rede."

# Exibe na tela a saida
echo "$numero_dispositivos"

```

Você pode movelo para /usr/bin e disponibilizar o comando para todos os usuarios
```
# copiar para /usr/bin
sudo cp scanrede.sh /usr/bin/

# Permição para usuarios e grupos
sudo chmod 777 /usr/bin/scanrede.sh

# Tornalo executavel
sudo chmod +x /usr/bin/scanrede.sh
```
