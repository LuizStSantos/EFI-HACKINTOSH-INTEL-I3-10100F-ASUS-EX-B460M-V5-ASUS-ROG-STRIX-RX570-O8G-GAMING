# EFI-HACKINTOSH-INTEL-I3-10100F-ASUS-EX-B460M-V5-ASUS-ROG-STRIX-RX570-O8G-GAMING
<br/>

ℹ️ A versão atual é totalmente compatível com macOS Sonoma. OpenCore, drivers e kexts estão sempre atualizados!

## :warning: Aviso:
 **ESTE NÃO É UM GUIA!**

|**1.0**| É apenas o meu `EFI` completo para o meu hardware com base nos meus experimentos, por favor, consulte Dortania antes de fazer qualquer coisa. Não me responsabilizo por qualquer dano. Esta configuração OpenCore é otimizada para o meu hardware específico, então por favor, use-o apenas como referência ou se acontecer de você ter o mesmo hardware ou similar.|
| ------ | ----- |

|**1.1**|  Essa `EFI` e modificada para uso de um processador com final `F`, `i3-10100F`.|
| ------ | ----- |

## :camera: Pós install:


![POSINSTALL](https://github.com/user-attachments/assets/85839332-9565-4e4f-a0bf-36053aa65176)


## :computer: Hardware:

| **Categoria** | **Componente**                                                                    |
| ------------ | -------------------------------------------------------------------------------- |
| **CPU**      |  [Intel(R) Core(TM) i3-10100F CPU @ 3.60GHz](https://www.intel.com.br/content/www/br/pt/products/sku/203473/intel-core-i310100f-processor-6m-cache-up-to-4-30-ghz/specifications.html)                                      |
| **GPU**      |  [Asus ROG Strix RX 570 O8G Gaming](https://www.asus.com/br/supportonly/rog-strix-rx570-o8g-gaming/helpdesk_manual/)                                          |
| **RAM**      |  [XPG Gammix D30 2x8GB DDR4 3200MHz](https://www.xpg.com/pt/xpg/588)                                                    |
| **Placa mãe**  | [Asus EX-B460M-V5](https://www.asus.com/br/motherboards-components/motherboards/csm/ex-b460m-v5/) BIOS 1401|
| **SSD**      | [240GB Crucial BX500 SATA](https://br.crucial.com/products/ssd/bx500-ssd)                                                       |
| **Wi-Fi/BT** | [BCM94360CS2](https://a.aliexpress.com/_mNf8gH6)                                                                 |
| **Adaptador PCIE X1 Wi-Fi/BT** | [Adaptador PCIE X1](https://a.aliexpress.com/_mrjIsRA)                                                                 |
| **Ethernet** | Realtek RTL8111H                                                                  |
| **Audio**    | Realtek ALC887/897 (layout-id=1)                                                    |


## :white_check_mark: Funcionando:

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

## :x: Não funciona:

❌ Desabilitado 
- USB 3.0 Interno da placa mãe não está mapeado.

## :closed_lock_with_key: SMBIOS

iMac20,1 (usado nesta EFI)

Use GenSMBIOS para gerar seu próprio SMBIOS exclusivo e, em seguida, copie cada parâmetro seguindo o caminho (recomendado para seguir o guia): [GenSMBIOS](https://dortania.github.io/OpenCore-Post-Install/universal/iservices.html#using-gensmbios)

Config.plist -> PlatformInfo -> Genérico

## :closed_lock_with_key: Configuração da BIOS:

:warning: Aviso:
A Configuração da BIOS e baseada nas opções da placa mãe `Asus EX-B460M-V5 Versão da BIOS 1401`

❌ Desabilitar

- Secure Boot
	- Boot\Secure Boot
  		- **OS Type** `Others OS`.

- Fast Boot
	- Boot\Boot Configuration
		- **Fast Boot** `Disabled`.


- Compatibility Support Module (CSM).
	- Boot\CSM (Compatibility Support Module)
		- **Launch CSM** `Disabled`.

- Intel SGX
	- Advanced\CPU Configuration
		- **Software Guard Extensions (SGX)** `Disabled`.

- Intel Platform Trust
	- Advanced\Trusted Computing 
		- **Secure Device Support** `Disabled`.

- TPM
	- Advanced\PCH-FW Configuration
		- **TPM Device Selection** `Enable Discrete TPM`.
	- Você pode ativar no caso se você usa dual Boot, não interfere em nada, mas se você não usa recomendo deixar desabilitado.

- CFG Lock (MSR 0xE2 write protection)
	- Já vem desativado de fabrica.


✅ Habilitar

- VT-x
	- Já vem ativado de fabrica.

- VT-d ( Pode ser ativado se você definir `DisableIoMapper` como `YES` )
	- Advanced\CPU Configuration
		- **VT-d** `Enabled`.

- VMX
	- Advanced\CPU Configuration
		- **Intel (VMX) Virtualization Technology** `Enabled`.

- Above 4G decoding. 
	- Adicione `npci=0x2000` ao `boot-args`. 

- Hyper-Threading
	- Advanced\CPU Configuration
		- **Hyper-Threading** `Enabled`.

- EHCI/XHCI Hand-off
	- Advanced\USB Configuration
		- **XHCI Hand-off** `Enabled`.

- SATA Mode: AHCI
	- Advanced\PCH Storage Configuration
		- **Sata mode Selection** `AHCI`.


## :trophy: Creditos:

[Gabriel Luchina](https://www.youtube.com/c/GabrielLuchina)

[Acidanthera](https://github.com/acidanthera)

[Dortânia](https://dortania.github.io/getting-started/)

[Apple](https://www.apple.com/)
