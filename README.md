<p></p>
<p align="center"><img src="https://i.imgur.com/HJnpvwQ.png" width="200" height="48"/> EFI</p>
<p align="center">
 <a href="https://www.apple.com/macos">
  <img src="https://img.shields.io/badge/Ventura-13.4.1-informational.svg">
 </a>
 <a href="https://www.apple.com/macos">
  <img src="https://img.shields.io/badge/Sonoma-14.0%20beta3-informational.svg">
 </a>
 <a href="https://www.apple.com/macos">
  <img src="https://img.shields.io/badge/Sonoma-14.0%20beta3-informational.svg">
 </a>
 <a href="https://github.com/acidanthera/OpenCorePkg">
  <img src="https://img.shields.io/badge/OpenCore-0.9.3-informational.svg">
 </a>
 <a href="https://github.com/MAGICXcmd/Ryzentosh/blob/main/LICENSE">
  <img src="https://img.shields.io/github/license/MAGICXcmd/Ryzentosh?style=flat-square">
 </a>
</p>

<h2></h2>

> I built this EFI for myself and it does not guarantee 100% work with your hardware.

> **Note** \
> Please note that for iCloud services to work correctly, you will need to reset SMBIOS.<br/>
> MLB, ROM,System Serial Number, SystemUUID sections are specifically left empty. If you are using an iGPU, I recommend using an <u>iMac20,1</u> so that there are no problems with the black screen.

<br/>

<h2 align="center">📺 Build</h2>

| **Component** | **Model**                                                                                   |
| ------------- |---------------------------------------------------------------------------------------------|
| CPU | AMD Ryzen 5 5600G @ 4.2GHz                                                                  |
| Motherboard | MSI B450M PRO-VDH PLUS - BIOS Version 7A38v9E                                               |
| GPU | <s>Palit GeForce GTX 1660 Dual</s>, but in Hackintosh <u>I use embedded graphics</u> (iGPU) |
| RAM | ADATA XPG GAMMIX D20 2 x 8GB @ 3200 MHz                                                     |
| OS disk | Team Group GX2 256GB                                                                        |
| Other disk | NVME Apacer AS2280P4 256GB + WD Blue 1 TB                                                   |
| macOS | Ventura 13.4.1 (22F770820d), Sonoma 14 beta 3 (23A5286i)                                    |
| OpenCore | 0.9.3 Release                                                                               |

<br/>

<h2 align="center">🔧 BIOS</h2>

| **Component**                  | **Model**                                         |
|--------------------------------|---------------------------------------------------|
| SVM Mode                       | Enabled                                           |
| Above 4G Decoding              | Disabled                                          |
| Resizable BAR                  | Disabled                                          |
| Integrated Graphics Controller | Auto                                              |
| IOMMU                          | Enabled                                           |
| Primary Video Adaptor (IGD)    | Int Graphics (IGD)                                |
| Frame buffer Size              | Minimum 512 mb, but I chose 4 gb because I can 🤓 |
| Boot Mode                      | UEFI                                              |
| Secure Boot and TPM            | Disabled                                          |


<br/>

<h2 align="center">🩼 Functional</h2>

- [x] macOS Ventura thanks to [dortania](https://dortania.github.io/OpenCore-Install-Guide/)
- [x] CPU by [AMD-Vanilla](https://github.com/AMD-OSX/AMD_Vanilla)
- [x] Audio by [AppleALC](https://github.com/acidanthera/AppleALC)
- [x] iGPU by [NootedRed](https://github.com/NootInc/NootedRed)
- [x] NVME by [NVMefix](https://github.com/acidanthera/NVMeFix)
- [x] iCloud
- [ ] iMessage / FaceTime / Airdrop / Handoff (crashes are observed)
- [ ] There are small graphical artifacts when working with browsers on the Chromium engine. The developer of NootedRed is aware of the problem. A crutch is built into the config, which reduces the number of graphic artifacts

<br/>

<h2 align="center">🪚 Change it for youself</h2>

Edit the core count patch to match your CPU

See [AMD Vanilla OpenCore](https://github.com/AMD-OSX/AMD_Vanilla/tree/master) or [OpenCore-Install-Guide](https://dortania.github.io/OpenCore-Install-Guide/extras/monterey.html#amd-patches)

Find the three `algrey - Force cpuid_cores_per_package`
 
- `kernel -> Patch -> 0  -> Replace` for macOS 10.13.x, 10.14.x
- `kernel -> Patch -> 1  -> Replace` for macOS 10.15.x, 11.x
- `kernel -> Patch -> 2  -> Replace` for macOS 12.x, 13.0 to 13.2.1
- `kernel -> Patch -> 3  -> Replace` for macOS 13.3
 
```
B8000000 0000 => B8 <core count> 0000 0000
BA000000 0000 => BA <core count> 0000 0000
BA000000 0090 => BA <core count> 0000 0090
BA000000 00 => BA <core count> 0000 00
```
 
| CoreCount | Hexadecimal |
| --------- | ----------- |
| 6 Core    | 06          |
| 8 Core    | 08          |
| 12 Core   | 0C          |
| 16 Core   | 10          |
| 32 Core   | 20          |
| 64 Core   | 40          |
 
For example 5600G has 6 cores
 
```
B8 06 00000000
BA 06 00000000
BA 06 00000090
BA 06 000000
```
<br/>

<h2 align="center">🧱 Scripts</h2>

> You can also use scripts.

> **Warning** \
> All scripts must be used with elevated rights! To do this, use
> ```sudo bash <name_script>.sh```
1. **hostname.sh** - change the name of your computer's name or local hostname on Mac
2. **clear-network-interfaces.sh** - helps to solve problems with en0 ethernet

<br/>

<h2 align="center">💡 Tip</h2>

 1. If you want to change the processor name, use [this](https://github.com/corpnewt/CPU-Name)
 2. If you have a 1-in-1 CPU and motherboard configuration like mine, you can use this config. If it is different, I advise you to assemble it yourself according to [the guide](https://dortania.github.io/OpenCore-Install-Guide/)

> **Note** \
> This way you will spend less time solving problems and everything will work fine. 🫡

<br/>

<h2 align="center">🏞️ Screenshot</h2>
<img src="https://i.imgur.com/qBf9Km2.png" alt="macOS Ventura">

<br/>

<img src="https://i.imgur.com/fpN7SS7.png" alt="macOS Ventura">

<br/>

<img src="https://i.imgur.com/y12giX0.png" alt="macOS Ventura">
