# High Plains Drifter v2 — handwired keyboard assembly guide

![image](images/hpd_hw_bg_00.png)

## Before you start

This guide describes how to build the High Plains Drifter v2 keyboard without PCBs and without complex soldering. It is intended for users who want to assemble the curved HPD v2 split keyboard at home with minimal cost for parts and tools.

> ⚠️ This guide does not cover the assembly of modules for HPD v2, because handwired mounting of components and connectors is not reliable for modules.

## Useful links

- [HPD v2 case for 3D printing (STL)](stl)
- [HPD v2 case model for editing (STEP)](step)
- [HPD v2 circuit schematic](https://oshwlab.com/yuriiq/hpdv2)
- [Firmware](https://github.com/ergohaven/keymap_hub)
- [QMK documentation](https://docs.ergohaven.xyz/qmk/)

---

## Components

| Name | Quantity (pcs) |
| --- | ---: |
| RP2040 Zero MCU | 2 |
| USB Type-C daughterboard: 1.6mm thick | 2 |
| 1N4148 Diodes | 60 |
| 1 - 100 kOhm resistors | 2 |
| Hotswap sockets | 60 |
| Switch | 60 |
| Keycaps | 60 |
| M3x5 Inserts | 10 |
| M3x4 Screws | 10 |
| 3M bumpons (8mm) | 4 |
| Solid-core wire | ~1 meter |

---

## Tools and consumables

- Soldering iron
- Solder
- Tweezers
- Side cutters
- Screwdriver

---

## Assembly steps

### Step 1. Prepare the case, install switches and hotswaps

Print and prepare the [case](stl), heat-set the M3x5 metal inserts, and install the switches with Hotswap sockets.

![image](images/hpd_hw_bg_01_0.png)

---

### Step 2. Prepare the hotswap sockets for soldering

Next, we need to connect all hotswap sockets by columns and rows.

We will connect the rows using 1N4148 diodes. For this, bend the lead on the anode side and trim it, leaving 5-7 mm.

![image](images/hpd_hw_bg_02_1.png)

In this guide we will connect the columns with wires. Prepare them in the required way (but you can choose another connection method, for example, use the trimmed diode leads).

![image](images/hpd_hw_bg_02_0.png)

---

### Step 3. Solder the columns and rows

Connect the columns by soldering wires to one of the hotswap socket pins.

![image](images/hpd_hw_bg_03_0.png)
![image](images/hpd_hw_bg_03_1.png)

Next, connect the rows by soldering 1N4148 diodes with the anode to the second pin of each hotswap socket, and solder a common wire for each row.

![image](images/hpd_hw_bg_03_2.png)
![image](images/hpd_hw_bg_03_3.png)

---

### Step 4. Assemble the holders (controllers)

To assemble the holder (controller), we need two RP2040 Zero controllers, two USB Type-C daughterboards, two 1 - 100 kOhm resistors, and some wires.

Connect everything with wires according to the diagram.

![image](images/hpd_hw_bg_04_00.png)

First, solder the wires to the USB Type-C daughterboards. For convenience, it is better to use wires of different colors.

![image](images/hpd_hw_bg_04_0.png)

Then solder the USB Type-C daughterboards to the RP2040 Zero controller boards.

> ⚠️ On the left and right halves, D- and D+ **are swapped**!

**Left half:**

| USB contact | RP-ZERO pin |
|-------------|-------------|
| VCC         | 5V          |
| GND         | GND         |
| D−          | 0           |
| D+          | 1           |

![image](images/hpd_hw_bg_04_1.png)

**Right half:**

| USB contact | RP-ZERO pin |
|-------------|-------------|
| VCC         | 5V          |
| GND         | GND         |
| D−          | 1           |
| D+          | 0           |

![image](images/hpd_hw_bg_04_2.png)

Now solder the 1 - 100 kOhm resistors to the RP2040 Zero controllers. This is needed so that the computer can correctly detect which half is connected.

- **Left half:** one end of the resistor → **3V3** pin, the other → **29** pin

![image](images/hpd_hw_bg_04_3.png)

- **Right half:** one end of the resistor → **GND** pin, the other → **29** pin

![image](images/hpd_hw_bg_04_4.png)

---

### Step 5. Solder the holders (controllers) to the keyboard halves

In this step we will connect the columns and rows to the controller.

Connect everything with wires according to the diagram.

![image](images/hpd_hw_bg_05_00.png)

#### Columns (vertical key lines)

> ⚠️ Column numbering always starts from the side with the USB opening.

Solder the common wire from the **columns** to the required RP-ZERO pin:

| RP-ZERO pin | Column |
|-------------|--------|
| 28          | 1      |
| 15          | 2      |
| 14          | 3      |
| 13          | 4      |
| 12          | 5      |
| 7           | 6      |

#### Rows (horizontal key lines)

> ⚠️ Row numbering always goes from top to bottom.

| RP-ZERO pin | Row |
|-------------|-----|
| 6           | 1   |
| 5           | 2   |
| 4           | 3   |
| 3           | 4   |
| 2           | 5   |

![image](images/hpd_hw_bg_05_1.png)
![image](images/hpd_hw_bg_05_2.png)

---

### Step 6. Final steps

After soldering the controllers to the keyboard halves, it is recommended to check that the keys work correctly.

First, flash both halves:
- connect the USB-C cable from the PC to the controller. If the RPI-RP2 folder does not appear, double-click the **Reset** button on the RP2040 Zero
- copy the firmware file for **HPD v2 (no modules)** from [keymap_hub](https://github.com/ergohaven/keymap_hub) to the root of the RPI-RP2 folder
- repeat the same steps with the other half

After flashing, connect the halves with a USB-C cable and connect them to the PC, open [Vial](https://eh.works/vial), and check both halves in the **Matrix tester**.

![image](images/hpd_hw_bg_06_00.png)

<details>
<summary><strong>Possible issues and how to fix them</strong></summary>

- **The computer does not see the keyboard, the BOOT drive does not appear**
  Check the board for short circuits, inspect the 3V3, 5V and GND pins. Also check the integrity of the USB connector and its solder joints.

- **An entire column does not work**
  There is no connection between the column and the RP-ZERO. Continuity-test or visually inspect the wire from the left contact of the hot-swap socket to the required controller pin.

- **A row or part of a row does not work**
  The problem is with the diodes. Check the soldering, one or more diodes may be reversed or not fully soldered.

- **A key or several keys are stuck**
  Somewhere a diode is shorting to a column. Inspect the diode solder joints in the problematic area, look for accidental solder bridges.

- **The halves are mirrored (the left behaves like the right)**
  The resistors are soldered incorrectly. Go back to step 3 and check: on the left half the resistor goes to 3V3, on the right half it goes to GND.

</details>

If the test was successful, continue assembling the halves. Place the controller boards and the side USB-C connector into the printed [holder case](stl/handwired-holder.stl), then screw the assembled holder to the half case.

> ⚠️ To print the left [holder](stl/handwired-holder.stl), mirror the model in the slicer before printing.

On the left half

![image](images/hpd_hw_bg_06_1.png)
![image](images/hpd_hw_bg_06_2.png)

and on the right half

![image](images/hpd_hw_bg_06_3.png)
![image](images/hpd_hw_bg_06_4.png)

Then screw on the bottom covers with M3x4 screws and attach the silicone feet (five on each half).

![image](images/hpd_hw_bg_06_5.png)
![image](images/hpd_hw_bg_06_6.png)

Install the keycaps and side plugs.

![image](images/hpd_hw_bg_06_7.png)
![image](images/hpd_hw_bg_06_8.png)

### The keyboard is ready!

![image](images/hpd_hw_bg_07_0.png)

---
