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

## LESSON 8
## LESSON 9
