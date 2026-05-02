# High Plains Drifter v2 — handwired keyboard assembly guide

![image](images/hpd_hw_bg_00.png)

## Before you start

This guide describes how to assemble the High Plains Drifter v2 keyboard without PCBs and without complex soldering. It is intended for users who want to build the curved HPD v2 split keyboard at home with minimal cost for parts and tools.

> ⚠️ This guide does not cover assembly of modules for HPD v2, because handwired mounting of components and connectors is not reliable for modules.

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
| 1N4148 diodes | 60 |
| 1 - 100 kOhm resistors | 2 |
| Hotswap sockets | 60 |
| Switches | 60 |
| Keycaps | 60 |
| M3x5 inserts | 10 |
| M3x4 screws | 10 |
| 3M bumpons (8mm) | 10 |

<details>
<summary><strong>➕ Component appearance</strong></summary>

| Component | Appearance |
| --- | --- |
| RP2040 Zero MCU | <img src="images/bom_rp2040zero.png" width="400" height=""> |
| USB Type-C daughterboard: 1.6mm thick | <img src="images/bom_usb.png" width="400" height=""> |
| 1N4148 diodes | <img src="images/bom_diodes.png" width="400" height=""> |
| 1 - 100 kOhm resistors | <img src="images/bom_resistors.png" width="400" height=""> |
| Hotswap sockets | <img src="images/bom_hotswap.png" width="400" height=""> |
| M3x5 inserts | <img src="images/bom_m3x5_insert.png" width="400" height=""> |
| M3x4 screws | <img src="images/bom_m3x4_screws.png" width="400" height=""> |
| 3M bumpons (8mm) | <img src="images/bom_bumpons.png" width="400" height=""> |

</details>

---

## Tools and consumables

- 3D printer
- Soldering iron
- Tweezers
- Side cutters
- Screwdriver
- Craft knife
- Solder
- Filament
- Solid-core wire

---

## Assembly steps

### Step 1. Prepare the case, install switches and hotswaps

Print and prepare the [case](stl) on a 3D printer, heat-set the M3x5 inserts, and install the switches and hotswap sockets.

![image](images/hpd_hw_bg_01_0.png)

<details>
<summary><strong>➕ Detailed description</strong></summary>

Remove the supports from the case.

![image](images/hpd_hw_bg_01_1.png)

Any thin plastic strands in the switch mounting slots can be melted with a lighter.

![image](images/hpd_hw_bg_01_2.png)

Heat-set the metal inserts with a soldering iron.

![image](images/hpd_hw_bg_01_3.png)
![image](images/hpd_hw_bg_01_4.png)

Check that the inserts match the holes in the case cover.

![image](images/hpd_hw_bg_01_5.png)

Install the switches on both halves.

> 💡 Insert the switches contact-side down in the top row for easier assembly.

![image](images/hpd_hw_bg_01_6.png)
![image](images/hpd_hw_bg_01_7.png)

Install the hotswaps on both halves.

> 💡 For the switches in the top row, rotate the hotswaps by 180 degrees.

![image](images/hpd_hw_bg_01_8.png)
![image](images/hpd_hw_bg_01_9.png)

</details>

---

### Step 2. Prepare the hotswap sockets for soldering

Next, we need to connect all hotswap sockets by columns and rows.

We will connect the rows using 1N4148 diodes. For this, bend the lead on the anode side and trim it, leaving 5–7 mm.

![image](images/hpd_hw_bg_02_1.png)

<details>
<summary><strong>➕ Detailed description</strong></summary>

Bend the anode-side lead about 90 degrees.

> ⚠️ The black stripe on the diode marks the cathode; the anode is not marked on the body.

![image](images/hpd_hw_bg_02_2.png)

Clip the lead, leaving 5–7 millimeters.

![image](images/hpd_hw_bg_02_3.png)

</details>

In this guide we will connect the columns with wires. Prepare them in the required way.

> 💡 You can choose another connection method, for example, use the trimmed diode leads.

![image](images/hpd_hw_bg_02_0.png)

<details>
<summary><strong>➕ Detailed description</strong></summary>

Prepare 12 wires about 20 centimeters long. Prepare 8 of them as follows:

- Strip about 15 millimeters of insulation from the end of the wire.

![image](images/hpd_hw_bg_02_4.png)

- Make a cut in the insulation about 22 millimeters from the end and slide the insulation toward the end of the wire.

![image](images/hpd_hw_bg_02_5.png)

- Make another cut in the insulation about 22 millimeters further and slide the insulation toward the end of the wire.

![image](images/hpd_hw_bg_02_6.png)

- Repeat this a third and fourth time. In the end, you should get a wire with 5 exposed segments on the conductor.

![image](images/hpd_hw_bg_02_7.png)

For the remaining 4 wires, do the same but with one segment fewer.

![image](images/hpd_hw_bg_02_8.png)

</details>

---

### Step 3. Solder the columns and rows

Connect the columns by soldering wires to one of the hotswap socket pins.

![image](images/hpd_hw_bg_03_0.png)
![image](images/hpd_hw_bg_03_1.png)

<details>
<summary><strong>➕ Detailed description</strong></summary>

> 💡 For convenience, choose one side of the hotswaps for connecting the columns and pre-tin the hotswap contacts with solder.

> ⚠️ Column numbering starts from the side with the USB opening.

The two outer columns (5 and 6) are soldered with wires that have 4 segments, while columns 1–4 use wires with 5 segments prepared in step 2.

![image](images/hpd_hw_bg_03_4.png)
![image](images/hpd_hw_bg_03_5.png)

Do the same for the right half, mirroring the wire-soldering position.

![image](images/hpd_hw_bg_03_6.png)

</details>

Next, connect the rows by soldering 1N4148 diodes with the anode to the second pin of each hotswap socket, and solder a common wire for each row.

![image](images/hpd_hw_bg_03_2.png)
![image](images/hpd_hw_bg_03_3.png)

<details>
<summary><strong>➕ Detailed description</strong></summary>

Solder the diodes prepared in step 2 to the free hotswap contact with the anode side.

> ⚠️ Row numbering starts from top to bottom.

![image](images/hpd_hw_bg_03_7.png)
![image](images/hpd_hw_bg_03_8.png)

Join the cathode leads together into a common trace.

![image](images/hpd_hw_bg_03_9.png)

Solder a wire of about 15 centimeters to the common trace.

![image](images/hpd_hw_bg_03_10.png)

Repeat these steps for all rows on the left and right halves.

</details>

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
<summary><strong>⁉️ Possible issues and how to fix them</strong></summary>

- **The computer does not see the keyboard, the BOOT drive does not appear**

  Check the board for short circuits, inspect the 3V3, 5V and GND pins. Also check the integrity of the USB connector and its solder joints.

- **An entire column does not work**

  There is no connection between the column and the RP-ZERO. Continuity-test or visually inspect the wire from the hotswap sockets to the required controller pin.

- **A row or part of a row does not work**

  The problem is with the diodes. Check the soldering, one or more diodes may be reversed or not fully soldered.

- **A key or several keys are stuck**

  Somewhere a diode is shorting to a column. Inspect the diode solder joints in the problematic area, look for accidental solder bridges.

- **The halves are mirrored (the left behaves like the right)**

  The resistors are soldered incorrectly. Go back to step 4 and check: on the left half the resistor goes to 3V3, on the right half it goes to GND.

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
