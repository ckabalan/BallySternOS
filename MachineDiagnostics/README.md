# Machine Diagnostics

## Purpose

This is a standalone project that when connected (via USB) to a computer, this
program will make the Arduino output diagnostics to verify that the
Arduino can talk to the necessary components on the MPU board.

## Instructions

1. If this is your first time running diagnostics remove the playfield fuse from the machine to prevent a misconfiguration from damaging coils.
2. Open this directory in your Arduino IDE
3. Uncomment the appropriate #define block at the top of `MachineDiagnostics.ino`
4. Upload the code to your Arduino
5. Reset / Boot your pinball machine

## Example Output

The following indicates a successful test:

```
Start of program
Monitoring VMA signal, looking for presence of M6800 processor
Saw no sign of M6800 -- program will continue
Attempting to read & write from U10
  Testing U10A Control Register
    The U10A control register passed
  Testing U10B Control Register
    The U10B control register passed
  Testing U11A Control Register
    The U11A control register passed
  Testing U11B Control Register
    The U11B control register passed
Testing the clock cycle (if this hangs here, the conncection to clock is faulty)
It took 19108 microseconds for 10000 clock cycles
Clock frequency (very) approximately = 523 kHz
  DIP Bank 0 = 0xFE
  DIP Bank 1 = 0xFE
  DIP Bank 2 = 0x7F
  DIP Bank 3 = 0x4F
Starting interrupt tests - this is going to take 5 seconds to test
  In 5 seconds, saw 601 U10B interrupts and 1720 U11A interrupts
  Zero-crossing approx. 120.20 times a second
  Display interrupt approx. 344.00 times a second
  Interrupt tests done - if frequencies aren't approx 120 & 320, there's a problem with the interrupt line.
END OF TESTS
```

