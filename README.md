# WDT_T4
Watchdog for Teensy 4, WDOG1,2,3, EWM

## NXP MIMXRT1060-EVKB (i.MX RT1062)

This library needs **no changes** for the MIMXRT1060-EVKB — the WDOG/RTWDOG/EWM
watchdogs are silicon-level (same i.MX RT1062 as the Teensy 4.x), and the
library has no board-specific code. Builds clean for `teensy:avr:mimxrt1060evkb`.

Verified in the i.MX RT1062 QEMU `mimxrt1060-evk` model for `WDT_T4<WDT1>`
(WDOG1), `WDT_T4<EWM>` and `WDT_T4<WDT3>` (RTWDOG): for each, arming without
feeding resets the chip on timeout (and a watchdog *reset* reboots the
firmware), while feeding via the device's service/refresh sequence keeps the
system alive.
