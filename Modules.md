# Modules

## Mixins Modules

---

- sometimes called _interface inheritance_

When DRYing up code and the hierarchy of pure class based inheritance, while 
offering the best solution in most circumstances, does not fit every scenario.

Some subclasses may need to inherit a behaviour, while others might not and 
therefore should't have unused methods hanging around.

```
module Swimmable
  def swim
    "I'm swimming!"
  end
end

class Animal; end

class Fish < Animal
  include Swimmable         # mixing in Swimmable module
end

class Mammal < Animal
end

class Cat < Mammal
end

class Dog < Mammal
  include Swimmable         # mixing in Swimmable module
end
```

Dog and Fish can swim but, objects of other classes won't be able to.
Using modules to group common behaviours allows us to build a more powerful
flexible and DRY design.

Note: 
- methods should be named after a verb, since it is doing 'something', behaviour.
- Modules should have the 'able' suffix, ie., 'Swimmable', as a convention.

### When to use what

- You can only subclass from one class
  * you can mixin as many modules as you want
- 'is-a' relationship -> class inheritance
- 'has-a' relationship -> interface inheritance
ie., a dog is an animal and has an ability to swim.
- You cannot intantiate an object from a module. They are only for name-spacing
and grouping common methods together.
