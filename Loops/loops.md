# Loops in Ruby

## ```loop do ... end```

The ```loop do ... end``` method will continuously execute a block of code  placed between ```do``` and ```end``` until ctrl + c is pressed or a ```break``` statement placed in the loop has its conditions met.

```Ruby
# Example
i = 0
loop do
  i += 1
  puts i
  break # this will cause execution to exit the loop
end
```
Note that the break statement ends the loop after one iteration. A <strong> conditional loop </strong> creates a condition that breaks the loop.

Example:

```Ruby
i = 0
loop do
  i += 2
  puts i
  if i == 10
    break  # the loop breaks when i reaches 10
  end
end
```

The code block to be executed can also be denoted with ```{...}```

```Ruby
# Example
loop {

}
```

## The ```next``` keyword

The keyword ```next``` can be used to skip an iteration of a loop. This is useful when you want a loop to continue, but to act differently in a specific circumstance.

Example:

```Ruby
i = 0
loop do
  i+=2
  if i == 4
    next  #skip rest of the code in this iteration
  end
  puts i
  if i == 10
    break
  end
end
```

## While loops
A while loop is given a parameter that evaluates to a boolean. When that parameter evaluates to ```false``` the loop breaks.

```Ruby
def some_input(x)
# Should take an integer and print it to the console incrementally decreasing by 1
  while x.to_i > 3
    puts x
    x = x - 1
  end

end

```

## Until loops
Until loops are the opposite of while loops as they also take a parameter that evaluates to a boolean, but contrarily they break when the parameter evaluates to ```true```.

Example:
```Ruby
x = gets.chomp.to_i

until x < 0
  puts x
  x -= 1
end
```

## For Loops

A ```for``` loop executes a code block a finite amount of times defined in the initiation of the loop like so:

```Ruby
x = gets.chomp.to_i

for i in 1..x do
  puts i
end
# takes an integer and prints from 1 to the input integer
```
