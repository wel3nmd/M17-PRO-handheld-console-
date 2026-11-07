🇧🇷 README – Português (Brasil)
M17 Deep Mod Project

Projeto experimental e educacional focado em estudar profundamente o console portátil M17 (SJGAM), utilizando a placa W12-V02, explorando seus limites de hardware, software e modificações físicas.

Este projeto não é comercial, não possui releases e tem como objetivo aprendizado, pesquisa, reverse engineering e documentação técnica inédita sobre o M17.

📌 Sobre o M17 (modelo base)

O M17 é um console portátil retrô de baixo custo, amplamente vendido no mercado chinês, com foco em emulação via Linux.

Características conhecidas

CPU ARM Quad-core Cortex-A7 (~1.2 GHz, Rockchip RK3126 / variantes)

Sistema Linux baseado em EmuELEC (ex: EmuELEC / Spectral Elec)

Tela LCD 4.3” (480×272)

Controles analógicos simples (sujeitos a drift)

Armazenamento principal via cartão microSD

Cartão fornecido de fábrica possui baixa durabilidade (falhas recorrentes em poucos meses)

Memória interna mínima para boot / fallback OEM

Sem Wi-Fi ou Bluetooth nativos (hardware capado para multiplayer ou recursos online)

Refrigeração passiva ou inexistente, resultando em aquecimento elevado durante uso prolongado

🎯 Objetivos do Projeto

Estudar o processo de boot do RK3126

Entender o funcionamento da memória interna OEM vs armazenamento em SD

Analisar e modificar o Linux / EmuELEC

Explorar UART, pinos de debug e comunicação serial

Implementar Wi-Fi e Bluetooth via ESP32

Investigar possibilidade de armazenamento interno fixo

Criar documentação técnica que não existe publicamente

Testar limites térmicos, elétricos e de hardware do console

🔧 Modificações Planejadas / Em Estudo

ESP32 (Wi-Fi + Bluetooth via UART)

Sistema de refrigeração ativa (ventoinha + dissipadores)

Estudo de SD soldado / armazenamento interno fixo

Custom Firmware / CFW

Estudo de dual-storage (SD sistema + SD jogos)

Possível troca de analógicos (drift)

Modificações físicas na carcaça (custom shell)

Investigação de USB / OTG (se disponível no hardware)

Análise de consumo energético e bateria

⚠️ Aviso Importante / Riscos

⚠️ RISCO REAL DE DANO PERMANENTE

Este projeto envolve:

Soldagem direta na placa

Modificação de firmware e bootloader

Alterações físicas, térmicas e elétricas

Riscos incluem:

Brick irreversível do console

Superaquecimento de componentes

Curto-circuito e perda total do dispositivo

❌ NÃO RECOMENDADO para iniciantes
Faça por sua conta e risco.

📂 Status do Projeto

Fase: Pesquisa / Estudo

Repositório: Publico (projeto em desenvolvemento por motivos de dinheiro)

Releases: Nenhum

Documentação: Em construção

Objetivo atual: mapear hardware e validar hipóteses

🇺🇸 README – English
M17 Deep Mod Project

An experimental and educational project focused on deep research of the M17 (SJGAM) handheld console, based on the W12-V02 board, exploring its hardware, software and physical modification limits.

This is not a commercial project. No releases are planned. The goal is learning, reverse engineering and original technical documentation.

📌 About the M17 (Base Model)

The M17 is a low-cost Chinese retro handheld console designed mainly for Linux-based emulation.

Known characteristics

ARM Quad-core Cortex-A7 CPU (~1.2 GHz, Rockchip RK3126 / variants)

Linux-based system (EmuELEC / Spectral Elec)

4.3” LCD display (480×272)

Basic analog sticks (prone to drift)

Main storage via microSD card

Factory SD cards show low reliability and short lifespan

Minimal internal OEM memory for boot / fallback

No native Wi-Fi or Bluetooth

Passive or no active cooling, causing high operating temperatures

🎯 Project Goals

Study the RK3126 boot process

Understand OEM internal memory vs SD storage

Analyze and modify Linux / EmuELEC

Explore UART and serial debug interfaces

Add Wi-Fi and Bluetooth using ESP32

Research internal fixed storage solutions

Create original technical documentation

Test thermal, electrical and hardware limits

🔧 Planned / Research Modifications

ESP32 (Wi-Fi + Bluetooth via UART)

Active cooling system (fan + heatsinks)

Internal fixed storage vs removable SD research

Custom Firmware (CFW)

Dual-storage architecture research

Analog stick replacement (drift fix)

Physical mods / custom shell

USB / OTG capability research

Power consumption and battery analysis

⚠️ Warning / Risks

⚠️ HIGH-RISK PROJECT

This project involves:

Direct soldering

Firmware and bootloader modification

Physical, thermal and electrical changes

Possible risks:

Irreversible device brick

Overheating

Permanent hardware damage

❌ Not recommended for beginners
Proceed at your own risk.

📂 Project Status

Stage: Research / Study

m17_tools
Development/research repo for M17 console

Technical specs
CPU: Rockchip RK3126C
RAM: 256MB DDR3
Screen: 4.3 inches 480x272
Ports: USB-C power/data, headphone jack 3.5mm, microSD slot
Buttons: volume +/-, power, gamepad buttons
Speaker: 1 speaker
Custom firmware (RukaCFW Retroarch)

Default system structure
Factory system is installed within this partition scheme:

NO  LBA       Name                
00  00004000  uboot
01  00006000  trust
02  00008000  misc
03  0000A000  boot
04  0001A000  recovery
05  0002A000  backup
06  0003A000  oem
07  00102000  rootfs
08  00202000  userdata
uboot and trust follow RK norm
misc, backup and oem partitions are empty
boot and recovery are Android-scheme boot images. boot has no ramdisk included, recovery seems to not be used in a normal boot process.
rootfs contains a custom-built Buildroot Linux system. Using an script at /etc/init.d, em_ui.sh is launched if it's located under SD card mount point, otherwise /usr/bin/game is launched.
userdata, despite being mounted, seems to not be used at the current stage.
SD card contains default "emulationstation" binary, config files and ROMs, but whole system is installed on internal memory.

Loader mode
Connect device to PC with USB cable, keep volume down button pressed, then power on the device.

Recovery?? mode
Keep volume down pressed, power on the device. Stuck at Loading... screen, no interface through USB.

ADB access
Place files under ADB folder on this repo on the root folder of your SD card. Turn on the device with SD card inserted, then connect with your computer and list adb devices.

Root access
Root is the default user. Anything you include in em_ui.sh file under sdcard root folder will run as root (like the ADB-enabling script).

Firmware backup
Using rkdeveloptool, rkloader or any other Rockchip-focused tool will only properly backup the first 32MB of flash, due to a bug? in device uboot. Anything beyond this point will be invalid data. But as long as we have ADB shell and root permissions...

dd if=/dev/mmcblk1 of=/sdcard/backup.img
Emulationstation binaries
By default, an emulationstation binary on sdcard root is launched. Modifying em_ui.sh and pointing it to run "emulationstation" from system path instead of the sdcard path "/sdcard/emulationstation" will launch the binary present under /usr/bin, whose biggest difference is a new option under EmulationStation settings; Sound options.

EmulationStation Settings
Both "emulationstation" binaries present on this system have been built without normal user settings integrated (on code), so there is no way of "unlocking" options through es_settings.xml or similar methods.

Booting with no SD card
Booting device with no SD card inserted will display a basic emulator interface with some NES games. This happens when /sdcard/em_ui.sh script is not present, and /usr/bin/game is launched instead.

Retroarch cores in userdata partition
In general, there is a lot of folders and files on SD card and system rootfs with no particular use or reason, probably things left from manufacturer tests. In this category we can find some roms and Retroarch cores under /userdata path. Cores can be manually launched, but they are prone to crash.

Running other systems on M17
Technically there are no limitations on running another system on this device, as long as someone takes the time to make a port for this platform. Internal flash is writable using rkdeveloptool or even Rockchip proprietary tools, and we have a proper backup of the original content. So given the similarity of this system to Powkiddy A12/A13 or PS5000, that should be the way to go.

You could give a try to this, no guarantees

UART interface
Three points indicated, square one is GND

Force Maskrom mode
Short circuit this test point with GND

Debugging with UART while booting from SD card
It's impossible, as some CPU bus is shared between UART and SD card, so logging text is corrupted with SD card activity electrical noise...

Recovering from a bad flash
Device recovery

My first experience recovering this device, do not follow this procedure

Repository: Public

Releases: None

Documentation: In progress
