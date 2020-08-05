# crash-course-in-python-examples
example1:
friends = ['Taylor', 'Alex', 'Pat', 'Eli']
for friend in friends:
    print("Hi " + friend)
    
    output:
Hi Taylor
Hi Alex
Hi Pat
Hi Eli

example2:
for i in range(10):
  print("Hello, World!")
  
  output:'
Hello, World!
Hello, World!
Hello, World!
Hello, World!
Hello, World!
Hello, World!
Hello, World!
Hello, World!
Hello, World!
Hello, World!

Tip: remember that you can use a**b to calculate a to the power of b.

example:

color = 'Yellow'
thing = 'sunshine'
print(color + " is the color of " + thing)

output:

Yellow is the color of sunshine

example:

Use Python to calculate how many different passwords can be formed with 6 lower case English letters. For a 1 letter password, there would be 26 possibilities. For a 2 letter password, each letter is independent of the other, so there would be 26 times 26 possibilities. Using this information, print the amount of possible passwords that can be formed with 6 letters.

letter = 6
possibility = 26
total = 26**6
print(total)

output:

308915776

example:

Most hard drives are divided into sectors of 512 bytes each. Our disk has a size of 16 GB. Fill in the blank to calculate how many sectors the disk has.

disk_size = 16*1024*1024*1024
sector_size = 512
sector_amount = disk_size/sector_size

print(sector_amount)

output:

33554432.0

example:
>>> print(10>1)
True
>>> print('cat'=='dog')
False
>>> print(1!=2)
True
>>> print(1<'1')
Traceback (most recent call last):
  File "<pyshell#4>", line 1, in <module>
    print(1<'1')
TypeError: '<' not supported between instances of 'int' and 'str'
>>> print(1=='1')
False
>>> print('yellow'>'cyan'and'brown'>'magenta')
False
>>> print(25>50 or 1!=2)
True
>>> print(not 42=='answer')
True
    
    
example:
def month_days(month,days):
    print(month+' '+'has'+' '+str(days)+' '+'days.')
month1=month_days("June",30)
month2=month_days("July",31)


output:
June has 30 days.
July has 31 days.


example:

def is_positive(number):
  if number>0:
    return True
    
    
output:

is_positive(-5) returned None
is_positive(0) returned None
is_positive(13) returned True

Congrats! You've now written
your first conditional block. Great work!

example:

def is_positive(number):
  if number > 0:
    return True
  else:
    return False
    
output:
is_positive(-5) returned False
is_positive(0) returned False
is_positive(13) returned True

Well done, you! You're starting to
master conditional expressions!

example:

def number_group(number):
  if number>0:
    return "Positive"
  elif number<0:
    return "Negative"
  else:
    return "Zero"

print(number_group(10)) #Should be Positive
print(number_group(0)) #Should be Zero
print(number_group(-5)) #Should be Negative

output:

Here is your output:
Positive

example:

def greeting(name):
  if name == "Taylor":
    return "Welcome back Taylor!"
  else:
    return "Hello there, " + name

print(greeting("Taylor"))
print(greeting("John"))

output:

Welcome back Taylor!
Hello there, John

example:
number=10
if number > 11: 
  print(0)
elif number != 10:
  print(1)
elif number >= 20 or number < 12:
  print(2)
else:
  print(3)
  
  output:
  
  10
  
  example:
  .Question 5
If a filesystem has a block size of 4096 bytes, this means that a file comprised of only one byte will still use 4096 bytes of storage. A file made up of 4097 bytes will use 4096*2=8192 bytes of storage. Knowing this, can you fill in the gaps in the calculate_storage function below, which calculates the total number of bytes needed to store a file of a given size?

def calculate_storage(filesize):
    block_size = 4096
    # Use floor division to calculate how many blocks are fully occupied
    full_blocks = filesize//4096
    # Use the modulo operator to check whether there's any remainder
    partial_block_remainder = filesize%4096
    # Depending on whether there's a remainder or not, return
    # the total number of bytes required to allocate enough blocks
    # to store your data.
    if partial_block_remainder > 0:
        return 4096*(full_blocks+1)
    return full_blocks*4096

print(calculate_storage(1))    # Should be 4096
print(calculate_storage(4096)) # Should be 4096
print(calculate_storage(4097)) # Should be 8192
print(calculate_storage(6000)) # Should be 8192

output:

4096
4096
8192
8192

example:Complete the function by filling in the missing parts. The color_translator function receives the name of a color, then prints its hexadecimal value. Currently, it only supports the three additive primary colors (red, green, blue), so it returns "unknown" for all other colors.

def color_translator(color):
	if color == "red":
		hex_color = "#ff0000"
	elif color == "green":
		hex_color = "#00ff00"
	elif color == "blue":
		hex_color = "#0000ff"
	else:
		hex_color = "unknown"
	return hex_color

print(color_translator("blue")) # Should be #0000ff
print(color_translator("yellow")) # Should be unknown
print(color_translator("red")) # Should be #ff0000
print(color_translator("black")) # Should be unknown
print(color_translator("green")) # Should be #00ff00
print(color_translator("")) # Should be unknown

output:
#0000ff
unknown
#ff0000
unknown
#00ff00
unknown

example:Students in a class receive their grades as Pass/Fail. Scores of 60 or more (out of 100) mean that the grade is "Pass". For lower scores, the grade is "Fail". In addition, scores above 95 (not included) are graded as "Top Score". Fill in this function so that it returns the proper grade.

def exam_grade(score):
	if score>95:
		grade = "Top Score"
	elif score>=60:
		grade = "Pass"
	else:
		grade = "Fail"
	return grade

print(exam_grade(65)) # Should be Pass
print(exam_grade(55)) # Should be Fail
print(exam_grade(60)) # Should be Pass
print(exam_grade(95)) # Should be Pass
print(exam_grade(100)) # Should be Top Score
print(exam_grade(0)) # Should be Fail

output:

Pass
Fail
Pass
Pass
Top Score
Fail

example:

def sum(x, y):
		return(x+y)
print(sum(sum(1,2), sum(3,4)))

output:
10

example:The longest_word function is used to compare 3 words. It should return the word with the most number of characters (and the first in the list when they have the same length). Fill in the blank to make this happen.

def longest_word(word1, word2, word3):
	if len(word1) >= len(word2) and len(word1) >= len(word3):
		word = word1
	elif len(word2) >= len(word1) and len(word2) >= len(word3):
		word = word2
	else:
		word = word3
	return(word)

print(longest_word("chair", "couch", "table"))
print(longest_word("bed", "bath", "beyond"))
print(longest_word("laptop", "notebook", "desktop"))

output:
chair
beyond
notebook

example:

def format_name(first_name, last_name):
	# code goes here
	if first_name!="" and last_name!="":
		return ("Name: "+last_name+", "+first_name)
	elif first_name!="" or last_name!="":
		return ("Name: "+first_name+last_name)
	else:
		return (""+"")
print(format_name("Ernest", "Hemingway"))
# Should return the string "Name: Hemingway, Ernest"

print(format_name("", "Madonna"))
# Should return the string "Name: Madonna"

print(format_name("Voltaire",""))
# Should return the string "Name: Voltaire"

print(format_name("", ""))
# Should return an empty string

output:

Name: Hemingway, Ernest
Name: Madonna
Name: Voltaire

example:
The fractional_part function divides the numerator by the denominator, and returns just the fractional part (a number between 0 and 1). Complete the body of the function so that it returns the right number. Note: Since division by 0 produces an error, if the denominator is 0, the function should return 0 instead of attempting the division.

def fractional_part(numerator, denominator):
	if denominator==0:
		return 0
	return (numerator%denominator)/denominator
	# Operate with numerator and denominator to 
	

# keep just the fractional part of the quotient
	

print(fractional_part(5, 5)) # Should be 0
print(fractional_part(5, 4)) # Should be 0.25
print(fractional_part(5, 3)) # Should be 0.66...
print(fractional_part(5, 2)) # Should be 0.5
print(fractional_part(5, 0)) # Should be 0
print(fractional_part(0, 5)) # Should be 0

output:

0.0
0.25
0.6666666666666666
0.5
0
0.0
