🇧🇷 README – Português (Brasil)
M17 Deep Mod Project

Projeto experimental e educacional focado em estudar profundamente o console portátil M17 (SJGAM), utilizando a placa W12-V02, explorando seus limites de hardware, software e modificações físicas.

Este projeto não é comercial, não possui releases e tem como objetivo aprendizado, pesquisa e documentação técnica inédita sobre o M17.

📌 Sobre o M17 (modelo base)

O M17 é um console portátil retrô de baixo custo, amplamente vendido no mercado chinês, com foco em emulação.

Características conhecidas:

CPU ARM Quad-core Cortex-A7 (~1.2 GHz, Rockchip RK3126 / variantes)

Sistema Linux baseado em EmuELEC (ex: EmuELEC / Spectral Elec)

Tela LCD 4.3” (480×272)

Controles analógicos simples (sujeitos a drift)

Armazenamento principal via cartão microSD

Memória interna mínima para boot/fallback (OEM)

Sem Wi-Fi ou Bluetooth nativos

Refrigeração passiva ou inexistente

🎯 Objetivos do Projeto

Estudar o processo de boot do RK3126

Entender o funcionamento da memória interna OEM vs SD

Analisar e modificar o Linux/EmuELEC

Explorar UART e comunicação serial

Implementar Wi-Fi e Bluetooth via ESP32

Criar documentação técnica que não existe publicamente

Testar limites térmicos e de hardware do console

🔧 Modificações Planejadas / Em Estudo

ESP32 (Wi-Fi + Bluetooth via UART)

Sistema de refrigeração ativa (ventoinha + dissipação)

Estudo de armazenamento interno fixo vs SD removível

Custom Firmware / CFW

Possível troca de analógicos (drift)

Modificações físicas na carcaça (custom shell)

Estudo de portas USB / OTG (se disponível)

⚠️ Aviso Importante / Riscos

⚠️ RISCO REAL DE DANO PERMANENTE

Este projeto envolve:

Soldagem direta na placa

Modificação de firmware

Alterações físicas e elétricas

Riscos incluem:

Brick do console

Superaquecimento

Perda total do dispositivo

❌ NÃO RECOMENDADO para iniciantes
Faça por sua conta e risco.

📂 Status do Projeto

Fase: Pesquisa / Estudo

Repositório: Privado

Releases: Nenhum

Documentação: Em construção

🇺🇸 README – English
M17 Deep Mod Project

An experimental and educational project focused on deep research of the M17 (SJGAM) handheld console, based on the W12-V02 board, exploring its hardware, software and physical modification limits.

This is not a commercial project. No releases are planned. The goal is learning, reverse engineering and original technical documentation.

📌 About the M17 (Base Model)

The M17 is a low-cost Chinese retro handheld console designed mainly for emulation.

Known characteristics:

ARM Quad-core Cortex-A7 CPU (~1.2 GHz, Rockchip RK3126 / variants)

Linux-based system (EmuELEC / Spectral Elec)

4.3” LCD display (480×272)

Basic analog sticks (prone to drift)

Main storage via microSD card

Minimal internal OEM memory for boot/fallback

No native Wi-Fi or Bluetooth

Passive or no active cooling

🎯 Project Goals

Study the boot process of RK3126

Understand internal OEM memory vs SD storage

Analyze and modify Linux/EmuELEC

Explore UART communication

Add Wi-Fi and Bluetooth using ESP32

Create original technical documentation for the M17

Test thermal and hardware limits

🔧 Planned / Research Modifications

ESP32 (Wi-Fi + Bluetooth via UART)

Active cooling system (fan + heatsink)

Internal fixed storage vs removable SD research

Custom Firmware (CFW)

Analog stick replacement (drift fix)

Physical mods / custom shell

USB / OTG capability research (if supported)

⚠️ Warning / Risks

⚠️ HIGH-RISK PROJECT

This project involves:

Direct soldering

Firmware modification

Physical and electrical changes

Possible risks:

Device brick

Overheating

Permanent hardware damage

❌ Not recommended for beginners
Proceed at your own risk.

📂 Project Status

Stage: Research / Study

Repository: Private

Releases: None

Documentation: In progress

Se quiser, no próximo passo eu posso:

reduzir isso pra uma versão curta

criar uma descrição de 350 caracteres

ou adaptar pra README mais “clean” estilo projeto open-source
