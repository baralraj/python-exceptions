If we do not follow the proper syntax of the python, it will throw an error called syntax error or parsing errors. The python interpreter immediately reports it.

```
print "something"
SyntaxError: Missing parentheses in call to 'print'. Did you mean print(...)?
```

Print is a built-in function in python, and it requires parentheses. When an error occurs python will stop and generate an error message.

Even if the python expression has no syntax error, it may cause an error at runtime, called an exception. There are number of built-in exceptions are defined in the Python library.

For example, when we try to open a file that does not exist `FileNotFoundError`, when a key is not found in a dictionary `KeyError`, try to divide any number by zero `ZeroDivisionError`, or try to import a module that does not exist `ImportError` and so on.

These exceptions can be handled using the `try` statement

```
# The try block will generate an error because the variable num is not defined:
try:
  print(num)
except:
  print("An exception occurred")
```
Since the try block raises an error, the expect block will be executed. But without using this try block, the program will crash and raise an error

```
print(num) 
NameError: name 'num' is not defined

```

If we want to execute a special block of code for some special error, we can define as many exception blocks as we want

```
try:
  print(num)
except NameError:
  print("Variable num is not defined")
except:
  print("Something else went wrong here")
```

We can choose to raise (throw) an exception if some condition occurs. In order to raise an exception, we can use the `raise` keyword in python.

```
num = 0
if num <= 0:
  raise Exception("Only positive and non-zero number required")

```

We can also define the kind of error to raise and the details error message to print:

```
num = 0
if num <= 0:
  raise TypeError("Only positive and non-zero number required")
```

If we have the situation like clean up the resources, closing the connection etc. we can use finally block to make sure those code will be executed. The finally block is always guaranteed to run no matter if there is an exception or not.

```
try:
  txt_file = open("text_file.txt")
  try:
    txt_file.write("some message")
  except:
    print("Something went wrong when writing to the file")
  finally:
    txt_file.close()
except:
  print("Something went wrong when opening the file")
```
 
For more see [Errors and Exceptions in python](https://docs.python.org/3/tutorial/errors.html)
