<p></p>
<p align="center"><img src="https://i.imgur.com/HJnpvwQ.png" width="200" height="48"/> EFI</p>
<h2></h2>
<p align="center">I built this EFI for myself and it does not guarantee 100% work with your hardware.<br/>
❗️ Please note that for iCloud services to work correctly, you will need to reset SMBIOS.<br/>
❗️❗️ The MLB, ROM,System Serial Number, SystemUUID sections are specifically left empty.<br/>
❓ If you use iGPU, I recommend configuring <u>iMac20,1</u> for correct operation.</p>

<br/>

<h2 align="center">📺 Build</h2>

| **Component** | **Model** |
| ------------- | --------- |
| CPU | AMD Ryzen 5 5600G @ 4.2GHz |
| Motherboard | MSI B450M PRO-VDH PLUS - BIOS Version 7A38v9E |
| GPU | <s>Palit GeForce GTX 1660 Dual</s>, but in Hackintosh <u>I use embedded graphics</u> (iGPU) |
| RAM | ADATA XPG GAMMIX D20 2 x 8GB @ 3200 MHz |
| OS disk | Team Group GX2 256GB |
| Other disk | NVME Apacer AS2280P4 256GB + WD Blue 1 TB |
| macOS | Ventura 13.4.1 (22F770820d) |
| OpenCore | 0.9.3 Release |

<br/>

<h2 align="center">🔧 BIOS</h2>

| **Component** | **Model** |
| ------------- | --------- |
| SVM Mode | Enabled |
| Above 4G Decoding | Auto/Disabled |
| Resizable BAR/Clever Memory Access (C.A.M) | Disabled |
| UMA Frame buffer Size | Auto|
| Integrated Graphics Controller | Auto |
| UMA Above 4G | Auto |
| IOMMU | Enabled |
| Primary Video Adaptor (IGD) | Int Graphics (IGD) |
| CSM (Compatibility Support Module) | Disabled |
| Boot Mode | UEFI |
| VRAM for iGPU | Minimum 512 mb, but I chose 4 gb because I can 🤓 |

<br/>

<h2 align="center">🩼 Functional</h2>

- [x] macOS Ventura thanks to [dortania](https://dortania.github.io/OpenCore-Install-Guide/)
- [x] CPU by [AMD-Vanilla](https://github.com/AMD-OSX/AMD_Vanilla)
- [x] USB
  by [USBToolBox](https://github.com/USBToolBox) and [dortania](https://dortania.github.io/OpenCore-Post-Install/usb/)
- [x] Audio by [AppleALC](https://github.com/acidanthera/AppleALC)
- [x] iGPU by [NootedRed](https://github.com/NootInc/NootedRed)
- [x] Bluetooth and WiFi (?) (there is no way to check, but, in theory, they should work)
- [x] NVME by [NVMefix](https://github.com/acidanthera/NVMeFix)
- [x] iCloud by [NullEthernet](https://github.com/RehabMan/OS-X-Null-Ethernet)
- [ ] iMessage / FaceTime / Airdrop / Handoff (crashes are observed)
- [ ] There are small graphical artifacts when working with browsers on the Chromium engine. The developer of NootedRed is aware of the problem. A crutch is built into the config, which reduces the number of graphic artifacts

<br/>

<h2 align="center">💡 Tip</h2>
<p>If you have a 1-in-1 CPU and motherboard configuration like mine, you can use this config. If it is different, I advise you to assemble it yourself according to <a href="https://dortania.github.io/OpenCore-Install-Guide/" target="__blank">the guide</a></p>

This way you will spend less time solving problems and everything will work fine. 🫡

<br/>

<h2 align="center">🏞️ Screenshot</h2>
<img src="https://i.imgur.com/qBf9Km2.png" alt="macOS Ventura">

<br/>

<img src="https://i.imgur.com/fpN7SS7.png" alt="macOS Ventura">

<br/>

<img src="https://i.imgur.com/y12giX0.png" alt="macOS Ventura">
