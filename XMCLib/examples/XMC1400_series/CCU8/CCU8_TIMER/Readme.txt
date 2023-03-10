Description of example project
==============================
This example project depicts usage of SCU and CCU8 drivers.

The SCU driver is used to configure the clock settings and take the CCU8 peripheral out of reset.
CCU8 APIs are used to configure a CCU8 slice to operate in timer mode. The timer start is externally
triggered and the trigger originates from SCU.

In the ISRs of compare and period match events, interrupt counters are bumped up and the SCU is instructed
to regenerate the trigger for start of the timer slice.  


Hardware Setup
===============
XMC1400 Bootkit (No other satellite board required)


How to test the application
============================
a. Import the project
b. Compile and flash the application onto the device
c. Add g_num_period_interrupts and g_num_compare_interrupts to the watch window
d. Run the application. 
e. watch the two interrupt counters steadily increment

How to modify the application
==============================
a. To choose a different module.slice, please update the macros SLICE_PTR, MODULE_PTR, MODULE_NUMBER, SLICE_NUMBER
and CAPCOM_MASK.

