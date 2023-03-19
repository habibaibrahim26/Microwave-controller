# project
Finite State Machine Demonstration :
Idle state: wait until the door is closed switch 3 (external push button is unpressed) and 
then wait for new input from the keypad (displaying mode?) 
as input : 'A' >> go to state popcorn.
 : 'B' >> go to state beef.
 : 'C' >> go to state chicken.
Note: In cases B and C if a illegal number is pressed such as ' 0' it will give ERR.
 : 'D' >> go to state cooking time where waiting for user input.
After any of these cases are done we go back to idle state again.
Every state explained:
CASE A:
if we pressed A on the keypad the LCD will display "POPCORN" then we must press 
on switch 2 to start the timer and the leds will be on as long the timer is, LCD display 
the countdown, it will finish the 1 minute time and the LCD will display "FINISHED" 
and the leds will toggle and the buzzer will make sound 3 times, then the controller 
returns to case Idle waiting for a new input.
CASE B:
if we pressed B on the keypad the LCD it will display "BEEF WEIGHT?" and wait 
for the delay then clear the LCD then goto the weight function ,in this function we write 
the number of kilos between 1 and 9 and if we pressed 0 on the keypad the LCD will 
display "ERR" then the LCD will be cleared then will ask again about the weight till we 
press a valid number after that the function will calculate the time (by the given rate)
and pass the value to timer function to display it on the LCD and wait for switch 2 to be 
pressed to start the countdown which will be displayed on the LCD and the leds will be 
on as long the timer is, if didn’t pause the timer then the time will finish and the LCD
will display "FINISHED" and the leds will toggle and the buzzer will make sound 3 
times, then the controller returns to case Idle waiting for a new input.
CASE C:
if we pressed C on the keypad the LCD it will display "CHICKEN WEIGHT?" and 
wait for the delay then clear the LCD then goto the weight function , in this function we 
write the number of kilos between 1 and 9 and if we pressed 0 on the keypad the LCD 
will display "ERR" then the LCD will be cleared then will ask again about the weight 
till we press a valid number after that the function will calculate the time (by the given 
rate) and pass the value to timer function to display it on the LCD and wait for switch 2 
to be pressed to start the countdown which will be displayed on the LCD and the leds 
will be on as long the timer is, if didn’t pause the timer then the time will finish and the 
LCD will display "FINISHED" and the leds will toggle and the buzzer will make 
sound 3 times, then the controller returns to case Idle waiting for a new input.
CASE D:
when 'D' is pressed displaying "Cooking Time?" showing on LCD the limitation for 
input time that must be less than 30 minutes and more than 1 second and wait for user 
input, if an invalid input is entered it returns to show on LCD the restrictions again and 
wait for user input also while pushing inputs on keypad the user can clear the latest 
inputs to start again to insert new inputs, when a valid inputs is entered we go to timer 
function made for this case displaying time and counting it down after pressing switch 2 
to start, if didn’t pause the timer then the time will finish and the LCD will display 
"FINISHED" and the leds will toggle and the buzzer will make sound 3 times, then 
the controller returns to case Idle waiting for a new input.
Important Note: timer and pause state are applied to all the cases 
mentioned above.
Timer state (countdown): 
The most common state in all states { 'A','B','C','D' } as while the countdown starts the 
leds must be on, the time state included the delay function check for switch1 or switch3 
(door) are pressed or not if pressed then we go to state pause.
Pause state:(we enter this state by pressing switch 1 or switch 3(opening the door))
While in this state the leds should be blinking while checking for switches 1 or 2 are 
pressed or not also checks if the door is closed. If switch 2 is pressed while door is 
closed leds are turned on again and return from Pause state to timer state and resume 
counting down the remaining time. if switch 1 is pressed (for the second time) also 
while the door is closed go from pause state to Idle state and clear display waiting for a 
new input, (leds will go off in Idle state)
