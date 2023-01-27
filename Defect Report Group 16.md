Group 16 Defect Report

**Exploratory tests:**

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

**Defect:**

Entering pin using keyboard stop working after CLEAR has been pressed

**Function being tested:**

Entering card pin using keyboard/buttons

**Initial state of the system:**

System is off

**Steps:**

1. Start Machine
2. Insert any number of bills
3. Use any card
4. Type any pin (using keyboard or buttons)
5. Press **CLEAR**

**Expected** :

Being able to re-type the pin using keyboard or buttons

**Received:**

System stops respond to keyboard presses but buttons on screen still work

**Additional Notes** :

Note: system still works properly

**Regression testing:**

Still is a problem in Version 1.1

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

**Defect:**

Pressing buttons that don't correspond to menu options shown freezes System for a few seconds

**Function being tested:**

ATM reacting to a button press that is not a option shown on the menu

**Initial state of the system:**

System is off

**Steps:**

1. Turn on application
2. Enter any amount of money
3. Enter any registered card (1)
4. Enter correct pin (42)
5. Select a number not corresponding to a transaction (0, \>4)

**Expected** :

A error sound should be heard and nothing should be displayed (or a error message displaying that there is no transaction button for the button they pressed)

**Received:**

System displays $20 as if 20 dollars in cash is being taken out and program freezes for a short period of time

**Additional Notes** :

Soft failure: System goes back to normal after $20 stops being displayed

**Regression testing:**

Almost all the buttons were fixed. Button 5 still has this problem in Version 1.1

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

**Defect:**

When transferring money from one account to another it's always short $0.5

**Function being tested:**

ATM prints correct amount on transfer transaction

**Initial state of the system:**

System is off

**Steps:**

1. Turn on application
2. Enter any amount of money
3. Enter any registered card(1)
4. Enter correct pin (42)
5. Select 3 (transfer)
6. Select 1 (checking) to 2 (Saving)
7. And reasonable amount (Below 100 since we start with 100)

**Expected** :

The reasonable amount transferred

**Received:**

The amount is always $0.5 below what was entered

**Additional Notes** :

Soft failure: Machine still works

**Regression testing:**

Fixed

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

**Defect:**

System deposits $10 short from the inputted amount

**Function being tested:**

Does the system deposit the correct amount of money into the account?

**Initial state of the system:**

System is off

**Steps:**

1. Turn the System on
2. Enter any legitimate amount of money
3. Enter the registered card 1
4. Enter correct pin (42)
5. Select Deposit (2)
6. Select Checking (1)
7. Choose type in a legitimate deposit amount
8. Insert Envelope

**Expected** :

Deposits correct amount into the account then prints out a receipt with the proper amount deposited and the total balance of the account and available money

**Received:**

Deposit is $10 short from the inputted amount. (if inputting $100 the deposited is $90)

**Additional Notes** :

Note: System works as normal just always $10 less then what the user inputted

**Regression testing:**

System is now $0.1 short instead of $10 short. Thus system still has this problem in Version 1.1

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

**Defect:**

Money Market does not function

**Function being tested:**

Money Market account isn't functional

**Initial state of the system:**

System is off

**Steps:**

1. Turn on application
2. Enter any amount of money
3. Enter any registered card (1)
4. Enter the correct pin (42)
5. Select any transaction type (1, 2, 3, 4)
6. Select Money Market as the Account (In case of choosing Transfer selecting Money Market from or to doesn't matter)
7. Proceed with the proper steps to complete transaction (In case of Balance Inquiry there is no steps other than selecting Money Market)

**Expected** :

Withdrawal: The withdrawal amount specified withdrawn (if available amount is enough)

Deposit: The amount specified is Deposited into the account

Transfer: The amount specified is either transferred into Money Market from another account or out of Money Market from another account

Balance Inquiry: Shows the proper balance of $5000 in the account

**Received:**

Withdrawal: Invalid Account Type error

Deposit: Invalid Account Type error

Transfer: Invalid Account Type error

Balance Inquiry: Unknown Error Type

**Additional Notes** :

Machine still works

**Regression testing:**

Still is a problem in Version 1.1

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

**Defect:**

System hangs when deposit amount is 100 million or over

**Function being tested:**

ATM depositing a very big amount

**Initial state of the system:**

System is off

**Steps:**

1. Turn the System on
2. Enter any amount of money
3. Enter any registered card (1)
4. Enter correct pin (42)
5. Select Deposit
6. Select checking
7. Enter 100 million or more

**Expected** :

Amount specified deposited

**Received:**

Program freezes

**Additional Notes** :

Soft failure: Machine still works

Note 1: We understand 100 million is a lot but we believe that at least a cap should be added to how much can be deposited so this crash is avoidable

**Regression testing:**

Still is a problem in Version 1.1

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

**Defect:**

Receipt prints incorrect card number for transactions

**Function being tested:**

Is the correct card number printed on the receipts when doing any transaction?

**Initial state of the system:**

System is off

**Steps:**

1. Turn the System on
2. Enter any amount of money
3. Enter the registered card (1 or 2)
4. Enter correct pin (42, or 1234)
5. Select any transaction type (1, 2, 3, 4)
6. Select any account (NOT Money Market as the account is bugged and doesn't work. Incase of Transfer Account order selection doesn't matter)
7. Complete transaction

**Expected** :

The receipt prints out "card 1" and the transaction # (for card 1)

The receipt prints out "card 2" and the transaction # (for card 2)

**Received:**

The receipt prints out "card 2" and the transaction # (for card 1)

The receipt prints out "card 3" and the transaction # (for card 2)

**Additional Notes** :

Does not affect the machine's log.

**Regression testing:**

Still is a problem in Version 1.1

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

**Defect:**

Entering card number 3 will completely crash after entering pin

**Function being tested:**

What will the ATM do if a non registered card number tries to login

**Initial state of the system:**

System is off

**Steps:**

1. Turn the System on
2. Enter any amount of money
3. Enter card number 3
4. Enter any pin

**Expected** :

FAILURE invalid card error

**Received:**

Program freeze/hangs

**Additional Notes** :

Soft failure: Machine somewhat works, like show longs will show the logs and buttons seem like they can be pressed but otherwise nothing worse. Receipt can be taken as well

**Regression testing:**

Fixed

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

**Defect:**

Entering 11 or more numbers as the pin will freeze the System

**Function being tested:**

Does the system give an error when the PIN entered is 11 or more digits in length?

**Initial state of the system:**

System is off

**Steps:**

1. Turn the System on
2. Enter any amount of money
3. Enter any card number
4. Enter a pin of length 11 or more

**Expected** :

Pin was incorrect error if card number is registered, else FAILURE invalid card error

**Received:**

Program freeze

**Additional Notes** :

Soft failure: Machine somewhat works, like show longs will show the logs and buttons seem like they can be pressed but otherwise nothing worse. Receipt can be taken as well

Note: I know that having a pin that big is ridiculous but there should be a pin max length so this doesn't happen

**Regression testing:**

Still is a problem in Version 1.1

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

**Defect:**

Withdraw option order is mixed up (each option withdraws the next options amount

**Function being tested:**

Does the system withdraw the correct amount of money from an account?

**Initial state of the system:**

System is off

**Steps:**

1. Turn the System on
2. Enter 100 $20 bills
3. Enter the registered card 1
4. Enter correct pin (42)
5. Select Withdrawal
6. Select from Checking
7. Select to Withdraw $200 (5)

**Expected** :

The ATM doesn't Withdraw any money since the card account doesn't have sufficient funds (Checking starts with $100 in it)

**Received:**

The ATM Withdraws $20 from the checking account

**Additional Notes** :

Soft failure: Machine still works

Note 1: There should be enough cash in the ATM since we are making it start with 10 $20 bills

Note 2: When testing the other withdrawal amounts they all also get the incorrect withdrawn amounts but there is a pattern. The amount withdrawn is always the amount that should be withdrawn for the choice in front of it. If 1 ($20) is chosen $40 is withdrawn, if 2 ($40) is chosen then $60 is withdrawn, if 3 ($60) is chosen then $100 is withdrawn and so on.

**Regression testing:**

Fixed

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

**Defect:**

Order of transfer is incorrect

**Function being tested:**

Does the system print the correct account transfer labels on the receipt/log?

**Initial state of the system:**

System is off

**Steps:**

1. Turn the System on
2. Enter any amount of money
3. Enter the registered card 1
4. Enter correct pin (42)
5. Select transfer transaction
6. Select from Checking to Savings
7. Enter a valid amount

**Expected** :

The receipt prints TRANSFER FROM: CHKG TO SVGS

**Received:**

The receipt prints the opposite TRANSFER FROM SVGS TO CHKG

The log also prints the opposite 1 (corresponding to SVGS) to 0 (corresponding to CHKG)

**Additional Notes** :

Note 1: System still works

Note 2: I'm pretty sure log is supposed to display SVGS to CHKG instead of 1 to 0

**Regression testing:**

Log order is now correct but still displaying as a numerical representation instead of the names. Receipt still shows the wrong order. Thus system still has this problem in Version 1.1

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

**Defect:**

No option to check Savings Balance

**Function being tested:**

Check the Balance of Accounts

**Initial state of the system:**

System is off

**Steps:**

1. Turn the System on
2. Enter any amount of money
3. Enter the registered card 1
4. Enter correct pin (42)
5. Select Balance Inquiry (4)

**Expected** :

3 options showing Checking, Savings, and Money Market

**Received:**

Only 2 options showing Checking, and Money Market

**Additional Notes** :

Soft failure: Machine still works

**Regression testing:**

Fixed

**Manual Scripted tests:**

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

**Defect:**

Log displays the numerical representation of the accounts instead of their names

**Function being tested:**

Is the log information displayed correctly after a transaction is completed?

**Initial state of the system:**

System is off

**Steps:**

1. Turn the System on
2. Enter any amount of money
3. Enter the registered card 1
4. Enter correct pin (42)
5. Select any transaction
6. Complete the transaction properly
7. Say yes to another transaction prompt
8. Choose the show log button

**Expected** :

Log displays a message of what transactions occurred, what card number it happened on, what transaction it was, then from what account the transaction happened and the amount

**Received:**

Log displayed a message of what transactions occurred, what card number it happened on, what transaction # it was, then **displayed a numerical representation of the account instead of the account name** and the amount

**Additional Notes** :

Soft failure: Machine still works

**Regression testing:**

Still is a problem in Version 1.1

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

**Defect:**

System takes user back to initial pin input page instead of logging them in after Re-entry of pin

**Function being tested:**

Does the system allow for the correct re-entry of a PIN after a failed attempt?

**Initial state of the system:**

System is off

**Steps:**

1. Turn the System on
2. Enter any legitimate amount of money
3. Enter the registered card 1
4. Enter incorrect pin (any pin that's not 42 or above 10 digits)
5. Enter correct pin (42)

**Expected** :

After inputting the correct pin into the re-enter pin page it should log you into the account

**Received:**

After inputting the correct pin into the re-enter pin page it takes you to the original pin prompting page and then if you enter the correct pin again it logs you into the account

**Additional Notes** :

Note: System still works

**Regression testing:**

Still is a problem in Version 1.1

**Regression testing:**

(New Defects)

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

**Defect:**

An error occurred during Balance inquiry of Savings account

**Function being tested:**

Checking the Balance inquiry of Savings account

**Initial state of the system:**

System is off

**Steps:**

1. Start Machine
2. Insert any number of bills
3. Enter any registered card (1)
4. Enter the correct pin (42)
5. choose Balance Inquiry transaction (4)
6. Select Savings (2)

**Expected** :

System prints a correct receipt showing correct balance; System records transaction correctly in the log (showing both message to the bank and approval back)

**Received:**

**System displays "Unknown error" and displays $500 then** System prints a correct receipt showing correct balance; System records transaction correctly in the log (showing both message to the bank and approval back)

**Additional Notes** :

Note: system still works properly but for some reason freaks out before continuing with the proper transaction process

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_