# Class Inheritance

```
class Animal
  def speak
    "Hello!"
  end
end

class GoodDog < Animal
end

class Cat < Animal
end

sparky = GoodDog.new
paws = Cat.new
puts sparky.speak           # => Hello!
puts paws.speak             # => Hello!
```

The `<` symbol signifies an inheritance.
The class to the left of the symbol will inherit the bahaviour of the class
on the right side.

- You can still override an inherited method.
- An overriden method can still access the Parent Class' method with
  the `super` keyword.

```
class Animal
  def speak
    "Hello!"
  end
end

class GoodDog < Animal
  def speak
    super + " from GoodDog class"
  end
end

sparky = GoodDog.new
sparky.speak        # => "Hello! from GoodDog class"
```
