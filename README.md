# GotekFlashFloppy

A Gotek based PCB for Amiga computer. Can be mounted externally and internally.
Can be equipped with push buttons or with a rotary encoder. A 0.96" OLED display can be directly mounted using 4 spacers. 

A 23-pin connector can be directly soldered to the pcb. Also, with an adapter pcb (23 to 34 pin) it can be mounted internally as "classic" Gotek pcb. 
Adapter's Gerbers located in **"gff_int_adapter_rev0.zip"** archive.

## Firmware: 

Please refer to FlashFloppy's repository for the latest one: https://github.com/keirf/FlashFloppy

## MPU programming

Some early revisions of the MPU can not be programmed via DFU. It is described in an application note AN2606(chapter 16.3.2):
https://www.st.com/resource/en/application_note/cd00167594-stm32-microcontroller-system-memory-boot-mode-stmicroelectronics.pdf

As I have such early revision of the MPU, I needed to use SWD interface. Actually, DFU mode flashing was not considered in the design.

Hardware: ST-LINK V2 (Chinese clone).
The MPU supplied from ST-LINK. It is enough for programming.

![image](https://user-images.githubusercontent.com/81614352/161376170-f51de39b-b773-4ece-bd92-1ba2a78fee27.png)


Software(Windows): STM32 ST-LINK Utility. Can be downloaded here: https://www.st.com/en/development-tools/stsw-link004.html

One important note to the ST-LINK flashing method. The following steps might be required if the MPU already programmed:
1. Run the tool, select "Connect under RESET" in settings. 
2. Connect ST-Link (it provides 3.3V which is enough for the MPU programming). 
3. Short C9 (to activate RESET)
4. Press "Connect" button, 
5. Release RESET
6. Open "hex" file and program it pressing "Program Verify" button.

![image](https://user-images.githubusercontent.com/81614352/161376354-b9f38411-f5d8-49ba-a336-605454dd63c4.png)

Other HW tools can be used for the MPU programming:

- FT2232H based with OpenOCD. Very easy to build.
- J-LINK
- U-LINK


## PCB:

Two layers, 1.6mm thikness. Optimized for JLCpcb.

3D render of the pcb(Just a nice picture. Some components must be unpopulated):

![изображение](https://user-images.githubusercontent.com/81614352/147295152-706d75bf-d8f5-40ec-aabd-f7ac8d367e31.png)

Adapter board(soldered side by side to the main pcb):

![изображение](https://user-images.githubusercontent.com/81614352/147295380-0f68693d-83f9-445c-b219-cb39a0d05e49.png)


## An example of internal mount with a 3D printed frame
Adapter's (frame) STL model is in CAD folder.


![изображение](https://user-images.githubusercontent.com/81614352/149626035-84b3a01c-4d0e-413d-bd10-ca4955fdb4cc.png)


The display and rotary encoder mounted on top of the Amiga 500. Its model also in the "Cad" folder.
![изображение](https://user-images.githubusercontent.com/81614352/149626079-a46008b2-d571-40e1-984e-06d83c1680c4.png)

## As an external floppy
3D render.

![изображение](https://user-images.githubusercontent.com/81614352/151380256-0f387eae-9beb-4d54-aaa4-10b2c35eb94d.png)

The device in 3D printed enclosure. Connected to my Amiga 500
![изображение](https://user-images.githubusercontent.com/81614352/151381351-cd62bc86-be2c-4154-a5bb-29decbf1ad6e.png)

