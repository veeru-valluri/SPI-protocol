# SPI Master Core in Verilog
**Simulated and Verified using ModelSim**

This project provides a detailed implementation of a Serial Peripheral Interface (SPI) Master Core using Verilog HDL. It was developed to gain hands-on experience in designing digital circuits, implementing communication protocols, and working with simulation tools. The SPI Master Core supports a wide range of standard SPI features and is designed to be configurable and reusable in embedded system designs.

---

## Project Overview

The SPI Master Core is a full-duplex, synchronous serial interface that allows communication between a master device and one or more SPI-compliant slave devices. The core supports flexible configuration of transfer parameters such as bit order, clock polarity, clock phase, and word length. The design is fully simulated and verified using the ModelSim simulation tool.

---

## Architecture

The core architecture includes the following main components:

- **Clock Generator**: Creates the SPI clock based on a configurable divider.
- **Shift Register**: Manages serial data transfer.
- **Control Unit**: Handles configuration, timing, and data management.
- **Slave Select Logic**: Selects target slave devices during communication.
- **Interrupt Support**: Enables signaling to external systems upon transfer completion.


![image](https://github.com/user-attachments/assets/106bd329-7b8f-4c0a-97e8-600285c48690)


---

## Features

- Full-duplex synchronous serial communication
- Configurable transfer word length (up to 128 bits)
- MSB-first or LSB-first data transfer
- Independent control over transmit and receive clock edges (rising/falling)
- Support for up to 32 slave devices
- Automatic slave select handling
- Interrupt enable feature
- Programmable SPI clock divider
- Easy configuration via `spi_defines.v` header file

---

## Simulation and Verification

The design is tested through a Verilog testbench in ModelSim, using a variety of SPI mode configurations.

### Clock Generator Simulation

![image](https://github.com/user-attachments/assets/2eedfec0-e12d-4878-ad92-d907f55e8087)


### Shift Register Simulation


![image](https://github.com/user-attachments/assets/10f62203-3968-4827-9141-711f37d5b1d7)



---

## Test Cases

Three key test cases were used to verify different SPI configurations:

### Test Case 1
- Transmit on falling edge (`TX_NEG = 1`)
- Receive on rising edge (`RX_NEG = 0`)
- LSB-first transfer (`LSB = 1`)
- Word length: 4 bits

![image](https://github.com/user-attachments/assets/a73a21b2-5cc0-4263-a8ca-d18f19e1b451)



### Test Case 2
- Transmit on falling edge (`TX_NEG = 1`)
- Receive on rising edge (`RX_NEG = 0`)
- MSB-first transfer (`LSB = 0`)
- Word length: 4 bits


![image](https://github.com/user-attachments/assets/44d68b5a-f38c-4c20-b399-b9feded4474d)


### Test Case 3
- Transmit on rising edge (`TX_NEG = 0`)
- Receive on falling edge (`RX_NEG = 1`)
- LSB-first transfer (`LSB = 1`)
- Word length: 4 bits


![image](https://github.com/user-attachments/assets/8f8bed8f-81ca-4e63-a0ad-38c5bc74c412)



---



