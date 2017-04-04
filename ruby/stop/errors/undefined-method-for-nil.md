# undefined method `my\_method\_name' for nil:NilClass (NoMethodError)

This error means that you're calling a method on an object that has not been defined properly.

## Example #1: undefined method `my\_method\_name'

Here we're searching for a contact by an id number that does not exist:

```ruby
# my_program

class Contact

  def self.find(id)
    # code that finds a contact by id
    # returns nil if contact is not found
  end

end

contact = Contact(99)
puts contact.full_name
```

The error:

```bash
/path/to/my_program.rb:65:in `<top (required)>':
undefined method `full_name' for nil:NilClass (NoMethodError)
```

We expected contact to be defined, but as the contact wasn't found, we couldn't call the method `full_name` on it.

To fix this error, we could adjust our program like so:

```ruby
contact = Contact(99)
if contact
  puts contact.full_name
else
  puts 'Contact not found'
end
```

## Example #2: undefined method `-'

Here we're trying to determine someones age by the current year and the year they were born:

```ruby
# age.rb
@year_born = 1973
age = @current_year - @year_born
puts age
```

Our error:

```bash
age.rb:2:in `<main>': undefined method `-' for nil:NilClass (NoMethodError)
```

`@current_year` was never defined, and as `@current_year` begins with an `@`, it is treated as an instance variable. Undefined instance variables are set to a `NilClass` instance. Ruby was expecting that `NilClass` had a method called `-` (the subtraction symbol). In other words, the ruby interpreted expected this:

```ruby
 class NilClass
   def -(value)
    2017 - value
  end
end

@year_born = 1973
age = @current_year - @year_born
puts age

```

Of course, we wouldn't add this method to NilClass in this way.

What we need to do is define `@current_year` first:

```ruby
@current_year = 2017
@year_born = 1973
age = @current_year - @year_born
puts age

```

---
[Back to Start](https://github.com/bitmakerlabs/debugging-guide/blob/master/README.md)
