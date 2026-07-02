# SabhyaPad

This is my own MacroPad, called **SabhyaPad**! It has 6 buttons that can easily be customized using QMK. Using it is really simple: just plug a USB-C cable into your computer, allow it to connect, and then start using it.

<img width="1202" height="802" alt="image" src="https://github.com/user-attachments/assets/5c3a187a-51d2-4c51-a3fa-b85cd888f4c1" />

## Here is a [video](https://youtu.be/60F119tDTQQ) of it on YouTube!!! I accidentally put the wrong link in the demo section actually...

I made this so that my life is easier. Currently, it is configured to do this...

<img width="145" height="98" alt="Screenshot 2026-05-24 at 6 02 34 PM" src="https://github.com/user-attachments/assets/16749f90-6267-47b6-a7e4-e2aabe7f8d18" />

## BOM
|Item                    |Quantity|Remarks                                       |Unit Price 1 (INR)|Order Quantity|Order Unit Price (INR)|Order Unit Price (Est. USD)|Link To Buy                                                                                                                           |
|------------------------|--------|----------------------------------------------|------------------|--------------|----------------------|---------------------------|--------------------------------------------------------------------------------------------------------------------------------------|
|Switches                |6       |Switches of MX style.                         |₹93.18            |6             |₹93.18                |$1.00                      |https://www.mouser.in/ProductDetail/CHERRY/MX1A-L1NN?qs=F5EMLAvA7IDlALNAurZTXA%3D%3D                                                  |
|Seeed Studio Xiao RP2040|1       |Main Chip.                                    |₹464.97           |1             |₹464.97               |$4.90                      |https://www.mouser.in/ProductDetail/Seeed-Studio/102010630?qs=sqEgtWRSLJ0HHL%252BkmwiGyA%3D%3D                                        |
|Blank DSA keycaps       |6       |Blank DSA keycaps of black colour(3d printed).|₹2.13             |6             |₹12.75                |$0.13                      |Own 3d printer or print-legion                                                                                                        |
|PCB                     |1       |Main PCB.                                     |₹1112.00          |1             |₹95.25                |$1.00                      |allpcb.com                                                                                                                            |
|M3x16mm screws          |4       |Screws.                                       |₹12.27            |4             |₹49.09                |$0.51                      |https://robokits.co.in/robot-parts/nut-bolts-standoffs/mushroom-head-bolts/m3-x-16-mm-ss-bolt-precision-stainless-steel-304-moq-25-pcs|
|M3 nuts                 |4       |Nuts                                          |₹1.18             |4             |₹4.72                 |$0.05                      |https://robokits.co.in/robot-parts/nut-bolts-standoffs/nuts/m3-nuts-304-stainless-steel-moq-50-pcs                                    |


## Hardware

This is the schematic of my PCB...

<img width="545" height="386" alt="Screenshot 2026-05-24 at 6 05 46 PM" src="https://github.com/user-attachments/assets/70550790-5a9b-4d93-9fb3-b33b66891bd4" />

And this is what my PCB design looks like...

<img width="1342" height="1310" alt="image" src="https://github.com/user-attachments/assets/9090c282-6e9f-4d26-bcaa-d01cc373c261" />

### 3D Render of PCB

<img width="1064" height="616" alt="image" src="https://github.com/user-attachments/assets/b9bcddda-a231-4e5e-9894-024474978a85" />

## 3D Models

Please note that I will add USB-C port after I receive the PCB and can confirm the measurements

### Case Render(SabhyaPad Case Assembled)

<img width="843" height="536" alt="Screenshot 2026-06-10 at 11 30 27 PM" src="https://github.com/user-attachments/assets/f8b7894e-f188-406c-ae61-83ce9adb4cd0" />


### Cut Case Render(SabhyaPad Case Cut)

<img width="874" height="528" alt="Screenshot 2026-06-10 at 11 31 21 PM" src="https://github.com/user-attachments/assets/1e93eed8-a6d7-47dd-9058-49b9e7e0bbc5" />


### Final Render(no keycaps)

<img width="846" height="555" alt="Screenshot 2026-06-10 at 11 29 30 PM" src="https://github.com/user-attachments/assets/937e7dfa-f806-4e3a-843d-dea7589cda09" />


---

# Assembly

For assembly:
1. 3D Print the case cut file.
2. Take your soldered PCB and push it into the top part. It will click and then it will be attached.
3. Take the bottom part and put it at the bottom.
4. Use M3x16mm screws and the M3 nuts to enclose it.

# Firmware

The SabhyaPad firmware is based on **QMK Firmware** and is located in:

```text
FIRMWARE/sabhyapad
```

## Requirements

Install **QMK MSYS** from:

https://qmk.fm

After installation, open QMK MSYS and verify it is installed correctly:

```bash
qmk --version
```

## Setting Up QMK

Clone and set up QMK Firmware:

```bash
qmk setup
```

## Installing SabhyaPad

Navigate to the keyboards directory:

```bash
cd qmk_firmware/keyboards
```

Clone this repository:

```bash
git clone https://github.com/SabhyaAggarwal/SabhyaPad.git
```

## Building the Firmware

Return to the QMK root directory:

```bash
cd ../..
```

Compile the firmware:

```bash
qmk compile -kb sabhyapad -km default
```

Or:

```bash
make sabhyapad:default
```

## Firmware Output

A successful build will generate:

```text
sabhyapad_default.uf2
```

Since SabhyaPad uses an **RP2040** microcontroller, the firmware is generated in UF2 format.

## Flashing the Firmware

1. Hold the **BOOTSEL** button while plugging the keyboard into your computer.
2. A drive named **RPI-RP2** will appear.
3. Drag and drop:

```text
sabhyapad_default.uf2
```

onto the drive.

The keyboard will automatically reboot and start running the new firmware.

## Updating

Pull the latest changes:

```bash
cd qmk_firmware/keyboards/SabhyaPad
git pull
```

Rebuild:

```bash
cd ../..
qmk compile -kb sabhyapad -km default
```

## Troubleshooting

Check your QMK installation:

```bash
qmk doctor
```

Clean and rebuild:

```bash
qmk clean
qmk compile -kb sabhyapad -km default
```

List available keymaps:

```bash
qmk list-keymaps -kb sabhyapad
```

## Quick Start

```bash
qmk setup

cd qmk_firmware/keyboards
git clone https://github.com/SabhyaAggarwal/SabhyaPad.git

cd ../..

qmk compile -kb sabhyapad -km default
```

### Specifications

- MCU: RP2040
- Switches: 6 Mechanical Switches
- Firmware: QMK
- Connector: USB-C
- Firmware Format: UF2
