VARIABLES
Variables can be classified into two main categories, environment variables, and shell variables.

How to Create a variable:
    1. Use only letters a-z, numbers 0-9 and underscore character(_)
    2. Do not leave any spaces between the variable name, equal sign and the value
    3. Do not name the variable starting with a number but underscore is okay

Note: Variables are- Case Sensitive

How to remove a variable:
    unset variablename

How to dispaly environmental variables:
    1.env 
    2.printenv 
    3.echo $VARIABLE # We need to place a $ before the variable name when using echo command

How to create an environmental variable
    By using export command

    export NEWVAR=abc >> Environmental variable created
    NEWVAR=abc >>>>>>>>> Shell variable created

How to create a script file
    By using chmod +x filename
    1. Create a file using touch command
        touch myscript.sh
    2.Edit the file by using Vi editor
        vi myscript.sh
    3. Enter commands that you would like to add and save the file
    4. Change the file to executable file
        chmod +x myscript.sh
    5.To run the script apply ./
        ./myscript.sh
    6. If you want to run the script directly without ./, then you need to copy it to one of the PATHs.
        sudo cp myscript.sh /usr/bin/  # You need to do it with sudo command

How to edit PATH variable
    1. export PATH=/games/awesome  #This will add to the PATH variable
    2. PATH=/games/awesome         #This will repalce the PATH variable. Do not use this method unless you want to completely change the PATH variable

Best practice: Always use export when creating environmental variables

How to add space between variable names:
    1. Normally we do not use space inside variable names
        VARIABLE_NAME NOT VARIABLE NAME
    2. If we want to have a space between variable name
        1.Use single quotes # Ignores all special characters and accepts them as a regular character
        2.Use double quotes # Keeping $ as a special character, ignores other special characters
        3.Use \