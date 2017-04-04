# syntax error, unexpected end-of-input, expecting keyword_end

This means that a syntax block was started, but never ended. The most common situtations are when we define a **class** or **method** or use a  **control expression** (`if`, `switch`, loop, `do` block).

## Step 1: Fix Indenting

To fix this, first fix your indenting. This will usually make it obvious where the `end` is missing. You can see where your indenting is off by using the warning flag when running your ruby program: `e.g. ruby -w my_program.rb`.

## Step 2: Decipher the warning

Look at the line numbers the warnings point to. From these, you may be able to figure out where your end is missing. If not, go to the next step.

## Step 3: Isolate Code Causing Error

If you're not able to figure out where the issue is due to the warnings, try commentings out chunks of code and seeing if you can get your program run. Then uncomment and run your code chunk by chunk until the error returns. Using this method you'll be able to isolate where your `end` is missing.

## Example

```ruby
# my_simple_class.rb

class MySimpleClass

  def hello(name = nil)

    if name
      puts "Hello #{name}"
    else
      puts "Come on, ya gotta tell me yer name!"
    end

  end

  def goodbye(name = nil)

    if name
      puts "See Ya Later, #{name}"
    else
      puts "You're leaving already? I didn't even get your name!"

  end

  def count_to_ten
    [1, 2, 3, 4, 5, 6, 7, 8, 9, 10].each do |number|
      puts number
    end
  end

end

MySimpleClass.new.hello('Sean')
MySimpleClass.new.count_to_ten
MySimpleClass.new.goodbye('Sean')

```

```bash
$ ruby my_simple_class.rb
my_simple_class.rb:34: syntax error, unexpected end-of-input, expecting keyword_end
```

Here we know we're missing the `end` keyword, but the error is pointing to the last line of our program, which isn't very helpful in isolating the error.

Let's try running it again with the `-w` flag:

```bash
$ ruby -w my_simple_class.rb
my_simple_class.rb:22: warning: mismatched indentations at 'end' with 'if' at 17
my_simple_class.rb:30: warning: mismatched indentations at 'end' with 'def' at 15
my_simple_class.rb:34: syntax error, unexpected end-of-input, expecting keyword_end
```

Ah, this is much more helpful. It's telling us that the `end` keyword on line 22 isn't matching up with the

```ruby
if name
```

on line 17. This is because this is this specific `if` statement that is missing the `end`.

---
[Back to Start](https://github.com/bitmakerlabs/debugging-guide/blob/master/README.md)
