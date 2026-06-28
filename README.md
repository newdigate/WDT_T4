# WDT_T4
Watchdog for Teensy 4, WDOG1,2,3, EWM

## NXP MIMXRT1060-EVKB (i.MX RT1062)

This library needs **no changes** for the MIMXRT1060-EVKB — the WDOG/RTWDOG/EWM
watchdogs are silicon-level (same i.MX RT1062 as the Teensy 4.x), and the
library has no board-specific code. Builds clean for `teensy:avr:mimxrt1060evkb`.

Verified in the i.MX RT1062 QEMU `mimxrt1060-evk` model: arming `WDT_T4<WDT1>`
and not feeding it triggers the watchdog timeout action. (Two QEMU-model
caveats, not library issues: feeding via the WSR service does not yet refresh
the modelled timer, and a watchdog *reset* action does not re-run the firmware
in emulation — both are tracked against the QEMU model, not this library.)
