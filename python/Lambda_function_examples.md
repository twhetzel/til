# Lambda Functions

## Description
A lambda function is an anonymous function. It can take any number of arguments, but can only have one expression. It does not have a return statement.

## Examples
### Add 10 to variable a and return the result.
```
x = lambda a : a + 10
print(x(5))
```

### Multiply two numbers together and return the result.
```
x = lambda a, b : a * b
print(x(5, 6))
```

### Convert comma-separated value to list and strip whitespace from each value
```
items = "apple ,  bannana, pear"
x = list(map(lambda item: item.strip(), items.split(",")))
print(x)
```
