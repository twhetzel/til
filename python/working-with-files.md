## How to read in file in Python
```
with open('books_published_last_two_years.txt') as f:
    recent_books = f.read().split('\n')
```

NOTE: Using `with` will automatically close the file

