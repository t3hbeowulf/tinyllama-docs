# Getting Started - Assembling the Official Case

Congratulations on purchasing an ITX Llama and the official ITX case! This guide page and video are here to help you construct your new case. Enjoy!

---

## Assembly Instructions (video)

<iframe width="560" height="315" src="https://www.youtube.com/embed/PY_88_Z4S98?si=26q5dDUQcKfhq5Rr" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

---

## Bill of Materials

If you chose to order just the 3D printed case parts rather than a complete kit, the following items will be needed in order for you to complete your case assembly: 

### Parts included with every order:

* Left panel
* Right panel
* Top panel
* Front I/O
* Bottom panel
* Front panel
* Back panel

#### Additional small parts:
* Power button cover
* IO Bracket
* OLED Retainer
* SDCard reader bracket
* Feet x4

### Accessories included with the complete kit: 

If you selected "Complete" when ordering your case, these parts are included.

* Switches
* Cables
* Micro-SD card extender
* USB Extenders
* Screws
* OLED Display
* Rotary encoder

### Shopping List for "Only 3D Printed Parts" option:

If you selected "Only 3D printed parts" when ordering your case, the following parts will need to be sourced elsewhere to complete your case.<br>
**NOTE: Confirm your selections in each listing!**

| QTY (per case)  | Item Name         | Shopping Link(s)                                                    | Notes                         |
| :-------------: | :---------------- | :-----------------------------------------------------------------  | :---------------------------- |
| 1  | Switch for PI/WT, 2pole 2throw | [AliExpress](https://www.aliexpress.com/item/32839181628.html)      | |
| 2  | USB Extenders USB 2.0 F-M 0.5m | [AliExpress](https://www.aliexpress.us/item/3256805261299135.html)  | |
| 2  | LEDS 2x5x7                     | [AliExpress](https://www.aliexpress.com/item/1005004436340818.html) | _one red, one green per case_ |
| 13 | m3 brass heat inserts m3x5x4.2 | [AliExpress](https://www.aliexpress.us/item/3256804442999990.html)  | |
| 1  | Arcade button 24mm             | [AliExpress](https://www.aliexpress.us/item/4000923863812.html)     | |
| 6  | Magnets 8x3                    | [AliExpress](https://www.aliexpress.com/item/1005005632635545.html) | |
| 1  | SDcard extender 46cm           | [AliExpress](https://www.aliexpress.com/item/1005002964656399.html) | |
| 3  | Pushbutton switches            | [AliExpress](https://www.aliexpress.com/item/1005002759466966.html) | |
| 1  | Rotary encoder 15mm plum       | [AliExpress](https://www.aliexpress.us/item/1005005983134515.html)  | |
| 1  | Rotary encoder black plum cap  | [AliExpress](https://www.aliexpress.us/item/3256805796819763.html?gatewayAdapt=4itemAdapt) | |
| 1  | OLED Display                   | [AliExpress](https://www.aliexpress.us/item/1005006351390199.html)  | |
| 13 | m3 10mm screws                 | [AliExpress](https://www.aliexpress.us/item/1005007219475077.html)  | _screws for case back/motherboard/tpu feet/gpu bracket_ |
| 2  | m2 6mm screws                  | [AliExpress](https://www.aliexpress.us/item/1005007219475077.html)  | _screws for SD card mount_ |
| 6  | 2 pin DuPont cable + connector 30cm | [AliExpress](https://www.aliexpress.com/item/32840578827.html) | |
| 3  | 3 pin DuPont cable + connector 30cm | [AliExpress](https://www.aliexpress.com/item/1005002918267300.html) | |
| 2  | 1 pin DuPont cable + connector 30cm | [AliExpress](https://www.aliexpress.com/item/1005008475374431.html) | female to female black (2xGND for encoder) |
| 1  | 4 Pin DuPont cable + connector 30cm | [AliExpress](https://www.aliexpress.com/item/1005006533245708.html) | _For OLED display connection_ |

### Power Supplies

The official case has provisions for two power supply options. 

* The default is using an external power brick through a panel-mounted jack provided by a PicoPSU of 80W or higher. 
* As an advanced option, users may opt to install an internal Mean Well power supply for the PicoPSU and utilize the C8 panel mount cutouts to plug an ungrounded power cable into their Llama's case. 
    
!!! warning "WARNING!" 
    The Mean Well PSU setup is considered an unsupported, advanced option—recommended only for users who are experienced and understand the associated requirements. The official case design continues to support and recommend the use of a PicoPSU, which avoids these issues entirely. <br>
    That said, it’s certainly helpful to note the grounding considerations with the Mean Well unit. While grounding can add a layer of safety, it's worth mentioning that many modern consumer electronics—including the latest consoles from Microsoft and Sony—use ungrounded C8 connectors without issue. These designs pass stringent safety certifications, so a C8 connector isn’t inherently unsafe when used appropriately within a well-designed system.

## Case Assembly - Electronics / Wiring Guide

Download the [PDF Guide][case-assembly_electronics] for Case Electronics Assembly for more details and/or follow the diagrams below: 

### Power / Reset / MT-32 Buttons

<p><img src=../images/case_buttons_switches.png title="Case Buttons / Switches" width=25%></p>

??? note "2-wire DUPONT cables"
    Use red/black 2-wire cables with dupont connector in one end.
    <p><img src=../images/wire_2pin-dupont.png title="2-wire Dupont" width=25%></p>

!!! info inline end "Polarity"
    Polarity does _**NOT**_ matter for the buttons or switches.

* Solder the wire end to the switches. The other end goes into the llama pin headers. 
    * Power switch connect to PWRSW
    * Reset Switch connects to RSTSW


### LEDs

<p><img src=../images/case_leds.png title="LEDs" width=25%></p>

??? note "2-wire DUPONT cables"
    Use red/black 2-wire cables with dupont connector in one end.
    <p><img src=../images/wire_2pin-dupont.png title="2-wire Dupont" width=25%></p>

!!! warning inline end "Polarity"
    Polarity _**does**_ matter for the LEDs.

In this instance the polarity DOES matter, the short leg of the LED is the negative and the longer is the positive.
For simplicity always use **black** wire for negative or ground. Cut back the legs a bit before soldering, and use either heat shrink, or hot glue to make the legs hold a bit better in the long run.

<p><img src=../images/header_frontpanel.png title="ITX Llama Front Panel Header" width=25%></p>
The dupont connector then goes into the `+PLED-` and the `+HDLED-` pins on the lama, do mind the polarity! 

### WT / Pi Switch

This switch has an two poles INPUT in the middle and two double-pole OUTPUTS, one on each
side. Use the 3-wire cables with 3-pin dupont connectors.

<p>
<img src=../images/mt32pi_toggle-switch.png title="WT / Pi Toggle Switch" width=25%>
<img src=../images/header_pi-wt.png title="WT / Pi Header" width=25%>
</p>

??? note "3-wire DUPONT cables"
    Use red/black/gold 3-wire cables with dupont connector in one end.
    <p><img src=../images/wire_3pin-dupont.png title="3-wire Dupont" width=25%></p>

<p><img src=../images/pi-wt_wiring.jpg title="WT / Pi Switch Wiring Diagram" width=50%></p>

The switch works in “reverse”, so when mounting it in the case, if the toggle is in the down
position pointing at PI printed on the case, the wires in the top row will be activated. If the function
seems reversed, just rotate the switch half a turn and tighten the nut.

### mt32-pi Front Panel

<p><img src=../images/mt32pi_frontpanel.png title="mt32-pi Front Panel Header" width=50%></p>

#### OLED Display

??? note "4-wire DUPONT cables"
    Use red/black/white/gold 4-wire cables with dupont connector in one end.
    <p><img src=../images/wire_4pin-dupont.png title="4-wire Dupont" width=25%></p>

1. On the display, connect the black side to GND pin, RED becomes VCC which IS power so colors
match up nicely. (SCL = Orange and SDA = Yellow) No Soldering is needed for the display, use the 4-pin dupont cable.
1. On the ITX Llama, connect it to the first four pins, be careful to connect the dupont connector in the right
orientation. SDA=Yellow, SCL=Orange, 3v3=red, GND=Black

#### Buttons / Rotary Encoder

??? note "2-wire + 3-wire + 1-wire DUPONT cables"
    Use red/black/gold 3-wire cables with a dupont connector on one end and 2x black 1-wire cables with a dupont connector for the rotary encoder. Use red/black 2-wire cables with dupont connector for the buttons.
    <p>
    <img src=../images/wire_3pin-dupont.png title="3-wire Dupont" width=25%>
    <img src=../images/wire_2pin-dupont.png title="3-wire Dupont" width=25%>
    </p>

!!! info inline end "Rotary Switch"
    Do note that this image is seen from the front with the rotary shaft towards you.

<p><img src=../images/rotary-encoder.png title="mt32-pi Front Panel Header" width=25%></p>

* SYNTH button connects to Red(B1), Black(GND) 
* ROM button connects to Red(B2), Black(GND)
* For consistency, use this color map for the rotary encoder: B3=Red, B4=Black, B5=Yellow.
* Snip off the connector of the other end and solder Yellow(B5) to `SW`, Black(B4) to `CLK`, Red(B3) to `DT` on the rotary encoder.
* Solder one of the 1-wire cables to each of the GND pins on the rotary encoder and connect the other the dupont connectors J13 row for B4 and B5

<p><img src=../images/mt32pi_wiring.jpg title="mt32-pi Front Panel Wiring Diagram" width=100%></p>

[case-assembly_electronics]: https://docs.retrodreams.ca/itxllama/binaries/MANUALS/ITXLlama_Case_WireAssembly_Guide.pdf