# Windows-basic-commands-batchscript
Ex08-Windows-basic-commands-batchscript

# AIM:
To execute Windows basic commands and batch scripting

# DESIGN STEPS:

### Step 1:

Navigate to any Windows environment installed on the system or installed inside a virtual environment like virtual box/vmware 

### Step 2:

Write the Windows commands / batch file . Save each script in a file with a .bat extension. Ensure you have the necessary permissions to perform the operations. Adapt paths as needed based on your system configuration.
### Step 3:

Execute the necessary commands/batch file for the desired output. 




# WINDOWS COMMANDS:
## Exercise 1: Basic Directory and File Operations
Create a directory named "my-folder"
## COMMAND AND OUTPUT

### command
mkdir my-folder

### output
<img width="310" height="85" alt="1" src="https://github.com/user-attachments/assets/79b7aee4-52a4-479a-8280-eff28d0c6ead" />


Remove the directory "my-folder"

## COMMAND AND OUTPUT

### command
rmdir my-folder

### OUTPUT
<img width="336" height="94" alt="2os" src="https://github.com/user-attachments/assets/ea6714fb-b082-4003-b4f3-58b051e2c289" />


Create the file Rose.txt

## COMMAND AND OUTPUT
### command
echo Roses are beautiful. > Rose.txt
### output
<img width="568" height="237" alt="3os" src="https://github.com/user-attachments/assets/e63827a5-bca3-414c-8134-dc78566ca3ed" />


Create the file hello.txt using echo and redirection

## COMMAND AND OUTPUT
### command
echo Hello World > hello.txt
### output
<img width="460" height="75" alt="4os" src="https://github.com/user-attachments/assets/18675dc8-34f3-480a-b503-6d97bbf673a2" />


Copy the file hello.txt into the file hello1.txt

## COMMAND AND OUTPUT
### command
copy hello.txt hello1.txt
### output
<img width="407" height="88" alt="5os" src="https://github.com/user-attachments/assets/74c7bd71-7c2f-4bd5-9886-06c3108d06d0" />


Remove the file hello1.txt
## COMMAND AND OUTPUT

### command
del hello1.txt

### output
<img width="314" height="83" alt="6os" src="https://github.com/user-attachments/assets/a5a015ce-94b9-4dbd-ac8f-3190a2476663" />

List out the file hello1.txt in the current directory
## COMMAND AND OUTPUT
### command
dir hello1.txt

### output
<img width="504" height="222" alt="7os" src="https://github.com/user-attachments/assets/9af11ef2-d5f3-4f94-b976-c2216c43e176" />


List out all the associated file extensions 

## COMMAND AND OUTPUT
### command
dir /b *.*
### output
<img width="347" height="84" alt="80s" src="https://github.com/user-attachments/assets/8e1bc189-08f0-471a-b9cf-9bb9fbbbfff1" />


Compare the file hello.txt and rose.txt

## COMMAND AND OUTPUT

### command
fc hello.txt Rose.txt
### output
<img width="403" height="155" alt="9os" src="https://github.com/user-attachments/assets/6ae8bf34-40f7-42f3-8cb2-740ca93e16d9" />


## Exercise 2: Advanced Batch Scripting
Create a batch file named on the desktop. The batch file need to have a variable assigned with a desired name for ex. name="John" and display as "Hello, John".


hello.bat 

@echo off
set name=John
echo Hello, %name%
pause




## OUTPUT
<img width="420" height="74" alt="10os" src="https://github.com/user-attachments/assets/1a56cb96-a06d-4861-99ed-373e66edffda" />



Create a batch file  on the desktop that checks whether a user-input number is odd or not. The script should:
Prompt the user to enter a number.
Calculate the remainder when the number is divided by 2.
Display whether the number is odd or not.
Ask the user if they want to check another number.
Repeat the process if the user enters Y, and exit with a thank-you message if the user enters N.
Handle invalid inputs for the continuation prompt (Y/N) gracefully.


oddcheck.bat

@echo off

:start
set /p num=Enter a number: 

set /a remainder=num%%2

if %remainder%==1 (
    echo %num% is odd.
) else (
    echo %num% is not odd.
)

:choice
set /p again=Do you want to check another number? (Y/N): 

if /I "%again%"=="Y" goto start
if /I "%again%"=="N" goto end

echo Invalid input. Please enter Y or N.
goto choice

:end
echo Thank you!
pause




## OUTPUT
<img width="547" height="186" alt="11os" src="https://github.com/user-attachments/assets/b7555942-4e81-4347-88b3-dde55d75a46d" />




Write a batch file that uses a FOR loop to iterate over a sequence of numbers (1 to 5) and displays each number with the label Number:. The output should pause at the end.

numbers.bat
@echo off

for /L %%i in (1,1,5) do (
    echo Number: %%i
)

pause





## OUTPUT

<img width="497" height="156" alt="12os" src="https://github.com/user-attachments/assets/28c62f41-e6a4-46aa-a3f4-55e27d52fee4" />



Write a batch script to check whether a file named sample.txt exists in the current directory. If the file exists, display the message sample.txt exists. Otherwise, display sample.txt does not exist. Pause the script at the end to view the result.

Instructions:
Use the IF EXIST conditional statement.
Make sure the script works for files located in the same directory as the batch file.
Use pause to keep the command window open after displaying the message.
Expected Output (if the file exists):

echo off

if exist sample.txt (
    echo sample.txt exists.
) else (
    echo sample.txt does not exist.
)

pause


## OUTPUT

<img width="451" height="84" alt="13os" src="https://github.com/user-attachments/assets/2ca39a24-d5d0-45b5-a784-9468999122a4" />



Write a batch script that displays a simple menu with three options:
Say Hello – Displays the message Hello, World!
Create a File – Creates a file named newfile.txt with the content This is a new file
Exit – Exits the script with a goodbye message
The script should repeatedly display the menu until the user chooses to exit. Use goto statements to handle menu navigation.

@echo off

:menu
echo ==========================
echo         MAIN MENU
echo ==========================
echo 1. Say Hello
echo 2. Create a File
echo 3. Exit
echo ==========================

set /p choice=Enter your choice: 

if "%choice%"=="1" goto hello
if "%choice%"=="2" goto create
if "%choice%"=="3" goto exit

echo Invalid choice.
pause
goto menu

:hello
echo Hello, World!
pause
goto menu

:create
echo This is a new file > newfile.txt
echo File created successfully.
pause
goto menu

:exit
echo Goodbye!
pause
exit



## OUTPUT

<img width="440" height="591" alt="14os" src="https://github.com/user-attachments/assets/7a01f822-94f9-4da5-89ee-df9e93c4b749" />


# RESULT:
The commands/batch files are executed successfully.

