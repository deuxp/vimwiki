# Common Mistakes Transitioning to Ruby

- attr_accessor takes args, but does not require an assignment operator
  - Symbol args are comma separated

- Private: when calling the private method from within, don't use `self`

- can use `(do something) if obj.zero?` instead of `if obj == 0 then {do something}`

- use case for using `protected` over `private` can be viewed in the 01_exercise_vehicle.rb
  - remember to use the data of class objects when passing them in as args
