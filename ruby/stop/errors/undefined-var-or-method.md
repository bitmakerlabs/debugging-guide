# undefined local variable or method (NameError)

If you type a word into ruby, and it's not a keyword (e.g. `if`, `else`, `def`, `class`, etc.), ruby will first try to treat the word as a variable if it was previously defined, and if not, try to call a method using that word.

## Example

```bash
/path/to/my_program.rb:30:in `my_method':
undefined local variable or method `my_variable_or_method_name'
for #<MyProgram:0x007fd229275440> (NameError)
```

It expected that this code existed in the same method before it got to the error:

```ruby
my_variable_or_method_name = "my variable value"`
```

or that the method was defined in the same class:

```ruby
def my_variable_or_method_name
  # code...
end
```

---
[Back to Start](https://github.com/bitmakerlabs/debugging-guide/blob/master/README.md)
