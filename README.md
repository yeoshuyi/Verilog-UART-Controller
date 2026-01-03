# Verilog-UART-Controller
Test project to make simple UART TXRX on Arty S7 for learning
Modifications are work in progress, will be awhile until I update anything here

Main modification/addition to the tutorial followed (in CREDITS)
1) Addition of parity check to make this 8P1 protocol, with 1 bit start/stop
2) Modification to RX baud gen to make it synchronous with start bit detection, more accurate sampling
3) Hence, addition of another independent baud gen for TX unit so it does not get distorted by RX baud gen resets
4) Added synthesis of 295MHz CLK from 100MHz CLK to support 921600Bd with 0.03% oversampling error
5) Pushed baud rate from 9600 to 921600 (~100 fold increase) with 16x Oversample (Theoretically, around 0.8Mbps data throughput)
6) Added stop bit check, instead of just waiting 16 ticks
7) Changed from register based FIFO to BRAM to accommodate more address space for high throughput

CREDITS
Original UART Design inspiration:
https://github.com/FPGADude/Digital-Design/tree/main/FPGA%20Projects/UART
Using FPGA Discovery's tutorial:
https://www.youtube.com/watch?v=L1D5rBwGTwY
