##Ruby Syntax

#####Commenting
```ruby
# Commenting in ruby
```

#####Computation
```ruby
  14 + 9 = 23    # addition
  14 - 9 = 5     # subtraction
  14 * 9 = 126   # multiplication
  14 / 9 = 1.5555.....  # division
```
######Modulus
```ruby
   14 % 9 = 5    # modulus arithmetic
```

#####Strings
```ruby
  "  "  # This is an empty string
  "Hello World"  # This is a nonempty string
  
  # these strings are assigned to a variable
  a_string = "Hello World"  # A string with double qoutes

  a_string = 'Hello World'  # A string with single qoutes

  puts(a_string) # puts prints out Hello World

```
######Concatenate 

```ruby
  "hello" + " World"  # Prints out Hello World this is a string concatenation

   h ="hello" 

   w = " World"

   puts("The program says " + h + w) #Prints out The program says hello World this is also a string concatenation

```
######Interpolation
```ruby

  h ="hello" 
  
  w = "World"
  
  "#{h} #{w}" #Prints out hello World
  
  puts("The program says " + "#{h} #{w}")  # Prints out The program says hello World

```
#####Variables
```ruby
  # Strings assigned to a variables
  h ="hello" 
  
  w = "World"  
  
  me = "Jonathan"
  
  does = "Programs"
  
  # Integers assigned to variables
  num_1 =45 

  num_2 =12 

```

#####Printing
```ruby
  puts("Hello World")   # puts prints string Hello World

  print("Hello World")  # prints string Hello World

```

#####Newlines/Tabs
```ruby
  \n # Newline
  \t # Tabs

```
#####Objects/Messaging
```ruby
  "helloWorld".length #Prints the length of the string which is 10
  
  "helloWorld".empty? #Boolean expression checking if the string is empty, prints false
  
  "".empty? #Another boolean expression checking and it prints true 

```
#####Control FLow
```ruby

#if  #else
 hw = "Hello World"  # String assigned to a variable
 if hw.empty?                               # The expression is checked to see if hw is empty     
 puts("There is no string assigned to hw")  # It skips through this conditional statement and:
 else
   puts("The string is printed: "+ hw)      # Prints this one because there is a string assigned to hw
 end                                        # It prints, The string is printed: Hello World

#elsif
  hw = "HelloWorld"
  if hw.length == 5                         # Expression is checked to see if the length of hw's string is equal to 5
   "hw is equal to the length of 5"         # Since it is not true it skips to elsif
  elsif hw.length > 5                       # Expression is checked to see if the length of hw is greater than 5
   "hw is greater than 5"                   # It is true then it prints hw is greater than 5
end

```
#####Logical Operators
```ruby
#&& (“and”), || (“or”), and ! (“not”)
# && both have to be true
# || One of the them has to be true 
# ! none are true

   hw = "Hello World"
   
   emp = ""

  if hw.empty? && emp.empty?                          # Expression checks if both have empty strings it skips 
      puts("There seems to be an empty string")
      
  elsif  hw.empty? || emp.empty?                      # Expression checks if one of the strings is empty
     puts("One of the strings is empty")              # It checks and prints One of the strings is empty
   
  else !hw.empty?                                
     puts("emp is empty")
  
  end

```
#####Special methods for converting integers and strings
```ruby
# .to_i converts string to integer
"45".to_i   # Prints 45

# .to_s converts integer to string
 45.to_s    # Prints "45"

```
#####Special Statements
```ruby
 string = "Hello World"
 puts "The string '#{string}' is assigned to string." unless string.empty?  # Prints The string 'Hello World' is assigned to  string.
 
  hw = "Hello World"
  r="Ruby"
 puts("Hello World length is greater than Ruby length") if hw.length > r.length  # Prints Hello World length is greater than Ruby length

```

#####Methods
```ruby

def num(int= '')                     # Method def 
  if int > 50                        # The user inputs a number in num() it checks if the number is greater than 50
    "The number is greater than 50"
  else                               # else the number is less than 50 
    "The number is less than 50"
  end
end


num(78)  # prints The number is greater than 50

```
#####Data Structures
```ruby

 #ARRAYS
 "hello   world  ruby     ".split  # Splits the string into an array
 #prints ["hello", "world", "ruby"]
 
 
 "hellojworldjrubyjj".split('j')  # Splits string and removes the string j
 #prints ["hello", "world", "ruby"]

  num = [34, 56, 23, 12, 78, 9, 56]    # Array with numbers

  num[0] # Prints 34
  num[3] # Prints 12
  num[6] # Prints 56
  num[5] # Prints 9

 #Ruby synonyms
 num.first # Prints 34
 num.second # Prints 56
 num.last  # Prints 56

 num.length # Length method prints out 7
 num != 1 #Prints true
 
 #Other Methods
 num.empty? # Prints false because the array is not empty
 num.include?(14) # Prints false because the array does not contain the integer 14
 num.sort # Prints and sorts the array from least to greatest: 
 # [9, 12, 23, 34, 56, 56, 78]
 num.reverse  # Prints and reverses the array: 
 # [56, 9, 78, 12, 23, 56, 34]
 num.shuffle #Prints and shuffles the array:
 # [78, 56, 12, 23, 34, 9, 56]
 num.join # Joins the array together and prints:
 # "3456231278956"
 num.join(',') # Joins the array together along with the comma char and prints:
 # "34,56,23,12,78,9,56"
 
 #Push Method
 num.push(99) # Adds 90 to the array and prints:
 # [34, 56, 23, 12, 78, 9, 56, 99]
 
 num << 88  #Pushing 88 into the array prints:
 # [34, 56, 23, 12, 78, 9, 56, 88]
 num << "Hello" << "World"  # Chain array pushes Hello World into the array and prints:
 # [34, 56, 23, 12, 78, 9, 56, 88, "Hello", "World"]
 
 
 #RANGES
 num = (0..12).to_a # Prints 0 to 12:
 # [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12]
 ('J'..'M').to_a #Prints J through M in the alphabet
 # ["J", "K", "L", "M"]

```
