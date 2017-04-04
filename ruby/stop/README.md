# If your program stops executing due to an error:

You're in luck! When your program raises an error, there's a good chance the error is telling you what the issue is (though sometimes it can be difficult to decipher the message).

1. Figure out what line in what file the error is happening
- Decipher the message


### Step 1. Figure out what line in what file the error is happening

Let's look at a generic message:

```bash
/path/to/my_program.rb:30:in `my_method_3': <error message> for #<MyProgram:0x007fd229275440> (ErrorClass)
   from my_program.rb:10:in `my_method_2'
	from my_program.rb:3:in `new'
	from my_program.rb:60:in `<main>
```

This message is telling you:

- the program the error is happening in is located in the folder `/path/to/`
- the error is happening in the file `my_program.rb`
- how it got to the error (aka: a stack trace):
    - first it executed line 60
    - line 60 called the `new` method on line 3
    - line 3 called `my_method_2` on line 10
    - line 10 called `my_method_3` on line 20
- the error is happening on line 30

### Step 2. Decipher the Message

Now that you know where the error is happening, let's look at common error messages:

- [syntax error, unexpected end-of-input, expecting keyword_end](errors/unexpected-end.md)
- [undefined local variable or method (NameError)](errors/undefined-var-or-method.md)
- [undefined method `my\_method\_name' for nil:NilClass (NoMethodError)](errors/undefined-method-for-nil.md)


### Step 3. Google the error

Put the error into google, and try to remove any context specific information from the error.

For example, if I had the error:

```bash
my_simple_class.rb:5:in `<class:MySimpleClass>':
undefined local variable or method `baby_cakes'
for MySimpleClass:Class (NameError)
from my_simple_class.rb:3:in `<main>'
```

I would remove my filename (`my_simple_class.rb`), line number (`5`), class name (`MySimpleClass`), my method (`babycakes`).

Thus I would be left with:

`undefined local variable or method NameError`

and I'd google just that.

It would likely lead me to a stackoverflow post. Skip to the **Question** part of the stackoverflow post and go directly to the answers. Look at the number one and number two answers (as occassionally the number one is marked correct, even though the number two answer is better).

If you understand the answer completely and you fix the your issue, then great, time to move on to your next bug!

However, if you don't understand the answer, the next step is to look up what the answer is saying in the ruby documentation and try to understand the methods there.

---
[Back to Previous Page](..)

[Back to Start](https://github.com/bitmakerlabs/debugging-guide/blob/master/README.md)
