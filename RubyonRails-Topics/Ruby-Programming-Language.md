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

#if 
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
