# Method Lookup Path

- calling `.ancestors` on an object will show you the Method lookup Path.

## order of a lookup path

```
module Walkable
  def walk
    "I'm walking."
  end
end

module Swimmable
  def swim
    "I'm swimming."
  end
end

module Climbable
  def climb
    "I'm climbing."
  end
end

class Animal
  include Walkable

  def speak
    "I'm an animal, and I speak!"
  end
end

class GoodDog < Animal
  include Swimmable
  include Climbable
end

puts "---GoodDog method lookup---"
puts GoodDog.ancestors
```

The above code produces the following output:

```
---GoodDog method lookup---
GoodDog
Climbable
Swimmable
Animal
Walkable
Object
Kernel
BasicObject
```

What we can surmise from this is that the order of lookup is
1. looks for instance method
2. then it checks for any interface instances in the instance object
3. then it checks the superclass for any inherited methods.
4. then it checks for class inherited methods.

The point is that it checks in the order of the last declared all the way up.


