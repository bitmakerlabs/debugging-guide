## Follow the flow

Follow the flow of your program. Think about:

- What happens first?
- What happens when a method is called?
- When the method is finished?
- What variables are being set?
- What variables are changing in value?

Try to understand each line of what your program is doing. If there's something you don't quite understand, try looking it up or calling over an instructor to explain.

#### Example

Given the following program, think about what's happening here:

```ruby

class MySimpleClass

  def initialize
  	puts "One My Simple Class Coming Right Up!"
  end

  def hello(name = nil)

    if name
      puts "Hello #{name}"
    else
      puts "Come on, ya gotta tell me yer name!"
    end

  end

end

greeter = MySimpleClass.new
greeter.hello('Sean')
puts 'Fin!'
```
Let's think about this program line by line:


```ruby
class MySimpleClass
```

This sets up a class called MySimpleClass in ruby's virtual machine. Note that it does not execute the class -- it's just setting up the class for later use.

```ruby
  def initialize
  	puts "One My Simple Class Coming Right Up!"
  end
```

This sets up a special method that is invoked when a new instance of this class is setup. Note that this method doesn't actually execute at this point -- it's only being defined.


```ruby
  def hello(name = nil)
    if name
      puts "Hello #{name}"
    else
      puts "Come on, ya gotta tell me yer name!"
    end
  end
```

This defines a method called `hello` that accepts one argument. We won't go into detail as to what this method does, as the method isn't actually being executed yet -- it's just being defined for execulation later.

```ruby
  def count_to_ten
    [1, 2, 3, 4, 5, 6, 7, 8, 9, 10].each do |number|
      puts number
    end
  end
```

This defines a method called `count_to_ten` that accepts no arguments. This method had not yet been executed.

```ruby
end
```
This ends the setting up of the class. Note that no code has actually executed yet -- it's only been setup in memory for us to use.

```ruby
greeter = MySimpleClass.new
```

Now we're actually using the code we've setup. We're creating a local variable called `hello`, and in that variable, storing a new instance of our MySimpleClass class. When the instance is created, it executes the initialize method.

```ruby
  def initialize
  	puts "One My Simple Class Coming Right Up!"
  end
```

Ah, now we're inside the initialize method, and the `puts` line is executed and the following appears in our terminal:

```
One My Simple Class Coming Right Up!
```

Then ...

```ruby
greeter.hello('Sean')
```

This calls the `hello` instance method, passing a string `'Sean'` as an argument.

```ruby
  def hello(name = nil)
```

Now we're at the beginning of this method. We're setting up a local variable called `name` to be used just within this method. `name` is going to be set to whatever arugment was passed in (`'Sean'` in our case), but if no argument was passed in, we would have still setup the `name` local variable, but just set it to `nil`.

```ruby
    if name
```

Here we're checking to see `if name` is evaluating to `true`. Controls expressions like `if`, `unless`, `while` always evalute to true or false, and then based on that decide the next step in the flow. In ruby, only `false` and `nil` evaluate to `false`. Everything else evaluates to `true`, include strings, intergers, the number `0`, and empty strings (`""`).

```ruby
      puts "Hello #{name}"
```
We output **Hello** and a single space to the terminal. Note that we're still inside the double quotes, so we're still inside a string at the moment.

We then encounter `#{name}`. The `#{}` inside quotes is a string interprolation, and the code in between the curly braces will be executed as ruby code. In our case, it's the variable `name`, which is currently set to the string `'Sean'`, and thus it returns `'Sean'`.

We're still inside the double quotes, which we're passing into the `puts` method, and so puts will output `Sean` to the screen.

And thus this simple line outputs:

```
Hello Sean
```

Then...

```ruby
    else
      puts "Come on, ya gotta tell me yer name!"
    end
```

As the `if` statement evaluable to true, we don't execute the `else` and instead just jump to the `end` of the `if`.

```ruby
  end
```

We then encounter the `end` of the method, and then return to the place that called our method.

```ruby
puts 'Fin!'
```

We output the string `'Fin'` to the terminal.

---
[Back to Start](/bitmakerlabs/debugging-guide/blob/master/README.md)
