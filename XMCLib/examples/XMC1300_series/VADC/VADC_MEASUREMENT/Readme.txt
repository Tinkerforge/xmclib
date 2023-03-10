Description of example project
==============================
This example project depicts usage of SCU and ADC drivers.

The SCU driver is used to configure the clock settings and take the ADC peripheral out of reset.
The ADC driver APIs are used to configure GLOBAL, GROUP, QUEUE, CHANNEL and RESULT functional blocks.
A single queue entry is created and added to the queue.
ADC conversion is triggered manually. And in the ISR, the interrupt count is bumped up and interrupt
flags are cleared. The ISR clears the interrupt and the main loop restarts the conversion.

Hardware Setup
===============
XMC1300 Bootkit
IO Pin : 2.5

How to test the application
============================
a. Import the project
b. Compile and flash the application onto the device
c. Add g_num_interrupts and result to the watch window
d. Run the application. 
e. watch g_num_interrupts steadily increment

How to modify the application
==============================
a. To choose a different pin, identify the corresponding group and Channel. Update the macros
CHANNEL_NUMBER, VADC_GROUP_PTR and VADC_GROUP_ID accordingly.

Known limitations
=================
Conversion results are slightly noisy.