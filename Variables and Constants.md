Variables and Constants in Ruby
===

A variable in Ruby can be distinguished by the characters
at the start of its name. There's no restriction to the
length of a variable's name(with the exception of the
heap size).

## Pseudo Variables

`self`  
Execution context of the current method.

`nil`  
The sole-instance of the `NilClass` class.

`true` and `false`  
The sole-instances of the `TrueClass` and `FalseClass`.

`$1`, `$2` ... `$9`  
Contents of capturing groups for regular expression
matches. They are local to **current thread and stack
frame**.

## Pre-defined Variables
[参见Wiki](http://en.wikibooks.org/wiki/Ruby_Programming/Syntax/Variables_and_Constants#Pre-defined_Variables)

## Pre-defined Constants

`__FILE__`, `__LINE__`, `__dir__`(new in Ruby 2.0)
