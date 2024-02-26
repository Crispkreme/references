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
Exercise:
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
## LESSON 9
