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
