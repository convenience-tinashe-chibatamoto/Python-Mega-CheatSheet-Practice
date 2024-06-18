96. What is the purpose of the del statement in Python?<br>
Ans: Answer already provided above.
<br>
97. Explain the difference between the os.system() and subprocess.run() functions in Python.<br>
Ans: Both ```os.system()``` and ```subprocess.run()``` are used in Python to execute system commands from your program. However, there are some key differences that make ```subprocess.run()``` the preferred option:<br><br>

Function Parameters:
* ```os.system(command)```: This function takes a single argument, the command to be executed as a string.
* ```subprocess.run(args, *, stdin=None, input=None, stdout=None, stderr=None, capture_output=False, shell=False, cwd=None, timeout=None, check=False, encoding=None, errors=None, text=None, env=None, universal_newlines=None)```: This function takes several arguments to configure the execution of the command.

Return Values:
* ```os.system(command)```: This function returns the exit code of the command. A return value of ```0``` indicates success, and a non-zero value indicates an error.
* ```subprocess.run(args, ...)```: This function returns a ```CompletedProcess``` object, which contains information about the executed command, including the return code, the standard output, and the standard error.

Functionality:
* ```os.system(command)```: This function is a simple wrapper around the system's shell, and it is limited to executing a single command.
* ```subprocess.run(args, ...)```: This function is more flexible and powerful, allowing you to control various aspects of the subprocess, such as input, output, and environment variables.

In general, ```subprocess.run()``` is the recommended function to use for executing external commands in Python, as it provides more control, better readability and better error handling than ```os.system()```. However, ```os.system()``` can be suitable for simple, one-off command executions where you don't need advanced functionality.<br>
Code Example:
```python
# Using os.system():
import os

# Execute the command and capture the return code
return_code = os.system("ls")

# Check if the command was successful (exit code 0)
if return_code == 0:
  print("Command executed successfully")
else:
  print("Error executing command")

# This code simply executes the ls command using os.system() and captures the return code. It doesn't capture the actual directory listing.


# Using subprocess.run():
import subprocess

# Run the command and capture the output
process = subprocess.run(["ls"], capture_output=True, text=True)

# Check the return code
if process.returncode == 0:
  # Decode the output and print it
  print(process.stdout)
else:
  print(f"Error: {process.stderr}")

# This code uses subprocess.run() with a list containing the command ("ls").
# It sets capture_output=True and text=True to capture the standard output as a string.
# It then checks the return code and prints the output or the error message accordingly.
# This example demonstrates the advantage of subprocess.run(). It captures the actual output of the command, making it more versatile.

```


<br>

98. How do you split a string into a list of substrings in Python?<br>
Ans: Ans: Answer already provided above.
<br>
99. What is the purpose of the try, except, else, and finally blocks in Python?<br>
Ans: Answer already provided above.
<br>
100. How do you create a shallow copy of a list in Python?<br>
Ans: Answer already provided above.
<br>
BONUS: https://www.edureka.co/blog/interview-questions/python-interview-questions/
