# Ruby Object Oriented Programming

## Terms

### Namespace
In Ruby the ```namespace``` refers to a module that contains a group of related objects. For example, ```Math ``` is a Ruby namespace.

### scope resolution operator - ```Math::PI```

The scope resolution operator is a double colon, ```::``` this lets Ruby know where to look for a specific bit of code. In this case Ruby knows to look in the ```Math``` module for ```PI```. In the event that PI was stored in two different modules with a different precision, Ruby would know which PI we were looking for.

### Mixins - ```include``` & ```extend```

 Mixins allow a ruby subclass to incorporate data or behavior from several classes into a single class without inheriting from multiple superclasses. Ruby does not allow inheritance from multiple superclasses.

 When a module is used to mix additional behavior and information into a class, it’s called a mixin. Mixins allow us to customize a class without having to rewrite code!

 ex:

 ```Ruby
 module Action
 def jump
   @distance = rand(4) + 2
   puts "I jumped forward #{@distance} feet!"
 end
end

class Rabbit
 include Action
 attr_reader :name
 def initialize(name)
   @name = name
 end
end

class Cricket
 include Action
 attr_reader :name
 def initialize(name)
   @name = name
 end
end

peter = Rabbit.new("Peter")
jiminy = Cricket.new("Jiminy")

peter.jump
jiminy.jump
 ```
In the above example it does not make sense for ```Cricket``` to be a subclass of ```Action``` but we do want to include methods from ```Action```. Therefore, we make ```Action``` a module and ```include``` it in the ```Cricket``` class as a ```mixin```.

Note that a mixin mixes a modules methods in at an instance level. To make this accessible at the class level we use the ```extend``` keyword.

## Variable Types -
### Instance Variables - ```@variable_name ```

Instance variables are variables that have the scope of the instance of a class that they are created in. Syntax is @ followed by the variable name.

### Class variables - ```@@class_variable_name```

A class variable is a variable that is available to the entire class and thus to all instances of that class.

## Class Methods
A class method is a method that acts on the class itself (not the class instance object) and therefore can do things like access class variables from within an instance object.

### scope resolution operator - ```Math::PI```

The scope resolution operator is a double colon, ```::``` this lets Ruby know where to look for a specific bit of code. In this case Ruby knows to look in the ```Math``` module for ```PI```. In the event that PI was stored in two different modules with a different precision, Ruby would know which PI we were looking for.
