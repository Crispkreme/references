## LESSON 1
Tags: input, output

Code:  
```sh
puts "Whats is your Name?"
name = gets
puts name
```

## LESSON 2
Tags: variable

Code:  
```sh
a = "sample variable"
myVariable = "sample variable"
my_variable = "sample variable"
```

## LESSON 3
Tags: comment

Code:  
```sh
puts "Hello!" # I'm a comment
```

## LESSON 4
Tags: flow control, condition, equality, inequality, numbers

Code 1:  
```sh
if name == 'Marvin'
  puts "Hello, Marvin"
else
  puts "hello, #{name}"
end
```

Code 2:  
```sh
a = "value"
b = "value"

a == b # => true
a == "something else" # => true
```

Code 3:  
```sh
title = "sample"
title != "sample1" # => true
title != "sample" # => false
```

Code 4:  
```sh
temp = 60
temp < 60    # => false
temp <= 60   # => true
temp > 25    # => true
temp >= 30   # => true
```

## LESSON 5
Tags: predicates

Example:  
```sh
puts "Hi, my name is Ruby"
puts "Whats is your name?"
name = gets.chomp
puts "Hi there #{name}, great to meet you"

questions = gets.chomp
if questions == "How old are you"
  puts "I'm 20 years old"
end

if questions == "Where do you live?"
  puts "Philippines"
end
```

## LESSON 6
Tags: methods, arguments

Code:  
```sh
def display_info(name, age)
  puts "Name: #{name}"
  puts "Age: #{age}"
end

display_info(name, age)
```
## LESSON 7
Tags: return

Code 1:  
```sh
def increase_by_10(number)
  return number + 10
end

puts increase_by_10(20) # => 30
```

Code 2:  
```sh
def add(number)
  return number + 10
end

puts increase_by_10(20) # => 30
```
Exercise:
- Add 2 numbers
- Multiply 3 numbers
- Return a string with an interpolated value (e.g. "the temperature outside is 'value'")
- Return a description of the temperature provided (e.g. it's hot)

Solution:  
```sh
def describe_temp(value)
  if value > 85
    "It's hot"
  else
    "It's not hot"
  end
end

puts describe_temp(85)
```

## LESSON 8
Tags: math, rounding, formatting

Examples builtin operation
- 1 + 1        # Addition
- 1 - 1        # Subtractions
- 1 * 1        # Multiplication
- 1 / 1        # Divisions
- 1 ** 1       # Exponents
- 10 % 3       # Modulo
- number.to_f  # integer => float
- number.to_i  # float => integer
- number.round # rounding the integer
- number.floor # always rounding down with floor
- number.ceil  # always rounding up with ceil
- sprintf("%.2f", 100.7676) # limit number to 2 decimal places

Code 1:  
```sh
def divide(number, denominator)
  number.to_f / denominator
end

puts divide(20, 7)
```
Example:
Build a calculator. It should take two numbers and an operand and output the result formatted to two decimal places. Operand should be any of:
- Add
- Subtract
- Divide
- Multiply

Solution:  
```sh

def add(a, b)
  display(a + b)
end

def divide(a, b)
  display(a / b)
end

def subract(a, b)
  display(a / b)
end

def multiply(a, b)
  display(a * b)
end

def power(a, b)
  display(a ** b)
end

def display(result)
  put sprintf("%.2f", result)
end

puts "Welcome to Basic Calculator"

puts "What is the first operand"
op_a = gets.chomp.to_f

puts "What is the second operand"
op_b = gets.chomp.to_f

puts "What operator would you like to use?"
operator = gets.chomp

add(op_a, op_b) if operator == 'add'
subract(op_a, op_b) if operator == 'subract'
multiply(op_a, op_b) if operator == 'multiply'
power(op_a, op_b) if operator == 'power'
divide(op_a, op_b) if operator == 'divide'

```

Exercise:
Enhace your calculator by adding the following capabilities:
- Calculate the square root of a number
- Calculate the area of a sphere given its diameter
- Calculate the length of the hypotenuse of a triangle given the other two sides

Solution:  
```sh

def square_root(value)
  display(Math.sqrt(value))
end

def sphere_area(diameter)
  # pi * D ^ 2
  display(Math::PI * diameter ** 2)
end

def hyp(a, b)
  # A ^ 2 + B ^ 2
  display(Math.sqrt(a ** 2 + b ** 2))
end

puts "Welcome to Advance Calculator"

puts "What operator would you like to use?"
operator = gets.chomp

puts "What is the first operand"
op_a = gets.chomp.to_f

if operator != 'sqrt' && operator != 'sphere_area'
  puts "What is the second operand"
  op_b = gets.chomp.to_f
end

square_root(op_a) if operator == 'sqrt'
sphere_area(op_a) if operator == 'sphere_area'
hyp(op_a, op_b) if operator == 'hyp'
```
## LESSON 9
Tags: string, formatting, concatenation

- "hi there" .reverse # "ereht ih"  => reverse functionality
- "hi there" .upcase  # "HI THERE"  => uppercase functionality
- "hi there" .lenght  # "8"         => length functionality
- "hi there"[3]       # "t"         => cardinal indexing functionality
- "hi there"[3..5]    # "the"       => slicing functionality
- "hi there"[-2]      # "r"         => negative indexing functionality
- "hi there"[-4..-2]  # "her"       => negative indexing functionality
- "foo" + "bar"       # "foobar"    => concatenation functionality
- "foo" * 3           # "foofoofoo" => multiplication functionality
- "hello" .reverse!   # "olleh"     => mutation functionality
- "abraca".gsub('a','A') 

Formatting the Characters
Code 1:  
```sh
#replace character
"abracadabra" .gsub('a','A') # "AbrAcAdAbrA"

#remove character
"abracadabra" .gsub('a','') # "brcdbr"

#replace words
"ken's pet" .gsub('pet','dog') # "ken's dog"

#mutation functions
str = "hello world"
str.gsub!('o', '')
puts str # "hell wrld"
```

Exercise 1:
The quick brown fox jumped over the lazy dog
- Reverse the string
- Capitalize every letter
- Cpunt the characters
- Generate a new string which is the first 10 characters of the input string
- Generate a new string which is the last 2 characters of the input string
- Determine the 5th character of the strings

Solution 1:  
```sh
str = The quick brown fox jumped over the lazy dog
str.reverse
str.upcase
str.length
str[0..9]
str[-2..-1]
str[4]
```

Exercise 2:
Given the array:
arr = ['a','b','c','c','d','e','f']
- Retrieve the 3rd elements (counting from 1)
- Retrieve the first two elements
- Retrieve the last elements
- Delete the duplicate 'c' character
- Add the character 'g', to the end of the array

Solution 2:  
```sh
arr = ['a','b','c','c','d','e','f']
arr[2]
arr[0..2]
arr[-1]
arr.deleted_at(3)
arr << 'g'
```

## LESSON 10
Tags: array, loop

- [1, 2, 3, 4].size            # => array size
- [1, 2, 3, 4].reverse         # => array reverse
- [1, 2, 3, 3, 4].uniq         # => array unique
- [1, 2, 3, 3, 4].sort.reverse # => array chaining

Sorting: 
sorting an elements exists
```sh
arr = [7,4,6,3,5]
arr.sort  # [3,4,5,6,7]
```

Inclusion: 
check if an elements exists
```sh
arr = %w(cat dog bee)
arr.include?('dog')   # true
arr.include?('horse') # false
```

Ways in doing loops
Example 1:  
```sh
# foor loop 1
animals = %w(fox horse dog cat)
for animal in animals
  puts animal
end

# foor loop 2
animals = %w(fox horse dog cat)
animals.each do |animal|
  puts animal
end

# foor loop 3
animals = %w(fox horse dog cat)
animals.each { |animal| puts animal }
```
Exercise 1:
- Print out the words one line at a time
- Sort the words and print again
- Reverse the sorted words and print again
- Add an extra word, remove the first elements, re-sort and print

Given function
# It assign a words into an array

input = <<-STR
Stacy Brown-Philpot is the chief operating officer of TaskRabbit, where she’s responsible for scaling and expanding the marketplace. Before TaskRabbit, she spent nearly a decade leading global operations for Google’s flagship products. She served as Head of Online Sales and Operations for Google India and opened the office in Hyderabad. Stacy was also an entrepreneur in residence at Google Ventures.
STR

$words = input.split(/\s+|\.|\,/).select { |w| !w.empty? } # This uses a Regular Expression (we'll learn about those later)

Solution 1:  
```sh
$words.each do |word|
  puts word
end

$words.sort!
$words.reverse!
$words << 'cat'
$words.deleted_at(0)
$words.sort!

$words.sort.each do |word|
  puts word
end
```
Solution 2:  
```sh
def display(array)
  array.each do |elem|
    puts elem
  end
end

display($words)
sorted = $words.sort

puts "\n\nSorted\n"
display(sorted)

puts "\n\nSorted Reverse\n"
display(sorted.reverse)

sorted.delete_at(0)
sorted << 'myword'

display(sorted.sort)
```
