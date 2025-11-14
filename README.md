# SPI-Protocol
This repo demonstrates design and verification of Serial Peripheral Interface (SPI) communication protocol.

## Design and Verification of SPI Protocol
SPT : The Serial Peripheral Interface
<img width="440" height="215" alt="peri_api_spi_diagram" src="https://github.com/user-attachments/assets/13f61347-97d3-4634-8996-7bac83ef04ac" />


SPI (Serial Peripheral Interface) is a high-speed, full-duplex protocol that was created by Motorola for the communication between microcontrollers and peripherals in a short distance. It selects the target device by using a Chip Select (CS/SS) line and can work with independent and daisy-chained multi-slave configurations. SPI is easy and quick since it does not use start/stop bits, however, it needs more CS lines as the number of slaves increases and it also does not offer error detection as a built-in feature.

- Main use case - communication b/w peripheral divices (sensors, displays) & microcontrollers.

- Developed by Motorola - 1980
- For short distance communication
. CSB (also called Slave select):
    - Pulled low to select target for communication
    - simple way to address targets
    - multiple cs lines can be used for multiple devices.
  
- 4 Modes of SPI

| Mode | Clk Polarity [CPOL] | CPHA |
| ---- | -------- | ---- |
|0|0|0|
|1|0|1|
|2|1|0|
|3|1|1|

- example : if Mode = 3 then, CPOL = 1 (CIK idle high) and CPHA = 1 (read on trailing edge)
  
- Multi - slave configuration
    - Independent slaves
    - Cooperative slaves/ Daisy chain


- Advantages: No start-stop bits required, full duplex protocol, Easy isolation.
- Disadvantages: SS/CSB increases as number of slaves increases, no protocol for error detection.

## FSM Based Architecture Design
<img width="388" height="646" alt="image" src="https://github.com/user-attachments/assets/c78b4426-ca42-4499-8b90-5e187c033b7d" />
<img width="414" height="712" alt="image" src="https://github.com/user-attachments/assets/a1dce063-05f7-48a7-b370-63eda70f0870" />

Above are the FSM flowcharts for master and slave architecures respectively
## Testbench Architecture

<img width="962" height="602" alt="image" src="https://github.com/user-attachments/assets/7496966c-1472-4d2a-a062-f8cd3066090a" />

## References:
- <a href="https://www.udemy.com/share/106k2a3@Jpho-VOf8wTPMeQi-Apt53UxAA9B7tMgNLXkbx1mdukUFrunTmb_XEcQ5SiTqofGcQ==/"> [Course] Verification Series Part 2: Hands-On SystemVerilog Projects </a>
- <a href="https://youtu.be/DOuB2zvE18U?si=L2TV6AcPT1fRATnd"> [YOUTUBE] SPI Protocol by Engineering Funda </a>
- <a href="https://youtu.be/0nVNwozXsIc?si=KUX88FvA-BOkT3QR"> [YOUTUBE] Understanding SPI by Rohde & Schwarz </a>
- [BOOK] Serial Communication Protocols and Standards by  Dawoud Shenouda Dawoud and Peter Dawoud





