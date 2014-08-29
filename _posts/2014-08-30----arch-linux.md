---
layout: post
title: "Отключение дискретной видеокарты Arch Linux"
description: "Работая на ноутбуке с двумя видеокартами в линуксе приходится либо мерится с тем что он греется либо отключать вторую видеокарту это маленькая шпаргалка как это делать в арче"
category: 
tags: []
---
{% include JB/setup %}
#Начало
Есть официальный ман арча как это делать  [Arch Wiki](https://wiki.archlinux.org/index.php/hybrid_graphics)

 Необходимо установить модуль acpi_call-git

    yaourt -S acpi_call-git
 
он попросит установить хедеры ядра 

    sudo pacman -S linux-headers
  
выбрать подходящие ядру хедеры посмотреть текущее ядро 

    uname -a

потом выполняем команды:

    sudo modprobe acpi_call
    sudo turn_off_gpu.sh

Данная команда показывает аткой вывод:

    Trying \_SB.PCI0.P0P1.VGA._OFF: failed
    Trying \_SB.PCI0.P0P2.VGA._OFF: failed
    Trying \_SB_.PCI0.OVGA.ATPX: failed
    Trying \_SB_.PCI0.OVGA.XTPX: failed
    Trying \_SB.PCI0.P0P3.PEGP._OFF: failed
    Trying \_SB.PCI0.P0P2.PEGP._OFF: failed
    Trying \_SB.PCI0.P0P1.PEGP._OFF: failed
    Trying \_SB.PCI0.MXR0.MXM0._OFF: failed
    Trying \_SB.PCI0.PEG1.GFX0._OFF: failed
    Trying \_SB.PCI0.PEG0.GFX0.DOFF: failed
    Trying \_SB.PCI0.PEG1.GFX0.DOFF: failed1
    Trying \_SB.PCI0.PEG0.PEGP._OFF: works!
    Trying \_SB.PCI0.XVR0.Z01I.DGOF: failed
    Trying \_SB.PCI0.PEGR.GFX0._OFF: failed
    Trying \_SB.PCI0.PEG.VID._OFF: failed
    Trying \_SB.PCI0.PEG0.VID._OFF: failed
    Trying \_SB.PCI0.P0P2.DGPU._OFF: failed
    Trying \_SB.PCI0.P0P4.DGPU.DOFF: failed
    Trying \_SB.PCI0.IXVE.IGPU.DGOF: failed
    Trying \_SB.PCI0.RP00.VGA._PS3: failed
    Trying \_SB.PCI0.RP00.VGA.P3MO: failed
    Trying \_SB.PCI0.GFX0.DSM._T_0: failed
    Trying \_SB.PCI0.LPC.EC.PUBS._OFF: failed
    Trying \_SB.PCI0.P0P2.NVID._OFF: failed
    Trying \_SB.PCI0.P0P2.VGA.PX02: failed
    Trying \_SB_.PCI0.PEGP.DGFX._OFF: failed
    Trying \_SB_.PCI0.VGA.PX02: failed
    Trying \_SB.PCI0.PEG0.PEGP.SGOF: failed
    Trying \_SB.PCI0.AGP.VGA.PX02: failed 

Важно чтоб один из них отработал и отключил видеокарту дальше необходимо все вышеперечисленное добавить в автозагрузку по мне это костыль но хз может поменяется потом.
