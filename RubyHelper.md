# Base
## Comments
### Multiline
```
=begin
comment 
=end
```
## Terminal output
### Output for array
`print`
## Variables and constants
### Global
`$pass = 'qwerty'`
### Constant
`PI = 3.14`
### Parallel assignment
`a = b = c = 42`
### Multiple assignment
`a,b,c = 0, 9, 3`
## Handle errors
```
begin
  raise NoMemoryError, 'Out of memory'
rescue NoMemoryError => exception_variable
  puts 'Error OnMemoryError', exception_variable
else 
  puts 'Code perform without errors'
ensure
  puts 'Code perform in anyway'
end
```
### Arifmetic operations
## Exponent
`2 ** 5` => 32
## Strings
* `string1 = %q[Escapes any quotation marks, but doesn't understend \n]`
* `string2 = %Q[Escapes any quotation marks and understend \n]`
### Command of linux 
* ``` string3 = `ls -a` ```
### Documents
``` 
text = <<MARKER
marker
may be
any
MARKER
```
## Array
### Create
* `empty_arr = Array.new(5)` => [nil,nil,nil,nil,nil]
* `true_arr = Array.new(5,true)` => [true,true,true,true,true]
### Get element
* `my_array.[] 1` => get element with index 1
* `my_array.valuest_at(1,2,3,1..2)`
* `my_array.take(3)`
### Add
* `test_array.push(3)` => in end
* `test_array.unshift(5)` => in begin
* `test_array.insert(3, 32, 90)` => in 3 position
### Delete
* `array.pop` => last element
* `array.shift` => first element
* `array.delete_at(4)` => indicated position
* `array.delete(2)` => concrete value
* `array.compact` => delete nil
* `array.uniq` => delete duplicate values
## Logic expressions
* `!0` => false
* `1 <=> 1` => 0, values are equal
* `1 <=> 2` => -1, left value less
* `2 <=> 1` => 1, left value greater
## Control structures
### conditions
* `x = if a > 0 then b else c end
* `x == 1 ? puts 'true' : puts 'false'`
### case
```
period = 2.3
case period
  when 0 
    puts 'beginner'
  when 0..1
    puts 'junior'
  when 1..3 
    puts 'middle'
  else
    puts 'super!'
end
```
## Cycles
### while
```
counter = 1
while counter <= 5
  puts "iteration #{counter}"
  counter += 1
end
```
### until 
```
counter = 0
until counter == 5
  puts 'values of counter #{counter}'
  counter += 1
end
```
### loop
```
loop do
  # code..
  break if condition
end

loop do
  # code..
  break unless anticondition
end
```
### times, upto
```
n.times do |i|
  # code...
end

0.upto(n) do |i|
  # code... 
end
```
### for, each_index
```
for i in 0..10 do
  # code...
end

list.each_index do |i|
  # code...
end
```
## each and etc enumerators
### Get summ of all elements
* `(5..10).reduce(:+)`                 => 45
* `(5..10).inject {|sum, n| sum + n}`   => 45
### Create array
* `(1..4).map { |i| i*i }` => [1,4,9,16]
* `(1..4).collect { "cat" }` => ["cat","cat","cat","cat"]
## Functions
``` 
def double(x)
  x*2
end

double double 4 # => 16
```
### splat operator(list of parameters in one array)
```
def foo(*array)
  print array
end

foo("arg1",2,false) # => ["arg1", 2, false]
```
### yield (function get block of code though yield)
```
def surround
  puts "{"
  yield
  puts "}"
end

surround { puts 'hello world' }
```
# Ruby OOP
## Variables
`@@` - variable of class
`@` - variable of instance 
```
class Human
  @@species = "H.sappiens" # variable of class
  NAME = "Humas Class" # constant of class
  
  def initialize(name, age = 0)
    @name = name # variables of instance
    @age = age
  end
  
  def species # getter for @@species
    @@species 
  end
  
  def name=(name) # setter for @name
    @name = name 
  end
  
  def name # getter for @name
    @name
  end
  
  attr_reader :name, :age # getters for variables of instace
  attr_writers :name, :age # setters for variables of instace
  attr_accessor :name, :age # include getters and setters 
  
  def self.say # method of class, call method Human.say
    puts 'ggwp'
  end
end
```
## Inheritance
```
class Doctor < Human
  def examinePatient 
    # ...
  end
  
  def method1 # override parent method
    super.method1() # call parent method
    # ... 
  end
end
```
## Modules
```
module ModuleExample 
  def foo
    'foo'
  end
end
```
### include
```
class Person
  include ModuleExample
end

Person.foo # => error
Person.new.foo # => 'foo'
```
### extend
```
class Book
  extend ModuleExample
end

Book.foo # => 'foo'
Book.foo.new # => error
```

