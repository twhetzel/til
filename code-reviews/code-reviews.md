# Code Reviews

## Benefits
* Catch errors
* Ensure readability
* Check standards are met
* Share knowledge among teams

## Conducting a Code Review
* Is the code clean and modular?
    Can I understand the code easily?
    Does it use meaningful names and whitespace?
    Is there duplicated code?
    Can you provide another layer of abstraction?
    Is each function and module necessary?
    Is each function or module too long?

* Is the code efficient?
    Are there loops or other steps we can vectorize?
    Can we use better data structures to optimize any steps?
    Can we shorten the number of calculations needed for any steps?
    Can we use generators or multiprocessing to optimize any steps?

* Is documentation effective?
    Are in-line comments concise and meaningful?
    Is there complex code that's missing documentation?
    Do function use effective docstrings?
    Is the necessary project documentation provided?

* Is the code well tested?
    Does the code high test coverage?
    Do tests check for interesting cases?
    Are the tests readable?
    Can the tests be made more efficient?

* Is the logging effective?
    Are log messages clear, concise, and professional?
    Do they include all relevant and useful information?
    Do they use the appropriate logging level?


## Writing a Code Review
* It's important to be thoughtful of your colleagues ideas and efforts. The goal of code review isn't to make all code follow your personal preferences, but a standard of quality for the whole team.

* Use a code linter, e.g. [pylint]()
It's also a good idea to agree on a style guide as a team to handle disagreements on code style, whether that's an existing style guide or one you create together incrementally as a team.

* Explain issues and make suggestions
BAD: Make model evaluation code its own module - too repetitive.

BETTER: Make the model evaluation code its own module. This will simplify models.py to be less repetitive and focus primarily on building models.

GOOD: How about we consider making the model evaluation code its own module? This would simplify models.py to only include code for building models. Organizing these evaluations methods into separate functions would also allow us to reuse them with different models without repeating code.

* Keep your comments objective
Try to avoid using the words "I" and "you" in your comments. You want to avoid comments that sound personal to bring the attention of the review to the code and not to themselves.

BAD: I wouldn't groupby genre twice like you did here... Just compute it once and use that for your aggregations.

BAD: You create this groupby dataframe twice here. Just compute it once, save it as groupby_genre and then use that to get your average prices and views.

GOOD: Can we group by genre at the beginning of the function and then save that as a groupby object? We could then reference that object to get the average prices and views without computing groupby twice.

* Provide code examples
When providing a code review, you can save the author time and make it easy for them to act on your feedback by writing out your code suggestions.



## References:
[Code Reviews](https://github.com/lyst/MakingLyst/tree/master/code-reviews)

[Code Review Best Practices](https://www.kevinlondon.com/2015/05/05/code-review-best-practices.html)