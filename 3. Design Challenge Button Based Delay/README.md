LAB 3(Embedded Systens):
Brian Scala:
2/22/2023:
Lab goal is to change the blinking speed of an LED due to the length of the button press




GPIOINIT 
This driver is used to vconfigure the buttons and LED's. Both buttons are settup for interupts

------------------------------------------------------------------------------------------------

timerInit
- Configures Timer
- Sets inital CCR0 Value to 1
- Set up ACLK as continuous
------------------------------------------------------------------------------------------------
Port_2 Interups
- the interupt switches between falling and rising edge of the clock
- Every rising edge - the counter incrememnts to get the total time of the button press
- The Button switches from LOW-->HIGH and HIGH-->LOW
---------------------------------------------------------------------------------------------------
Port_4 Interrupt
- When button 4.1 is pressed, go back to original CCR0 value
---------------------------------------------------------------------------------------------------
Timer0_B0_ISR
- count_timer increments
---------------------------------------------------------------------------------------------------
Timer1_B0_ISR
- Toggle LED
Set CCR0 to the length of the button Press
---------------------------------------------------------------------------------------------------
How To Use
- Button will initially be blinking
Hold Button 2.3, the length of the button hold will be the blinking speed of the LED
Press 4.1 to reset to original speed
