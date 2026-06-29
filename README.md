# WDT_T4
Watchdog for Teensy 4, WDOG1,2,3, EWM

## NXP MIMXRT1060-EVKB (i.MX RT1062)

This library needs **no changes** for the MIMXRT1060-EVKB — the WDOG/RTWDOG/EWM
watchdogs are silicon-level (same i.MX RT1062 as the Teensy 4.x), and the
library has no board-specific code. Builds clean for `teensy:avr:mimxrt1060evkb`.

Verified in the i.MX RT1062 QEMU `mimxrt1060-evk` model: arming `WDT_T4<WDT1>`
resets the chip on timeout, feeding it (the WSR service sequence) keeps the
system alive, and a watchdog *reset* reboots the firmware.
