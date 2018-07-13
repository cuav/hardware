The PixHack V5 is based on the PX4 / FMUv5 derived flight control controller hardware. This is a common achievement of APM / PX4 and CUAV.

The vast majority of hardware designs have been completed by CUAV and the PX4/APM team has validated the hardware and software functions.Thanks again for their selfless dedication. 
After many iterations and version optimizations, all discovered hardware problems have been fixed. Almost all credit should be attributed to APM and PX4 related developers. 

The design documents (schematic and PCB files) currently published in CUAV_GITHUB have not been officially mass-produced and commercialized ,Design that belongs to the verification function.because we are still testing and improving.

We will publish all design source files after the hardware is completely stable, not only in the PDF format. (June 22, 2018).


-------------------------------------------------- ------

Copyright statement:

PixHack V5 is an open hardware design, following the OSHW 1.1 definition licensed under the Creative Commons Attribution-ShareAlike 3.0 Unported (CC BY-SA 3.0) license.

Although PixHack V5 hardware is mainly designed and verified by CUAV, the final hardware design copyright will be attributed to PX4（FMU5）and APM.

Current PixHack V5 design documents may reference many design or reference documents and related libraries for these organizations or companies.

May include PX4 \ PIXHAWK \ APM \ ST \ Altium \ TDK \ Hrs \ JST \ Kyocera \ PANASONIC \ molex \ TI and other organizations or companies.

Thank them for their open design reference and related document library.

The main reference is some chip pin definition or 3D model of the component.

The companies or organizations mentioned above do not necessarily have references in the V5 design. It is also possible that some of the contents of other companies or organizations not mentioned above are also cited in the V5 design document.

The referenced design drawings or library copyrights should belong to them.If your design or library does not allow referrals and open, please contact us for modification and deletion.

-------------------------------------------------- -------

V5 controller hardware description:

1: V5_Core

This is a complete master core that contains the F765 processor and main sensors (BMI055\ms5611\ICM-20602\ICM-20689) and extends the I/O through the DF17 series 80P interface.

2: V5_Base

This is an extended backplane. Its main functions are:
1: Built-in 3-way power redundancy switching circuit
2: Built-in PX4_IO_V2 processor
3: Connect to CORE via 80P Connector
4: Expansion interface through wire-to-board connector.
These include:
    UART X4 (GPS*2 + MAVLINK*2)
    I2C X4
    PWM X14
    CAN X2
    DEBUG and SWD debug interfaces for F7 SWD