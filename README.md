# 1. Specifications
This project presents the internal architecture of an application for securing lockers.
Its operation can be described as follows: the user has to enter 3 characters in turn,
representing the digits 0 to 9 plus the letters A - F, to secure the locker. 

Once the locker is secured. To select the digits, the user uses the AD_CIFRU button, and the UP and DOWN
buttons. The RESET button is intended to clear what is on the SSD display, and if it is locked,
after pressing the button the cabinet still remains locked. The MASTER_RESET button
resets the whole application to its original state. 

To open the locker, the user must enter the code correctly. The entered code appears
on the 7-segment BCD display.

# 2. User and maintenance manual

**Description**: to implement an application that allows the user to add a 3-digit code to secure a
locker (similar to lockers used in gym lockers, shopping malls, etc).

**Functional requirements**:
1. A FREE_OCUPIED led will have the function to signal that the cabinet is free (led
off) or occupied (led on).
2. The user will press an ADAUGA_CIFRU button to signal the start of code entry. An
ENTER_CHARACTER LED will light to mark the status of the code.
3. The user will add 3 characters at a time using the UP and DOWN buttons
4. Characters are in the range 0-1-..-8-9-A-B-..-F
5. The current character is displayed on the SSD
6. To switch to the next character the user will press the ADAUGA_CIFRU button
7. The previously entered character remains displayed
8. The next character is visible on the display in the next position
9. After entering the third character, when pressing the ADAUGA_CIFRU button, the
SSD display will go off and the digit will be in the locked state by lighting the
FREE_OCUPATED LED.
10. The ENTER_CHARACTER LED will go out
11. Existence of a RESET button/switch while entering the digit to return to the initial
state (FREE_OPEN LED will go out, SSD display is blank, ENTER_CHARACTER
LED will go out)
12. The user will press the ADAUGA_CIFRU button/switch to start entering the code to
unlock the cipher.
13. Steps 2-8 will be repeated
14. When entering the last character, pressing the ADAUGA_CIFRU button will check if
the code entered corresponds to the previous code.
15. In the case of a tie, the FREE_UNKNOWN LED will flash, the
ENTER_CHARACTER LED will go out, the SSD display will
clear.
16. In the case of inequality, the FREE_UNKNOWN LED will remain lit,
the ENTER_LOAD LED will go out, the SSD display will clear.

**Non-functional requirements**:
• On-board implementation
• SSD usage
• Use of switch, led, buttons

**Use case example**: The user chooses a cabinet with the Free_occupied led off. Press the
ADAUGA_CIFRU button to enter the characters. The character "0" is visible on the SSD.
Enter the first character "2" by pressing the DOWN button twice. On the SSD the display
changes when the button is pressed, i.e. 0->1->2. The user presses ADAUGA_CIFRU again
to enter the second character "1". The user presses ADAUGA_CIFRU again to enter the
second character "3". The user presses ADAUGA_CIFRU again, the code is saved, the ssd
content is empty, the FREE_OCUPATED LED is on, the ENTER_CHARACTER LED will
go off.

# 3. Possibilities for further development
1. Extending the choice of characters for the cipher, so the code might be more difficult
for someone else to guess. Instead of characters from 0 to F , we can have 0 to Z.
2. Extending the number of digits stored, so instead of 3 more characters could be
stored. The user could even choose how many digits he wants his cipher to have.
3. To increase the security level of the locker, the user has the option to use
fingerprint or facial recognition. A master key can also be used, which acts as a
master reset in the system.
