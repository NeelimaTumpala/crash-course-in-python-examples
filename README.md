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


