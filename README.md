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

Repositório: Privado

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

Repository: Private

Releases: None

Documentation: In progress
