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

example: How many times will "Not there yet" be printed?

x = 0
while x < 5:
  print("Not there yet, x=" + str(x))
  x = x + 1
print("x=" + str(x))

ans: 5

explination: 

>>> x=0
>>> while x<5:
	print("not there yet, x=" +str(x))
	x=x+1

	
not there yet, x=0
not there yet, x=1
not there yet, x=2
not there yet, x=3
not there yet, x=4
>>> print("x=" +str(x))
x=5


example:

def attempts(n):
    x = 1
    while x <= n:
        print("Attempt " + str(x))
        x += 1
    print("Done")
    
attempts(5)

output:
Attempt 1
Attempt 2
Attempt 3
Attempt 4
Attempt 5
Done


example:

In this code, there's an initialization problem that's causing our function to behave incorrectly. Can you find the problem and fix it?

def count_down(start_number):
  current=3
  while (current > 0):
    print(current)
    current -= 1
  print("Zero!")
  
  output:
  
  Here is your output:
3
2
1
Zero!

You nailed it! By initializing the current variable you got
the function to behave correctly.


eample: to print 1 to 5 numbers

def print_range(start, end):
	# Loop through the numbers from start to end
	n = start
	while n <= end:
		print(n)
		n+=1

print_range(1, 5)  # Should print 1 2 3 4 5 (each number on its own line) 

output:
1
2
3
4
5


example:Fill in the blanks to make the print_prime_factors function print all the prime factors of a number. A prime factor is a number that is prime and divides another without a remainder.


def print_prime_factors(number):
  # Start with two, which is the first prime
  factor = 2
  # Keep going until the factor is larger than the number
  while factor <= number:
    # Check if factor is a divisor of number
    if number % factor == 0:
      # If it is, print it and divide the original number
      print(factor)
      number = number / factor
    else:
      # If it's not, increment the factor by one
      factor+=1
  return "Done"

print_prime_factors(100)
# Should print 2,2,5,5
# DO NOT DELETE THIS COMMENT

output:
2
2
5
5

example:

Question 3
The following code can lead to an infinite loop. Fix the code so that it can finish successfully for all numbers.

Note: Try running your function with the number 0 as the input, and see what you get!

note: i have done this task

def is_power_of_two(n):
  # Check if the number can be divided by two without a remainder
  while n % 2 == 0 and n>1:
    n = n / 2
 
  # If after dividing by two the number is 1, it's a power of two
  if n == 1:
    
    return True
  return False
  

print(is_power_of_two(0)) # Should be False
print(is_power_of_two(1)) # Should be True
print(is_power_of_two(8)) # Should be True
print(is_power_of_two(9)) # Should be False

output:
False
True
True
False


example:

def sum_divisors(n):
  
  # Return the sum of all divisors of n, not including n
  return sum([i for i in range(1, n)
                if n % i == 0])


print(sum_divisors(0))
# 0
print(sum_divisors(3)) # Should sum of 1
# 1
print(sum_divisors(36)) # Should sum of 1+2+3+4+6+9+12+18
# 55
print(sum_divisors(102)) # Should be sum of 2+3+6+17+34+51
# 114

output:

0
1
55
114

example:The multiplication_table function prints the results of a number passed to it multiplied by 1 through 5. An additional requirement is that the result is not to exceed 25, which is done with the break statement. Fill in the blanks to complete the function to satisfy these conditions.

def multiplication_table(number):
	# Initialize the starting point of the multiplication table
	multiplier = 1
	# Only want to loop through 5
	while multiplier <= 5:
		result = number*multiplier
		# What is the additional condition to exit out of the loop?
		if result>25 :
			break
		print(str(number) + "x" + str(multiplier) + "=" + str(result))
		# Increment the variable for the loop
		multiplier+= 1

multiplication_table(3) 
# Should print: 3x1=3 3x2=6 3x3=9 3x4=12 3x5=15

multiplication_table(5) 
# Should print: 5x1=5 5x2=10 5x3=15 5x4=20 5x5=25

multiplication_table(8)	
# Should print: 8x1=8 8x2=16 8x3=24

output:

3x1=3
3x2=6
3x3=9
3x4=12
3x5=15
5x1=5
5x2=10
5x3=15
5x4=20
5x5=25
8x1=8
8x2=16
8x3=24

example:

Fill in the gaps of the sum_squares function, so that it returns the sum of all the squares of numbers between 0 and x (not included). Remember that you can use the range(x) function to generate a sequence of numbers from 0 to x (not included).

def square(n):
    return n*n

def sum_squares(x):
    sum = 0
    for n in range(1,x):
        sum += square(n)
    return sum

print(sum_squares(10)) # Should be 285


Here is your output:
285

Nice job! You've got Python to do some complex operations
for you!

example: on for loop:
friends = ['Taylor','Alex','Pat','Eli']
for friend in friends:
    print("Hi "+friend)
output:
Hi Taylor
Hi Alex
Hi Pat
Hi Eli

example:

# To calculate sum and average
values=[23,52,59,37,48]
sum=0
length=0
for value in values:
    sum+=value
    length+=1
print("Total sum: "+str(sum)+"-Average: "+str(sum/length))

output:

Total sum: 219-Average: 43.8

example:

>>> product=1
>>> for n in range(1,10):
	product=product*n
	print(product)

	
1
2
6
24
120
720
5040
40320
362880

example: to find factorial

def factorial(n):
    result = 1
    for i in range(n):
        result *=n
        n-=1
        
    return result

print(factorial(4)) # should return 24
print(factorial(5)) # should return 120

Here is your output:
24
120

Well done, you! The pieces of code you're tackling keep
getting more complex, but you're doing a great job!

example:
#product of all numbers from 1 to 10
product =1
for n in range(1,10):
    product = product*n
print(product)

output:
362880

example: Temperature

def to_celsius(x):
    return (x-32)*5/9
for x in range(0,101,10):
    print(x, to_celsius(x))

output:
0 -17.77777777777778
10 -12.222222222222221
20 -6.666666666666667
30 -1.1111111111111112
40 4.444444444444445
50 10.0
60 15.555555555555555
70 21.11111111111111
80 26.666666666666668
90 32.22222222222222
100 37.77777777777778

example:
Note:
end=" " -->helps to print in a new line every time.

# Program to print each domino tail in a set:
for left in range(7):
    for right in range(left, 7):
        print("[" + str(left) + "|" +str(right)+ "]", end=" ")
    print()

output:
[0|0] [0|1] [0|2] [0|3] [0|4] [0|5] [0|6] 
[1|1] [1|2] [1|3] [1|4] [1|5] [1|6] 
[2|2] [2|3] [2|4] [2|5] [2|6] 
[3|3] [3|4] [3|5] [3|6] 
[4|4] [4|5] [4|6] 
[5|5] [5|6] 
[6|6] 


Note:
In this code, we're using a new parameter that we passed to the print function. This parameter is called End. Normally, once print has taken the content we passed and written it to the screen, then it writes a special character that creates a new line called the newline character. If we want print to write something else instead of the newline character, we use the end parameter, like we see in this example. Notice how the second for loop iterates over a different number of elements each time it's called as the value of left changes. Depending on what you want to achieve with your nested loops, you may want both loops to always go through the same number of elements. Or you might want the second loop to connect to the first one. 

example:

Let's say you run a local girl's basketball league in your town. You have four teams that will play against each other in the league, both at home and away. You've stored the names of the teams in a list, like this. We want to write a script that will output all possible team pairings. we don't want to do is have a team playing against itself.

teams =['Dragon','Wolves','Pandas','Unicorns']
for home_team in teams:
    for away_team in teams:
        if home_team!=away_team:
            print(home_team+' vs '+away_team)

output:

Dragon vs Wolves
Dragon vs Pandas
Dragon vs Unicorns
Wolves vs Dragon
Wolves vs Pandas
Wolves vs Unicorns
Pandas vs Dragon
Pandas vs Wolves
Pandas vs Unicorns
Unicorns vs Dragon
Unicorns vs Wolves
Unicorns vs Pandas

example:
#For loop from 0 to 2, therefore running 3 times
for x in range(0, 3):
    print("We're on time %d" % (x))
output:
We're on time 0
We're on time 1
We're on time 2

example:
#While loop from 1 to infinity, therefore running forever.


x = 1
while True:
    print("To infinity and beyond! We're getting close, on %d now!" % (x))
    x += 1
output:
To infinity and beyond! We're getting close, on 1 now!
and so on will continue until infinity

example:
# to print(1 to 10 tables)
for x in range(1, 11):
    for y in range(1, 11):
        print('%d * %d = %d' % (x, y, x*y))
output:
1 * 1 = 1
1 * 2 = 2
1 * 3 = 3
1 * 4 = 4
1 * 5 = 5
1 * 6 = 6
1 * 7 = 7
1 * 8 = 8
1 * 9 = 9
1 * 10 = 10
2 * 1 = 2
2 * 2 = 4
2 * 3 = 6
2 * 4 = 8
2 * 5 = 10
2 * 6 = 12
2 * 7 = 14
2 * 8 = 16
2 * 9 = 18
2 * 10 = 20
3 * 1 = 3
3 * 2 = 6
3 * 3 = 9
3 * 4 = 12
3 * 5 = 15
3 * 6 = 18
3 * 7 = 21
3 * 8 = 24
3 * 9 = 27
3 * 10 = 30
4 * 1 = 4
4 * 2 = 8
4 * 3 = 12
4 * 4 = 16
4 * 5 = 20
4 * 6 = 24
4 * 7 = 28
4 * 8 = 32
4 * 9 = 36
4 * 10 = 40
5 * 1 = 5
5 * 2 = 10
5 * 3 = 15
5 * 4 = 20
5 * 5 = 25
5 * 6 = 30
5 * 7 = 35
5 * 8 = 40
5 * 9 = 45
5 * 10 = 50
6 * 1 = 6
6 * 2 = 12
6 * 3 = 18
6 * 4 = 24
6 * 5 = 30
6 * 6 = 36
6 * 7 = 42
6 * 8 = 48
6 * 9 = 54
6 * 10 = 60
7 * 1 = 7
7 * 2 = 14
7 * 3 = 21
7 * 4 = 28
7 * 5 = 35
7 * 6 = 42
7 * 7 = 49
7 * 8 = 56
7 * 9 = 63
7 * 10 = 70
8 * 1 = 8
8 * 2 = 16
8 * 3 = 24
8 * 4 = 32
8 * 5 = 40
8 * 6 = 48
8 * 7 = 56
8 * 8 = 64
8 * 9 = 72
8 * 10 = 80
9 * 1 = 9
9 * 2 = 18
9 * 3 = 27
9 * 4 = 36
9 * 5 = 45
9 * 6 = 54
9 * 7 = 63
9 * 8 = 72
9 * 9 = 81
9 * 10 = 90
10 * 1 = 10
10 * 2 = 20
10 * 3 = 30
10 * 4 = 40
10 * 5 = 50
10 * 6 = 60
10 * 7 = 70
10 * 8 = 80
10 * 9 = 90
10 * 10 = 100

example:
for x in range(3):
    print(x)
else:
    print('Final x = %d' % (x))
output:
0
1
2
Final x = 2

example:
string = "Hello World"
for x in string:
    print(x)
output:
H
e
l
l
o
 
W
o
r
l
d

example:
collection = ['hey', 5, 'd']
for x in collection:
    print(x)
output:
hey
5
d

example:
#Loop over Lists of lists
list_of_lists = [ [1, 2, 3], [4, 5, 6], [7, 8, 9]]
for list in list_of_lists:
    for x in list:
        print(x)
output:
=============== RESTART: C:\Users\L\Documents\practice page 3.py ===============
1
2
3
4
5
6
7
8
9

example:
mylist = ['a', 'b', 'c', 'd']
for v in mylist:
    # do something with v
    print(v,end=" ")
output:
a b c d 

example:
Your own range generator using yield


def my_range(start, end, step):
    while start <= end:
        yield start
        start += step

for x in my_range(1, 10, 0.5):
    print(x)
output:
1
1.5
2.0
2.5
3.0
3.5
4.0
4.5
5.0
5.5
6.0
6.5
7.0
7.5
8.0
8.5
9.0
9.5
10.0

example:
#Creating your own iterable
class Iterable(object):

    def __init__(self,values):
        self.values = values
        self.location = 0

    def __iter__(self):
        return self

    def next(self):
        if self.location == len(self.values):
            raise StopIteration
        value = self.values[self.location]
        self.location += 1
        return value
example:
Write a script that prints the multiples of 7 between 0 and 100. Print one multiple per line and avoid printing any numbers that aren't multiples of 7. Remember that 0 is also a multiple of 7.

for i in range(0,101):
    if i%7==0:
        print(i)
output:
0
7
14
21
28
35
42
49
56
63
70
77
84
91
98

example:

Question 3
Write a script that prints the first 10 cube numbers (x**3), starting with x=1 and ending with x=10.
for i in range(1,11):
  print(i**3)
  output:
  
1
8
27
64
125
216
343
512
729
1000

example:
to find factorial of numbers from 1 t 10
def factorial(n):
    result = 1
    for x in range(result,n):
        result=result*n
        n=n-1
    return result

for n in range(1,11):
    print(n, factorial(n))
output:
1 1
2 2
3 6
4 24
5 120
6 720
7 5040
8 40320
9 362880
10 3628800

example:The retry function tries to execute an operation that might fail, it retries the operation for a number of attempts. Currently the code will keep executing the function even if it succeeds. Fill in the blank so the code stops trying after the operation succeeded.

def retry(operation, attempts):
  for n in range(attempts):
    if operation():
      print("Attempt " + str(n) + " succeeded")
      break
    else:
      print("Attempt " + str(n) + " failed")
      

retry(create_user, 3)
retry(stop_service, 5)

example:

To print factorials from 0 to 9

def factorial(n):
    result = 1
    for x in range(1,n):
        result = result * n
        n=n-1
    return result

for n in range(0,10):
    print(n, factorial(n+0))
    
output:

0 1
1 1
2 2
3 6
4 24
5 120
6 720
7 5040
8 40320
9 362880

output:

Attempt 0 failed
Attempt 1 failed
Attempt 2 succeeded
Attempt 0 succeeded
Attempt 0 failed
Attempt 1 failed
Attempt 2 failed
Attempt 3 succeeded
None

example: To count how many numbers are there in a line

def factorial(n):
    print("factorial called with "+str(n))
    if n<2:
        print("Return 1")
        return 1
    result = n*factorial(n-1)
    print("Returning" + str(result)+" for factorial of "+"str(n)")
    return result
factorial(4)

output:

factorial called with 4
factorial called with 3
factorial called with 2
factorial called with 1
Return 1
Returning2 for factorial of str(n)
Returning6 for factorial of str(n)
Returning24 for factorial of str(n)

example:
The function sum_positive_numbers should return the sum of all positive numbers between the number n received and 1. For example, when n is 3 it should return 1+2+3=6, and when n is 5 it should return 1+2+3+4+5=15. Fill in the gaps to make this work:

def sum_positive_numbers(n):
    # The base case is n being smaller than 1
    if n < 1:
        return 0

    # The recursive case is adding this number to 
    # the sum of the numbers smaller than this one.
    return n + sum_positive_numbers(n-1)

print(sum_positive_numbers(3)) # Should be 6
print(sum_positive_numbers(5)) # Should be 15

Here is your output:
6
15

Whoohoo! You've just written your first recursive function.
Well done!

example:

Question 4
The count_users function recursively counts the amount of users that belong to a group in the company system, by going through each of the members of a group and if one of them is a group, recursively calling the function and counting the members. But it has a bug! Can you spot the problem and fix it?

def count_users(group):
  count = 0
  for member in get_members(group):
    
    if is_group(member):
      count += count_users(member)
    else:
      count += 1
  return count

print(count_users("sales")) # Should be 3
print(count_users("engineering")) # Should be 8
print(count_users("everyone")) # Should be 18

output:
3
8
18

example:

Fill in the blanks to make the is_power_of function return whether the number is a power of the given base. Note: base is assumed to be a positive number. Tip: for functions that return a boolean value, you can return the result of a comparison.

def is_power_of(number, base):
  # Base case: when number is smaller than base.
  if number < base:
    # If number is equal to 1, it's a power (base**0).
    return __

  # Recursive case: keep dividing number by base.
  return is_power_of(__, ___)

print(is_power_of(8,2)) # Should be True
print(is_power_of(64,4)) # Should be True
print(is_power_of(70,10)) # Should be False

output:



example:
The even_numbers function returns a space-separated string of all positive numbers that are divisible by 2, up to and including the maximum that's passed into the function. For example, even_numbers(6) returns “2 4 6”. Fill in the blank to make this work.

def even_numbers(maximum):
	return_string = ""
	for x in range(2,maximum+1,2):
		return_string += str(x) + " "
	return return_string.strip()

print(even_numbers(6))  # Should be 2 4 6
print(even_numbers(10)) # Should be 2 4 6 8 10
print(even_numbers(1))  # No numbers displayed
print(even_numbers(3))  # Should be 2
print(even_numbers(0))  # No numbers displayed

output:

 2 4 6
 2 4 6 8 10

 2


example:
The counter function counts down from start to stop when start is bigger than stop, and counts up from start to stop otherwise. Fill in the blanks to make this work correctly.

def counter(start, stop):
	x = start
	if x>stop:
		return_string = "Counting down: "
		while x >= stop:
			return_string += str(x)
			if x>stop:
				return_string += ","
			x=x-1
	else:
		return_string = "Counting up: "
		while x <= stop:
			return_string += str(x)
			if x<stop:
				return_string += ","
			x=x+1
	return return_string

print(counter(1, 10)) # Should be "Counting up: 1,2,3,4,5,6,7,8,9,10"
print(counter(2, 1)) # Should be "Counting down: 2,1"
print(counter(5, 5)) # Should be "Counting up: 5"

output:

Counting up: 1,2,3,4,5,6,7,8,9,10
Counting down: 2,1
Counting up: 5

example:
Fill in the blanks of this code to print out the numbers 1 through 7.

number = 1
while number <= 7:
	print(number, end=" ")
	number=number+1
	
output:
1 2 3 4 5 6 7 

example:
Question 2
The show_letters function should print out each letter of a word on a separate line. Fill in the blanks to make that happen.

def show_letters(word):
	for i in word:
		print(i)

show_letters("Hello")
# Should print one line per letter

output:

H
e
l
l
o

example:

Question 3
Complete the function digits(n) that returns how many digits the number has. For example: 25 has 2 digits and 144 has 3 digits. Tip: you can figure out the digits of a number by dividing it by 10 once per digit until there are no digits left.

def digits(n):
	count = 0
	if n == 0:
	  return 1
	while (n>0):
		count += 1
		n=n//10
	return count
	
print(digits(25))   # Should print 2
print(digits(144))  # Should print 3
print(digits(1000)) # Should print 4
print(digits(0))    # Should print 1

output:

2
3
4
1

example:

Question 4
This function prints out a multiplication table (where each number is the result of multiplying the first number of its row by the number at the top of its column). Fill in the blanks so that calling multiplication_table(1, 3) will print out:

1 2 3

2 4 6

3 6 9

def multiplication_table(start, stop):
	for x in range(start,stop+1):
		for y in range(start,stop+1):
			print(str(x*y), end=" ")
		print()

multiplication_table(1, 3)
# Should print the multiplication table shown above

output:
1 2 3 
2 4 6 
3 6 9 

example:

7.Question 7
The following code raises an error when executed. What's the reason for the error?


def decade_counter():
	while year < 50:
		year += 10
	return year
ans:
Failure in initialising the variables

example:

What is the value of x at the end of the following code?

for x in range(1, 10, 3):
    print(x)
    
ans: 7

example:

What is the value of y at the end of the following code?

for x in range(10):
    for y in range(x):
        print(y)
	
ans: 8

example:
Question 10
How does this function need to be called to print yes, no, and maybe as possible options to vote for?

def votes(params):
	for vote in params:
	    print("Possible option:" + vote)
ans: (['yes','no','maybe'])

example:

Modify the double_word function so that it returns the same word repeated twice, followed by the length of the new doubled word. For example, double_word("hello") should return hellohello10.

def double_word(word):
    word=word*2
    return word+str(len(word))

print(double_word("hello")) # Should return hellohello10
print(double_word("abc"))  # Should return abcabc6
print(double_word(""))      # Should return 0

Here is your output:
hellohello10
abcabc6
0

Great work! You're getting comfortable using some of the
basic string operations. You'll soon be working on even more
interesting tasks!

example:

Want to give it a go yourself? Be my guest! Modify the first_and_last function so that it returns True if the first letter of the string is the same as the last letter of the string, False if they’re different. Remember that you can access characters using message[0] or message[-1]. Be careful how you handle the empty string, which should return True since nothing is equal to nothing.

def first_and_last(message):
    return False

print(first_and_last("else"))
print(first_and_last("tree"))
print(first_and_last(""))

output


strings:

>>> name = "Neelima"
>>> print(name[1])
e
>>> text="Random string with a lot of characters"
>>> print(text[-1])
s
>>> print(text[-2])
r
>>> color = 'orange'
>>> color[1:4]
'ran'
>>> fruit = "pineapple"
>>> print(fruit[:4])
pine
>>> print(fruit[4:])
apple
>>> message= "A kong string with a silly typo"
>>> message[2]='l'
Traceback (most recent call last):
  File "<pyshell#1>", line 1, in <module>
    message[2]='l'
TypeError: 'str' object does not support item assignment
>>> new_message=message[0:2]+"l"+message[3:]
>>> print(new_message)
A long string with a silly typo
>>> pets="cats & Dogs"
>>> pets.index("&")
5
>>> pets.index("c")
0
>>> pets.index("Dog")
7
>>> pets.index("s")
3
>>> pets.index("x")
Traceback (most recent call last):
  File "<pyshell#9>", line 1, in <module>
    pets.index("x")
ValueError: substring not found
>>> "Dragons" in pets
False
>>> "cats" in pets
True
>>> "mountains".upper()
'MOUNTAINS'
>>> "Mountains".lower()
'mountains'
>>> answer = 'YES'
>>> if answer.lower() == "yes":
	print("User said yes")

	
User said yes
>>> "The number of times e occurs in this string is 4".count("e")
4
>>> "forest".isnumeric()
False
>>> "12345".isnumeric()
True
>>> "Forest".endswith("rest")
True
>>> int("12345") + int("54321")
66666
>>> " ".join(['This','is','a','string','joined','by','spaces'])
'This is a string joined by spaces'
>>> "...".join(['This','is','a','string','joined','by','three','dots'])
'This...is...a...string...joined...by...three...dots'
	
example:
program to update new email ids:

def replace_domain(email,old_domain,new_domain):
    if "@" +old_domain in email:
        index = email.index("@"+old_domain)
        new_email=email[:index]+"@"+new_domain
        return new_email
    return email
    
    
example: unsolved

Fill in the gaps in the initials function so that it returns the initials of the words contained in the phrase received, in upper case. For example: "Universal Serial Bus" should return "USB"; "local area network" should return "LAN”.

def initials(phrase):
    words = phrase.___
    result = ""
    for word in words:
        result += ___
    return ___

print(initials("Universal Serial Bus")) # Should be: USB
print(initials("local area network")) # Should be: LAN
print(initials("Operating system")) # Should be: OS

output:


example:
>>> name="Neelima"
>>> number = len(name)*3
>>> print("Hello {}, your lucky number is {}".format(name,number))
Hello Neelima, your lucky number is 21
>>> print("Your lucky number is {number},{name}".format(name=name,number=len(name)*3))
Your lucky number is 21,Neelima

example:
Modify the student_grade function using the format method, so that it returns the phrase "X received Y% on the exam". For example, student_grade("Reed", 80) should return "Reed received 80% on the exam".

def student_grade(name, grade):
	print("{x} received {y}% on the exam.".format(x=name,y=grade))
	return ""

print(student_grade("Reed", 80))
print(student_grade("Paige", 92))
print(student_grade("Jesse", 85))

output:

Here is your output:
Reed received 80% on the exam.

Paige received 92% on the exam.

Jesse received 85% on the exam.


Not quite. Check that you're filling in the contents of the
student_grade function as requested.

example:

>>> price=7.5
>>> with_tax=price*1.09
>>> print(price,with_tax)
7.5 8.175


>>> print("Base price: ${:.2f}.with Tax: ${:.2f}".format(price,with_tax))
Base price: $7.50.with Tax: $8.18

NOTE:
You can also put a formatting expression inside the curly brackets, which lets you alter the way the string is formatted. For example, the formatting expression {:.2f} means that you’d format this as a float number, with two digits after the decimal dot. The colon acts as a separator from the field name, if you had specified one. You can also specify text alignment using the greater than operator: >. For example, the expression {:>3.2f} would align the text three spaces to the right, as well as specify a float number with two decimal places. String formatting can be very handy for outputting easy-to-read textual output.

example:

Question 5
The replace_ending function replaces the old string in a sentence with the new string, but only if the sentence ends with the old string. If there is more than one occurrence of the old string in the sentence, only the one at the end is replaced, not all of them. For example, replace_ending("abcabc", "abc", "xyz") should return abcxyz, not xyzxyz or xyzabc. The string comparison is case-sensitive, so replace_ending("abcabc", "ABC", "xyz") should return abcabc (no changes made).

def replace_ending(sentence, old, new):
	# Check if the old string is at the end of the sentence 
	if sentence.endswith(old):
		# Using i as the slicing index, combine the part
		# of the sentence up to the matched string at the 
		# end with the new string
		i = sentence.rfind(old)
		new_sentence = sentence[:i]+new
		return new_sentence

	# Return the original sentence if there is no match 
	return sentence
	
print(replace_ending("It's raining cats and cats", "cats", "dogs")) 
# Should display "It's raining cats and dogs"
print(replace_ending("She sells seashells by the seashore", "seashells", "donuts")) 
# Should display "She sells seashells by the seashore"
print(replace_ending("The weather is nice in May", "may", "april")) 
# Should display "The weather is nice in May"
print(replace_ending("The weather is nice in May", "May", "April")) 
# Should display "The weather is nice in April"

output:

It's raining cats and dogs
She sells seashells by the seashore
The weather is nice in May
The weather is nice in April

example:

Fill in the gaps in the nametag function so that it uses the format method to return first_name and the first initial of last_name followed by a period. For example, nametag("Jane", "Smith") should return "Jane S."

def nametag(first_name, last_name):
	return("{} {}.".format(first_name, last_name[0]))

print(nametag("Jane", "Smith")) 
# Should display "Jane S." 
print(nametag("Francesco", "Rinaldi")) 
# Should display "Francesco R." 
print(nametag("Jean-Luc", "Grand-Pierre")) 
# Should display "Jean-Luc G." 

Jane S.
Francesco R.
Jean-Luc G.

example:

Question 2
Using the format method, fill in the gaps in the convert_distance function so that it returns the phrase "X miles equals Y km", with Y having only 1 decimal place. For example, convert_distance(12) should return "12 miles equals 19.2 km".

def convert_distance(miles):
	km = miles * 1.6 
	result = "{} miles equals {:.1f} km".format(miles, km)
	return result

print(convert_distance(12)) # Should be: 12 miles equals 19.2 km
print(convert_distance(5.5)) # Should be: 5.5 miles equals 8.8 km
print(convert_distance(11)) # Should be: 11 miles equals 17.6 km

output:

12 miles equals 19.2 km
5.5 miles equals 8.8 km
11 miles equals 17.6 km

example:

The is_palindrome function checks if a string is a palindrome. A palindrome is a string that can be equally read from left to right or right to left, omitting blank spaces, and ignoring capitalization. Examples of palindromes are words like kayak and radar, and phrases like "Never Odd or Even". Fill in the blanks in this function to return True if the passed string is a palindrome, False if not.

def is_palindrome(input_string):
	# We'll create two strings, to compare them
	new_string = ""
	reverse_string = ""
	# Traverse through each letter of the input string
	for r in input_string.strip():

		# Add any non-blank letters to the 
		# end of one string, and to the front
		# of the other string. 
		
		new_string = new_string+r.replace(" ","")
		reverse_string = r.replace(" ","")+reverse_string
	# Compare the strings
	if new_string.lower()==reverse_string.lower():
		return True
	return False

print(is_palindrome("Never Odd or Even")) # Should be True
print(is_palindrome("abc")) # Should be False
print(is_palindrome("kayak")) # Should be True

output:

True
False
True

example:

>>> x = ["Now" , "we" , "are" , "cooking!"]
>>> type(x)
<class 'list'>
>>> print(x)
['Now', 'we', 'are', 'cooking!']
>>> len(x)
4
>>> "are" in x
True
>>> "today" in x
False
>>> "today" not in x
True
>>> print(x[0])
Now
>>> print(x[3])
cooking!
>>> print(x[4])
Traceback (most recent call last):
  File "<pyshell#12>", line 1, in <module>
    print(x[4])
IndexError: list index out of range
>>> x[1:3]
['we', 'are']
>>> x[:2]
['Now', 'we']
>>> x[2:]
['are', 'cooking!']

example:
Using the "split" string method from the preceding lesson, complete the get_word function to return the {n}th word from a passed sentence. For example, get_word("This is a lesson about lists", 4) should return "lesson", which is the 4th word in this sentence. Hint: remember that list indexes start at 0, not 1.

def get_word(sentence, n):
	# Only proceed if n is positive 
	if n > 0:
		words = ___
		# Only proceed if n is not more than the number of words 
		if n <= len(words):
			return(___)
	return("")

print(get_word("This is a lesson about lists", 4)) # Should print: lesson
print(get_word("This is a lesson about lists", -4)) # Nothing
print(get_word("Now we are cooking!", 1)) # Should print: Now
print(get_word("Now we are cooking!", 5)) # Nothing

output:


example:


