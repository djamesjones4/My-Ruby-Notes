# Regular Expressions
Great RegEx resource for Ruby
https://www.rubyguides.com/2015/06/ruby-regex/

## Character Classes

A character class lets you define a range or a list of characters to match.
For example, [aeiou] matches any vowel.

```=~``` returns the number of matches or ```nil```

```ruby

  def contains_vowel(str)
    str =~ /[aeiou]/
  end

  contains_vowel("test") # returns 1
  contains_vowel("sky") # returns nil  
```

## Shorthand Syntax

<table>
  <tr>
    <td>\w</td>
    <td>[0-9a-zA-Z]</td>
  </tr>
  <tr>
    <td>\d</td>
    <td>[0-9]</td>
  </tr>
  <tr>
    <td>\s</td>
    <td>white space (tabs, regular space, newline)</td>
  </tr>
</table>

There is also the negative form of these

<table>
  <tr>
    <td>\W</td>
    <td>Anything not in [0-9a-zA-Z]</td>
  </tr>
  <tr>
    <td>\D</td>
    <td>Anything not in [0-9]</td>
  </tr>
  <tr>
    <td>\S</td>
    <td>Anything that is not a white space (tabs, regular space, newline)</td>
  </tr>
</table>

## Dot Character
The dot character ```.``` matches everything but new lines. The dot must be escaped to capture a literal dot. I.E. ```\.```

## Escaping characterss
Characters can be escaped by adding a backslash before them.

```ruby
  # If we don't escape, the letter will match
  "5a5".match(/\d.\d/)
  # The above matches because the dot character is interpreted as the shorthand for "matching everything accept new line"

  #In this case only the literal dot matches
  "5a5".match(/\d\.\d/) # nil
  "5.5".match(/\d\.\d/) # match
```
### ```Regexp.escape()```

To insert the value of a variable into a regular expression and ensure that any meta-characters within the variable value are escaped you can use ```Regexp.escape(var)``` which will return a new string by escaping any characters that would have special meaning in a regular expression.

A variable can be inserted into a regular expression the same way as into a string, with ```#{var}```.

Example:
```ruby
var = "*This*"
str = "*This* is a string"
p str.gsub( /#{Regexp.escape(var)}/, 'foo' )
# => "foo is a string"
```
## Modifiers
Modifiers can be used to match multiple characters

<table>
  <tr>
    <td>+</td>
    <td>1 or more</td>
  </tr>
  <tr>
  <td> * </td>
  <td>0 or more</td>
  </tr>
  <tr>
    <td> ? </td>
    <td> 0 or 1 </td>
  </tr>
  <tr>
    <td> {3,5}</td>
    <td> Between 3 and 5 </td>
  </tr>
</table>
