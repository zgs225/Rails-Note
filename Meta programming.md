Meta programming
===

The machine could be used to create new programming that
it could then execute. And that would be meta programming
--writing code that writes code.

## Base

The basement of meta programming.

###Objects and Classes

In reality, however, Ruby has just a single underline
class and object structure.

A Ruby object has three components: a set of flags, some
instance variables, and an associated class.

#### self and Method calling

`self` has two significant roles in running Ruby program.

+ `self` control how Ruby finds instance variables.
+ `self` plays a vital role in method calling. If there
  is no explicit reciever, Ruby uses `self` as default
  reciever.

Inside a class definition, `self` is set to the class
object of the class being defined.

#### Singletons

Ruby lets you define methods that are specific to a
particular object. These are called `singleton methods`.

    animal = 'cat'
    def animal.speak
      puts "The #{ self } says miaow."
    end

    animal.speak # => "The animal says miaow."

When we defined singleton method for the `animal` object，
Ruby create a new anonymous class and defined the `speak`.

#### Singletons and Classes

Newcomers to Ruby commonly make the mistake of setting
instance variables inline in the class definition and
then attempting to access these variables from instance
methods.

**Instance variables defined in the class body are
associated with the class object, not the instance
of the class.**

####Another way to access the singleton class

You can do the same thing Ruby's Class << an_object
notation.

You can't create a new instance of a singleton class.

To make `attr_accessor` work with class level instance
variables, you must have to invoke `attr_accessor` in
singleton class.


#### Inheritance and Visibility

Within a class definition, you can change the visibility
of a method in an ancestor class.

If a subclass changes the visibility of a method in a
parent, Ruby effectively inserts a hidden proxy method in
the subclass that invoke the original method using
`super`.

The call of `super` can access the parent's methods
regardless of its visibility.

### Modules and Mixins

The module that you include is effectively added as a
superclass of the class being defined.

When you include a module in class `Example`, Ruby Constructs
a new class object, makes it the superclass of `Example`,
and then set the superclass of the new class to be the
original superclass of `Example`.

Ruby will include a module only **once** in a inheritance
chain.

#### prepend

> New feature in 2.0

If a method inside a prepended module has the same name
as one in the original class, it will be invoked instead
of the original. The prepended module can then call the
original using `super`.

#### extend

Add the instance methods to a particular object.If you
use it in a class definition, the module's methods
become class methods.

#### Refinements

> New feature in 2.0

A refinement is a way of packaging a set of changes to
one or more classes. These refinements are defined
within a module.

### Meta programming Class-Level Macros
