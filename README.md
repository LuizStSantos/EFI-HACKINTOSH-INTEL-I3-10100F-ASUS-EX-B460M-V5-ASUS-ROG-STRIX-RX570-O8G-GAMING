# EFI-HACKINTOSH-INTEL-I3-10100F-ASUS-EX-B460M-V5-ASUS-ROG-STRIX-RX570-O8G-GAMING
<br/>

ℹ️ A versão atual é totalmente compatível com macOS Sonoma. OpenCore, drivers e kexts estão sempre atualizados!

## :warning: Aviso:
 **ESTE NÃO É UM GUIA!**

|**1.0**| É apenas o meu `EFI` completo para o meu hardware com base nos meus experimentos, por favor, consulte Dortania antes de fazer qualquer coisa. Não me responsabilizo por qualquer dano. Esta configuração OpenCore é otimizada para o meu hardware específico, então por favor, use-o apenas como referência ou se acontecer de você ter o mesmo hardware ou similar.|
| ------ | ----- |

|**1.1**|  Essa `EFI` e modificada para uso de um processador com final `F`, `i3-10100F`.|
| ------ | ----- |

## :camera: Pós install
![Captura de Tela 2024-08-04 às 21 50 44](https://github.com/user-attachments/assets/fe7615de-facb-4c5a-a764-01d37a306435)



## :computer: Hardware:

| **Categoria** | **Componente**                                                                    |
| ------------ | -------------------------------------------------------------------------------- |
| **CPU**      |  [Intel(R) Core(TM) i3-10100F CPU @ 3.60GHz](https://www.intel.com.br/content/www/br/pt/products/sku/203473/intel-core-i310100f-processor-6m-cache-up-to-4-30-ghz/specifications.html)                                      |
| **GPU**      |  [Asus ROG Strix RX 570 O8G Gaming](https://www.asus.com/br/supportonly/rog-strix-rx570-o8g-gaming/helpdesk_manual/)                                          |
| **RAM**      |  [XPG Gammix D30 2x8GB DDR4 3200MHz](https://www.xpg.com/pt/xpg/588)                                                    |
| **Placa mãe**  | [Asus EX-B460M-V5](https://www.asus.com/br/motherboards-components/motherboards/csm/ex-b460m-v5/) |
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

USB 3.0 Interno da placa mãe não está mapeado.

## :closed_lock_with_key: SMBIOS

Você precisará gerar seu próprio SMBIOS e configurar, já que é necessário trabalhar totalmente com o macOS. De acordo com este EFI, você pode usar os seguintes SMBIOS: iMac20,1. Observe que se o seu hardware é diferente para o mencionado aqui você tem que escolher um SMBIOS apropriado.

Use GenSMBIOS para gerar seu próprio SMBIOS exclusivo e, em seguida, copie cada parâmetro seguindo o caminho (recomendado para seguir o guia acima):

Config.plist -> PlatformInfo -> Genérico

## :closed_lock_with_key: Configuração da BIOS:

❌ Desabilitar
- Secure Boot (Others OS)
- Compatibility Support Module (CSM).
- Intel SGX
- Intel Platform Trust
- CFG Lock (MSR 0xE2 write protection)
	- Deve estar desativado, se você não conseguir encontrar a opção, então **`ENABLE`** `AppleXcpmCfgLock`. 
	- Seu hack não inicializará com `CFG-Lock` enabled.

✅ Habilitar
- VT-x
- VT-d (pode ser ativado se você definir `DisableIoMapper` como `YES` )
- Fast Boot
- Above 4G decoding. 
	- Deve estar ativado, se você não conseguir encontrar a opção, adicione `npci=0x2000` to `boot-args`. 
	- Não tenha esta opção e `npci` em `boot-args` habilitados ao mesmo tempo.
	- 2020+ BIOS Notas: Ao ativar o Above4G, o suporte de BAR redimensionável pode ficar disponível em algumas placas-mãe Z490 e mais recentes. Certifique-se de que esteja **`DISABLED`** em vez de definido como Automático.
- Hyper-Threading
- Execute Disable Bit
- EHCI/XHCI Hand-off
- SATA Mode: AHCI

## :trophy: Creditos:

[Gabriel Luchina](https://www.youtube.com/c/GabrielLuchina)

[Acidanthera](https://github.com/acidanthera)

[Dortânia](https://dortania.github.io/getting-started/)

[Maçã](https://www.apple.com/)
