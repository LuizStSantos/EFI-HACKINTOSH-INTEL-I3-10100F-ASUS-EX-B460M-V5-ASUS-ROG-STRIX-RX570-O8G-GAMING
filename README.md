# EFI-HACKINTOSH-INTEL-I3-10100F-EX-B460M-V5-ASUS-RX570-8GB-ASUS-ROG
EFI-HACKINTOSH-INTEL-I3-10100F-EX-B460M-V5-ASUS-RX570-8GB-ASUS-ROG
<br/>
ℹ️ The current version is fully macOS  Ventura and Sonoma compatible. OpenCore, drivers, and kexts are always up to date!

:warning: **DISCLAIMER:**
<br/>
 ESTE NÃO É UM GUIA!
É apenas o meu EFI completo para o meu hardware com base nos meus experimentos, por favor, consulte Dortania antes de fazer qualquer coisa. Não me responsabilizo por qualquer dano. Esta configuração OpenCore é otimizada para o meu hardware específico, então por favor, use-o apenas como referência ou se acontecer de você ter o mesmo hardware ou similar.


![Captura de Tela 2024-08-04 às 21 50 44](https://github.com/user-attachments/assets/fe7615de-facb-4c5a-a764-01d37a306435)



## :computer: Hardware:

| **Category** | **Component**                                                                    |
| ------------ | -------------------------------------------------------------------------------- |
| **CPU**      | Intel(R) Core(TM) i3-10100F CPU @ 3.60GHz 4-Core Processor                                        |
| **GPU**      |Asus Rog - AMD Radeon RX 570  8GB                       |
| **RAM**      | 16GB  DDR4 2666MHZ                                                   |
| **CHIPSET**  | EX-B460M-V5 [Asus](https://www.asus.com/br/motherboards-components/motherboards/csm/ex-b460m-v5/) |
| **SSD**      | 240GB Crucial BX500 SATA                                                                 |
| **Wi-Fi/BT** | BCM94360CS2 [Aliexpress](https://a.aliexpress.com/_mNf8gH6)                                                                 |
| **Adaptador PCIE X1 Wi-Fi/BT** | Adaptador PCIE X1 [Aliexpress](https://a.aliexpress.com/_mrjIsRA)                                                                 |
| **Ethernet** | Realtek RTL8111H                                                                  |
| **Audio**    | Realtek ALC887/897 (layout-id=1)                                                    |


## :white_check_mark: Working:

✅ Funcionando:
- [x] CPU power management.
- [x] Graphics acceleration.
- [x] Keyboard & Mouse
- [x] Wi-Fi.
- [x] Bluetooth.
- [x] USB ports.
- [x] HDMI video & audio output.
- [x] Ethernet.
- [x] Audio (Internal speakers, 3.5mm headphone jack).
- [x] AirDrop & Handoff.
- [x] iCloud & App Store.
- [x] iMessage & FaceTime.

## :x: Not working:
             
❌ Não funciona:

USB 3.0 Interno da placa mãe não está mapeado.


## :closed_lock_with_key: SMBIOS


🔐 SMBIOS

Você precisará gerar seu próprio SMBIOS e configurar, já que é necessário trabalhar totalmente com o macOS. De acordo com este guia, você pode usar os seguintes SMBIOS: iMac20,1. Observe que se o seu hardware é diferente para o mencionado aqui você tem que escolher um SMBIOS apropriado.

Use GenSMBIOS para gerar seu próprio SMBIOS exclusivo e, em seguida, copie cada parâmetro seguindo o caminho (recomendado para seguir o guia acima):

Config.plist -> PlatformInfo -> Genérico

## BIOS setup:

🔐 Configuração da BIOS:

❌ Desabilitar
- Secure Boot (Others OS)
- Serial/COM Port
- Parallel Port
- Compatibility Support Module (CSM).
- Thunderbolt(For initial install, as Thunderbolt can cause issues if not setup correctly)
- Intel SGX
- Intel Platform Trust
- CFG Lock (MSR 0xE2 write protection)
	- This must be off, if you can't find the option then **`ENABLE`** `AppleXcpmCfgLock`. 
	- Your hack will not boot with `CFG-Lock` enabled.

✅ Habilitar
- VT-x
- VT-d
- Fast Boot
- Above 4G decoding. 
	- This must be on, if you can't find the option then add `npci=0x2000` to `boot-args`. 
	- Do not have both this option and `npci` on `boot-args` enabled at the same time.
	- 2020+ BIOS Notes: When enabling Above4G, Resizable BAR Support may become an available on some Z490 and newer motherboards. Please ensure this is **`DISABLED`** instead of set to Auto.
- Hyper-Threading
- Execute Disable Bit
- EHCI/XHCI Hand-off
- SATA Mode: AHCI

## Credits:

Créditos:

[Gabriel Luchina](https://www.youtube.com/c/GabrielLuchina)

[Acidanthera](https://github.com/acidanthera)

[Dortânia](https://dortania.github.io/getting-started/)

[Maçã](https://www.apple.com/)
