# When your program runs, but not with the expected result

Keep in mind that a program is a series of steps that continually transforms state. When you encounter unexpectd results, it means that the program at some point is transforming the current state in a way that you do not fully understand.

Use the following techniques to try to solve the issue:

- [follow the flow of your program's execution](try/flow.md)
- think about the scope of any variables you're working with (local, instance, class, global)
- think about methods you are calling, and what (if any), arguments you're providing those methods
- think about the results methods are returning
- think about the datatypes that you're working with
- use `puts` debugging
- use `binding.pry` and `binding.irb` to intercept and inspect your code as it's executing
- try working out the issue inside of a REPL (`irb` or `pry`)
- use `inspect` to look inside of an object
- use `raise` to cause a runtime error
- try to reproduce what you're doing in the simplest way possible, and then get it working in that way first

---
[Back to Previous Page](..)

[Back to Start](https://github.com/bitmakerlabs/debugging-guide/blob/master/README.md)
