## LESSON 1
Tags: input, output

Code:  
```sh
puts "Whats is your Name?"
age = gets
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
Tags: array, loop, map, select, sort, find, inclusion, comparison

- [1, 2, 3, 4].size            # => array size
- [1, 2, 3, 4].reverse         # => array reverse
- [1, 2, 3, 3, 4].uniq         # => array unique
- [1, 2, 3, 3, 4].sort.reverse # => array chaining

Comparison Operator
- 1 <=> 1  # => 0
- 1 <=> -1 # => 1
- 1 <=> 2  # => -1
  
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

Find: 
finding specific character inside the array
```sh
result = ['gum', 'pine', 'palm', 'olive'].find do |tree|
  tree[0] == 'o'
  puts tree
end
```
Select: 
selecting the specific words inside the array
```sh
result = ['gum', 'pine', 'palm', 'olive'].select do |tree|
  tree[0] == 'o'
  puts tree
end
```

Map: 
mapping the data inside the array
```sh
%w(gum pine palm olive).map do |tree|
  tree.upcase
  puts tree
end
```

Sort with a block: 
```sh
%w(gum pine palm olive).sort do |a,b|
  a.length <=> b.length
end
```

Array indexing:
```sh
arr = %w(gum pine palm olive)
  arr.each_with_index do |tree, index|
  puts "#{index}: #{tree}"
end
```

Associative array:
```sh
arr = [
  ['cat', 13],
  ['dog', 9]
]

arr[0]   # ['cat', 13]
arr[0][0]   # cat
arr[0][1]   # 13
arr[1][0]   # dog
arr[1][1]   # 9
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

Solution 1:  
```sh

# It assign a words into an array
input = <<-STR
Stacy Brown-Philpot is the chief operating officer of TaskRabbit, where she’s responsible for scaling and expanding the marketplace. Before TaskRabbit, she spent nearly a decade leading global operations for Google’s flagship products. She served as Head of Online Sales and Operations for Google India and opened the office in Hyderabad. Stacy was also an entrepreneur in residence at Google Ventures.
STR

$words = input.split(/\s+|\.|\,/).select { |w| !w.empty? } # This uses a Regular Expression (we'll learn about those later)

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

# It assign a words into an array
input = <<-STR
Stacy Brown-Philpot is the chief operating officer of TaskRabbit, where she’s responsible for scaling and expanding the marketplace. Before TaskRabbit, she spent nearly a decade leading global operations for Google’s flagship products. She served as Head of Online Sales and Operations for Google India and opened the office in Hyderabad. Stacy was also an entrepreneur in residence at Google Ventures.
STR

$words = input.split(/\s+|\.|\,/).select { |w| !w.empty? } # This uses a Regular Expression (we'll learn about those later)

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

Exercise 2:

input = <<-STR
Stacy Brown-Philpot is the chief operating officer of TaskRabbit, where she’s responsible for scaling and expanding the marketplace. Before TaskRabbit, she spent nearly a decade leading global operations for Google’s flagship products. She served as Head of Online Sales and Operations for Google India and opened the office in Hyderabad. Stacy was also an entrepreneur in residence at Google Ventures.
STR

$words = input.split(/\s+|\.|\,/).select { |w| !w.empty? } # This uses a Regular Expression (we'll learn about those later)

Generate the list of the unique words founf in the input string, count how many times each occurs and print them, You should number the lines of the output as follows:
- 1: and 3 occurrences
- 2: for 3 occurrences
- 3: the 3 occurrences

Solution 1:  
```sh
def frequency(word)
  arr = $words.select do |sample|
    word == sample
  end
  arr.size
end

frequencies = $words.unique.map do |word|
  [word, frequency(word)]
end

sorted = frequencies.sort do |a, b|
  b[-1] <=> a[-1]
end

sorted.each do |pair|
  puts "#{index + 1}: #{pair[-1]} to #{pair[-1]} occurencies
end

p frequencies
```

## LESSON 11
Tags: iteration

Up to:
```sh
result = 0
1.upto(10) do |num|
  result += num
end
puts result
```
Down to:
```sh
50.downto(10) do |num|
  puts num
end
```

Exercise 1:
Do the following:
- Sum the numbers from 1 to 100
- Given an array containing 10 items, delete the first item and print it Repeat 3 times

Solution 1:  
```sh
result = 0
1.upto(100) do |num|
result += num
end
puts result

arr = %w(jane john mary kate elle simon dan kumar wie charlotte)
4.times do
  puts arr.deleted_at(0)
end

puts "New array:"
puts arr
```
## LESSON 12
Tags: range

Exercise 1:
Do the following:
- Print every character from A-K
- Use a range, write a method to determine if a given float number is between two values.
- Print all multiples of 7 up to 140 (use range!)
- Write a method that returns the intersection of two ranges as a ranges or nil if they do not intersect (overlap)

Solution 1:  
```sh
def included?(range, number)

  # method 1
  if range.exclude_end?
    number >= range.begin && number < range.end
  else
    number >= range.begin && number <= range.end
  end

  # method 2
  range.cover?(number)

end

puts included?(1.0..10.9, 5.7)

1.upto(20) do |num|
puts num * 7

def intersect?(range1, range2)
  if range1.begin < range2.begin
    if range1.end < range2.begin
      nil
    else
      (range2.begin...range1.end)
    end
  else
    if range2.end < range1.begin
      nil
    else
      (range1.begin...range2.end)
    end
  end
end
```
## LESSON 13
Tags: hash

- nil is has no value or like null
- include check if value is not set

Example 1:  
```sh
balances = {
  3 => 'c',
  1 => 'a',
  2 => 'b',
  4 => 'd'
}

# method 1
hash.keys.sort.each do |key|
  puts "#{key} : #{hash[key]}"
end

# method 2
sorted_hash = {}
hash.keys.sort.each do |key|
  sorted_hash[key] = hash[key]
end

# method 3
sorted_array = hash.sort do |(key1, val1), (key2, val2)|
  key1 <=> key2
end
sorted_hash = Hash[sorted_array] # return associative array

# converting associative array to hash
hash = Hash[['a',1],['b',2]] # {'a' => 1, 'b' => 2}
```

Exercise 1:
Create a hash containing people and their current bank balances
Do the following:
- Print all the names and bank balances to the screen
- Everyone wants to pool thier money to buy a car, how much they do have?

Solution 1:  
```sh
balances = {
  'Dan'   => 1000,
  'Jess'  => 1200,
  'Bryan' => 1500,
  'Kath'  => 2000,
}

sum = 0
balances.each_pair do |name, balance|
  sum += balance
  puts "#{name} has a $#{balance}"
end

puts "The total balance is $#{sum}"
```

Exercise 2:
Create a method that sorts a hash in key descending order and returns the sorted hash

Solution 2:  
```sh
drivers = {
  4 => 'Alonso',
  1 => 'Vettel',
  3 => 'Raikonnen',
  2 => 'Ricciardo'
}

def sort(hash)
  sorted = {}
  hash.keys.sort.reverse.each do |key|
    sorted[key] = hash[key]
  end

  sorted
end

puts sort(drivers)
```
## LESSON 14
Tags: symbols

Exercise 1:
Create an array of users. Each 'users' in the array should be represented by a hash. You can store the users details such as name and email address using symbols
do the following:
- Search for a user by thier name
- Print the email address of that user

Solution 1:  
```sh
users = [
  {name: 'Dan', email: 'dan@coderdan.com'},
  {name: 'Lauren', email: 'lauren@coderlauren.com'},
  {name: 'Steve', email: 'steve@codersteve.com'},
]

user = users.find do |user|
  user[:name] == 'Missing'
end

if user
  puts user[:email]
else
  puts "No user found"
end
```

## LESSON 15
Tags: object basics, constructor, instance variables, inspecting objects

Exercise 1:
Create an user class that has an name, email, and age attributes. create an "instance" of the user, set its attributes and then print them out.

Solution 1:  
```sh

class User
  attr_accessor :name, :email, :age
end

user = User.new
user.name = 'Marvin'
user.email = 'ramosmarvin@sample.com'
user.age = 26

puts user.name
puts user.email
puts user.age
```

Exercise 2:
Create an user class that has an name, email, and age attributes. create an "instance" of the user, set its attributes and then print them out.

Solution 2:  
```sh

class User
  attr_accessor :name, :email, :age

  def initialize(name, email)
    self.name = name
    self.email = email
    self.age = age
  end

  def print
    puts "#{self.name}"
    puts "#{self.email}"
    puts "#{self.age}"
  end
end

user = User.new('Marvin', 'ramosmarvin@sample.com', 26)
user.print
```

Exercise 3:
Create a method on your user class to celebrate the users birthday. The method should print "Happy Birthday" and increment the user's age by 1.

Solution 3:  
```sh

class User
  attr_accessor :name, :email, :age

  def initialize(name, email)
    self.name = name
    self.email = email
    self.age = age
  end

  def celebrate_birthday!
    puts "Happy birthday!"
    self.age += 1
  end
end

user = User.new('Marvin', 'ramosmarvin@sample.com', 26)
puts user.age
user.celebrate_birthday!
puts user.age
```

Example 1:
Create a method on your user class to celebrate the users birthday. The method should print "Happy Birthday" and increment the user's age by 1.

Solution 1:  
```sh
class User
  def initialize(name, email)
    self.name = name
    self.email = email
    self.age = age
  end

  def name=(name)
    @name = name.downcase
  end
  def name
    @name
  end

  def email=(email)
    @email = email
  end
  def email
    @email
  end

  def age=(age)
    @age = age
  end
  def age
    @age
  end 
end
```

Example 3:
to_s

Solution 3:  
```sh

class User
  attr_accessor :name, :email, :age

  def initialize(name, email)
    self.name = name
    self.email = email
    self.age = age
  end

  def to_s
    "#{self.name}, {self.age}, {self.email}"
  end

  def inspect
    "#{self.name}, {self.age}, {self.email}"
  end
end

user = User.new('Marvin', 'ramosmarvin@sample.com', 26)
puts user
```

Exercise 4:
Define to_s and inspect methods on your User class
Test them by calling puts and p directly on a user object

Solution 4:  
```sh

class User
  attr_accessor :name, :email, :age

  def initialize(name, email)
    self.name = name
    self.email = email
    self.age = age
  end

  def celebrate_birthday!
    puts "Happy birthday!"
    self.age += 1
  end

  def to_s
    self.name
    self.email
    self.age
  end

  def inspect
    "#{self.name}, {self.age}, {self.email}"
  end
end

user = User.new('Marvin', 'ramosmarvin@sample.com', 26)
puts user
p user
```
## LESSON 16
Tags: time, time instantiation

- Absolute Time #specific clock or calendar entry e.g. Mar 9, 2023 08:00
- Relative times # a duration e.g. 3 hours, 41 minutes and 8 seconds
- Seconds since the epoch # time on most modern computers is stored as a number of the seconds. e.g. January 1, 1970 00:00

Example 1:
Day method

Solution 1:  
```sh
if time.monday?
  puts "Needed a coffee"
end
```

Example 2:
Time Formatting

Solution 2:  
```sh
  time.strftime("%B %d, %Y") # January 16, 2012

  def print_time_24
    time.now.strftime('%H:%M')
  end

  def print_time_12
    time.now.strftime('%I:%M %P')
  end

  pearl_harbor = Time.now(1941, 12, 7)
  jfk = Time.now(1963, 11, 22)
  moon = Time.now(1969, 7, 20, 20, 18)
  Time.now.to_i / (60 * 60 * 24 * 365.0)

  puts print_time_24
  puts print_time_12
```

Exercise 1:
Build a clock
Your clock should update every second and print out the time in a human readable format.

Solution 1:  
```sh

  # method 1
  loop do
    print "\r" + Time.now("%H:%M:%S on %B %d, %Y")
    sleep 1
  end

  # method 2
  class Clock

    def run
      loop do
        print "\r#{time_string}"
        sleep 1
      end
    end

    def time_string
      Time.now("%H:%M:%S on %B %d, %Y")
    end

  end
  clock = Clock.new
  clock.run
```

## LESSON 17
Tags: inheritance

- Model real life # like objects in general, inheretance aims to reflect the real world.

Exercise 1:
Create a project class. 
The project should have a name and a budget. It should also have an array of team members (for now you can store team members as a string).

Implement classes for the following types:
- Project manager
- Developer
- Designer

Each of your classes should have a name and salary attributes. For each class you should implement a method which returns a string describing the role of that type. For example, for the Project Manager type it might simply return "Project Manager".

Solution 1:  
```sh
  class Member
    attr_accessor :name, :salary

    def initialize(name, salary)
      @name = name
      @salary = salary
    end

    def day_rate
      salary.to_f / 210
    end

    def to_s
      "#{role} #{self.name} #{self.day_rate}"
    end
  end

  class ProjectManager < Member
    def role
      "Project Manager"
    end
  end

  class Developer < Member
    def role
      "Developer"
    end
  end

  class Designer < Member
    def role
      "Designer"
    end
  end
  
  class Project
    attr_accessor :name, :budget
    attr_reader :members

    def initialize(name, budget)
      @name = name
      @budget = budget
      @members = []
    end

    def total_day_rate
      sum = 0
      @members.each do |member|
        sum += member.day_rate
      end
      sum
    end

    def sorted_members
      @members.sort do |a,b|
        a.day_rate <=> b.day_rate
      end
    end
  end

  project = Project.new("Cafe Website", 5000)
  project.members << ProjectManager.new("Dan", 10000)
  project.members << Developer.new("Robin", 80000)
  project.members << Developer.new("Joe", 80000)
  project.members << Developer.new("James", 75000)

  puts project.members
  puts project.total_day_rate
  puts "Sorted by Day rate" 
  puts project.sorted_members
```

Exercise 2:
Create a product class with a price and quantity attributes. 
- Subclass (extend) Product with a Wine class
- The wine class should have a variety and alcohol % attributes

Solution 2:  
```sh
if time.monday?
  puts "Needed a coffee"
end
```
