# Class Inheritance

[source](https://launchschool.com/books/oo_ruby/read/inheritance)

```ruby
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

## Super

---

- You can still override an inherited method.
- An overriden method can still access the superclass' method with
  the `super` keyword.

```ruby
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

## Common Super Syntax

---

The common way to use super is in the `initialize` method of the subclass

```ruby
class Animal
  attr_accessor :name

  def initialize(name)
    @name = name
  end
end

class GoodDog < Animal
  def initialize(color)
    super
    @color = color
  end
end

bruno = GoodDog.new("brown")        # => #<GoodDog:0x007fb40b1e6718 @color="brown", @name="brown">
```

When using like this, the subclass passes all arguments to the super class.
That is why, in the example, 'brown' is passed as to `@name` in the super class.

To control what params are passed up to the superclass, we use parenthesis on 
the `super` keyword in the subclass `initialize` method

```ruby
# ... code
class BadDog < Animal
  def initialize(age, name)
    super(name)
    @age = age
  end
end

BadDog.new(2, "bear")        # => #<BadDog:0x007fb40b2beb68 @age=2, @name="bear">
```
That is how you specify what params from the init is being passed up to the 
superclass.

## Super() & method lookup path

---

If you are calling `super` and don't want to pass the init args up from
subclass, because there will be an error of arguments passed - if its not setup
to accept args, you have to call `super()` with parens to guard against
unwanted argumentargument passing up the _method lookup path_.
