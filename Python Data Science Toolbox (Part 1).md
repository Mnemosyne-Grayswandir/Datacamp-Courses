
# Python Data Science Toolbox (Part 1)

> URL: https://app.datacamp.com/learn/courses/python-data-science-toolbox-part-1

## Chapter 1 - Writing your own functions
### **Write a simple function**
Instructions:
 - Complete the function header by adding the appropriate function name, `shout`.
 - In the function body, **concatenate** the string, `'congratulations'` with another string, `'!!!'`. Assign the result to `shout_word`.
 - Print the **value** of `shout_word`.
 - Call the `shout` function.

 ````
# Define the function shout
def shout():
    """Print a string with three exclamation marks"""
    # Concatenate the strings: shout_word
    word = "congratulations"
    shout_word = word + "!!!"
    # Print shout_word
    print(shout_word)

# Call shout
shout()
````

### **Single-parameter functions**
Instructions:
 - Complete the function header by adding the parameter name, `word`.
 - Assign the result of concatenating `word` with `'!!!'` to `shout_word`.
 - Print the value of `shout_word`.
 - Call the `shout()` function, passing to it the string, `'congratulations'`.

 ````
# Define shout with the parameter, word
def shout(word):
    """Print a string with three exclamation marks"""
    # Concatenate the strings: shout_word
    shout_word = word + '!!!'

    # Print shout_word
    print(shout_word)

# Call shout with the string 'congratulations'
shout("congratulations")
````
### **Functions that return single values**
Instructions:
 - In the function body, concatenate the string in `word` with `'!!!'` and assign to `shout_word`.
 - Replace the `print()` statement with the appropriate `return` statement.
- Call the `shout()` function, passing to it the string, `'congratulations'`, and assigning the call to the variable, `yell`.
- To check if `yell` contains the value returned by `shout()`, print the value of `yell`.

````
# Define shout with the parameter, word
def shout(word):
    """Return a string with three exclamation marks"""
    # Concatenate the strings: shout_word
    shout_word = word + "!!!"

    # Replace print with return
    return shout_word

# Pass 'congratulations' to shout: yell
yell = shout("congratulations")

# Print yell
print(yell)
````

### **Functions with multiple parameters**
Instructions: 
 - Modify the function header such that it accepts two parameters, `word1` and `word2`, in that order.
 - Concatenate each of `word1` and `word2` with `'!!!'` and assign to `shout1` and `shout2`, respectively.
 - Concatenate `shout1` and `shout2` together, in that order, and assign to `new_shout`.
 - Pass the strings `'congratulations'` and `'you'`, in that order, to a call to `shout()`. Assign the return value to `yell`.

````
# Define shout with parameters word1 and word2
def shout(word1, word2):
    """Concatenate strings with three exclamation marks"""
    # Concatenate word1 with '!!!': shout1
    shout1 = word1 + "!!!"
        
    # Concatenate word2 with '!!!': shout2
    shout2 = word2 + "!!!"
        
    # Concatenate shout1 with shout2: new_shout
    new_shout = shout1 + shout2

    # Return new_shout
    return new_shout

# Pass 'congratulations' and 'you' to shout(): yell
yell = shout("congratulations", "you")

# Print yell
print(yell)
````

### **A brief introduction to tuples**
Instructions:
 - Unpack `nums` to the variables `num1`, `num2`, and `num3`.
 - Construct a new tuple, `even_nums` composed of the same elements in `nums`, but with the 1st element replaced with the value, 2.

````
# Unpack nums into num1, num2, and num3
num1 = 3
num2 = 4
num3 = 6

# Construct even_nums
even_nums = (2,4,6)
````

### **Functions that return multiple values**
Instructions:
 - Modify the function header such that the function name is now `shout_all`, and it accepts two parameters, `word1` and `word2`, in that order.
 - Concatenate the string `'!!!'` to each of `word1` and `word2` and assign to `shout1` and `shout2`, respectively.
 - Construct a tuple `shout_words`, composed of `shout1` and `shout2`.
 - Call `shout_all()` with the strings `'congratulations'` and `'you'` and assign the result to `yell1` and `yell2` (remember, `shout_all()` returns 2 variables!).

````
# Define shout_all with parameters word1 and word2
def shout_all(word1, word2):
        
    # Concatenate word1 with '!!!': shout1
    shout1 = word1 + "!!!"
        
    # Concatenate word2 with '!!!': shout2
    shout2 = word2 + "!!!"
        
    # Construct a tuple with shout1 and shout2: shout_words
    shout_words = (shout1, shout2)

    # Return shout_words
    return shout_words

# Pass 'congratulations' and 'you' to shout_all(): yell1, yell2
yell1, yell2 = shout_all("congratulations", "you")

# Print yell1 and yell2
print(yell1)
print(yell2)
````

 ### **Bringing it all together (1)**
 Instructions:
  - Import the pandas package with the alias `pd`.
  - Import the file `'tweets.csv'` using the pandas function `read_csv()`. Assign the resulting DataFrame to `df`.
  - Complete the `for` loop by iterating over `col`, the `'lang'` column in the DataFrame `df`.
  - Complete the bodies of the `if-else` statements in the for loop: if the key is in the dictionary `langs_count`, add `1` to the value corresponding to this key in the dictionary, **else** add the key to `langs_count` and set the corresponding value to `1`. Use the loop variable `entry` in your code.

````
# Import pandas
import pandas as pd

# Import Twitter data as DataFrame: df
df = pd.read_csv('tweets.csv')

# Initialize an empty dictionary: langs_count
langs_count = {}

# Extract column from DataFrame: col
col = df['lang']

# Iterate over lang column in DataFrame
for entry in col:

    # If the language is in langs_count, add 1 
    if entry in langs_count.keys():
            langs_count[entry] += 1
    # Else add the language to langs_count, set the value to 1
    else:
        langs_count[entry] = 1

# Print the populated dictionary
print(langs_count)
````

### **Bringing it all together (2)**
 Instructions:
  - Define the function `count_entries()`, which has two parameters. The first parameter is `df` for the DataFrame and the second is `col_name` for the column name.
  - Complete the bodies of the `if-else` statements in the `for` loop: **if** the key is in the dictionary `langs_count`, add `1` to its current value, **else** add the key to `langs_count` and set its value to `1`. Use the loop variable `entry` in your code.
  - Return the `langs_count` dictionary from inside the `count_entries()` function.
  - Call the `count_entries()` function by passing to it `tweets_df` and the name of the column, `'lang'`. Assign the result of the call to the variable `result`.

````
# Define count_entries()
def count_entries(df, col_name):
    """Return a dictionary with counts of occurrences as value for each key."""

    # Initialize an empty dictionary: langs_count
    langs_count = {}
        
    # Extract column from DataFrame: col
    col = df[col_name]
        
    # Iterate over lang column in DataFrame
    for entry in col:

        # If the language is in langs_count, add 1
        if entry in langs_count.keys():
            langs_count[entry] += 1
         # Else add the language to langs_count, set the value to 1
        else:
            langs_count[entry] = 1

    # Return the langs_count dictionary
    return langs_count

# Call count_entries(): result
result = count_entries(tweets_df, 'lang')

# Print the result
print(result)
````

## Chapter 2 - Default arguments, variable-length arguments and scope
### **The keyword global**
Instructions:
 - Use the keyword `global` to alter the object `team` in the global scope.
 - Change the value of `team` in the global scope to the string `"justice league"`. Assign the result to `team`.
 - Hit the Submit button to see how executing your newly defined function `change_team()` changes the value of the name `team`!

````
# Create a string: team
team = "teen titans"

# Define change_team()
def change_team():
    """Change the value of the global variable team."""

    # Use team in global scope
    global team

    # Change the value of team in global: team
    team = "justice league"

# Print team
print(team)

# Call change_team()
change_team()

# Print team
print(team)
````

### **Nested Functions I**
Instructions:
 - Complete the function header of the nested function with the function name `inner()` and a single parameter `word`.
 - Complete the return value: each element of the tuple should be a call to `inner()`, passing in the parameters from `three_shouts()` as arguments to each call.

````
# Define three_shouts
def three_shouts(word1, word2, word3):
    """Returns a tuple of strings concatenated with '!!!'."""

    # Define inner
    def inner(word):
        """Returns a string concatenated with '!!!'."""
            return word + '!!!'

    # Return a tuple of strings
    return (inner(word1), inner(word2), inner(word3))

# Call three_shouts() and print
print(three_shouts('a', 'b', 'c'))
````

### **Nested Functions II**
Instructions:
 - Complete the function header of the inner function with the function name `inner_echo()` and a single parameter `word1`.
 - Complete the function `echo()` so that it returns `inner_echo`.
 - We have called `echo()`, passing 2 as an argument, and assigned the resulting function to `twice`. Your job is to call `echo()`, passing 3 as an argument. Assign the resulting function to `thrice`.
 - Hit Submit to call `twice()` and `thrice()` and print the results.

````
# Define echo
def echo(n):
    """Return the inner_echo function."""

    # Define inner_echo
    def inner_echo(word1):
        """Concatenate n copies of word1."""
        echo_word = word1 * n
        return echo_word

    # Return inner_echo
    return inner_echo

# Call echo: twice
twice = echo(2)

# Call echo: thrice
thrice = echo(3)

# Call twice() and thrice() then print
print(twice('hello'), thrice('hello'))
````

### **The keyword nonlocal and nested functions**
Instructions:
 - Assign to `echo_word` the string `word`, concatenated with itself.
 - Use the keyword `nonlocal` to alter the value of `echo_word` in the enclosing scope.
 - Alter `echo_word` to `echo_word` concatenated with '!!!'.
 - Call the function `echo_shout()`, passing it a single argument 'hello'.

````
# Define echo_shout()
def echo_shout(word):
    """Change the value of a nonlocal variable"""
        
    # Concatenate word with itself: echo_word
    echo_word = word * 2
        
    # Print echo_word
    print(echo_word)
        
    # Define inner function shout()
    def shout():
        """Alter a variable in the enclosing scope"""    
        # Use echo_word in nonlocal scope
            nonlocal echo_word
            
        # Change echo_word to echo_word concatenated with '!!!'
        echo_word += "!!!"
        
    # Call function shout()
    shout()
        
    # Print echo_word
    print(echo_word)

# Call function echo_shout() with argument 'hello'
echo_shout("hello")
````

### **Functions with one default argument**
Instructions:
- Complete the function header with the function name `shout_echo`. It accepts an argument `word1` and a default argument `echo` with default value `1`, in that order.
 - Use the `*` operator to concatenate `echo` copies of `word1`. Assign the result to `echo_word`.
 - Call `shout_echo()` with just the string, `"Hey"`. Assign the result to `no_echo`.
 - Call `shout_echo()` with the string `"Hey"` and the value `5` for the default argument, `echo`. Assign the result to `with_echo`.

````
# Define shout_echo
def shout_echo(word1, echo=1):
    """Concatenate echo copies of word1 and three
    exclamation marks at the end of the string."""

    # Concatenate echo copies of word1 using *: echo_word
    echo_word = word1 * echo

    # Concatenate '!!!' to echo_word: shout_word
    shout_word = echo_word + '!!!'

    # Return shout_word
    return shout_word

# Call shout_echo() with "Hey": no_echo
no_echo = shout_echo("Hey")

# Call shout_echo() with "Hey" and echo=5: with_echo
with_echo = shout_echo("Hey", 5)

# Print no_echo and with_echo
print(no_echo)
print(with_echo)
````

### **Functions with multiple default arguments**
Instructions:
 - Complete the function header with the function name `shout_echo`. It accepts an argument `word1`, a default argument `echo` with default value `1` and a default argument `intense` with default value `False`, in that order.
 - In the body of the `if` statement, make the string object `echo_word` upper case by applying the method `.upper()` on it.
 - Call `shout_echo()` with the string, `"Hey"`, the value `5` for `echo` and the value `True` for `intense`. Assign the result to `with_big_echo`.
 - Call `shout_echo()` with the string `"Hey"` and the value `True` for `intense`. Assign the result to `big_no_echo`.

````
# Define shout_echo
def shout_echo(word1, echo=1, intense=False):
    """Concatenate echo copies of word1 and three
    exclamation marks at the end of the string."""

    # Concatenate echo copies of word1 using *: echo_word
    echo_word = word1 * echo

    # Make echo_word uppercase if intense is True
    if intense is True:
        # Make uppercase and concatenate '!!!': echo_word_new
        echo_word_new = echo_word.upper() + '!!!'
    else:
        # Concatenate '!!!' to echo_word: echo_word_new
        echo_word_new = echo_word + '!!!'

    # Return echo_word_new
    return echo_word_new

# Call shout_echo() with "Hey", echo=5 and intense=True: with_big_echo
with_big_echo = shout_echo("Hey", 5, True)

# Call shout_echo() with "Hey" and intense=True: big_no_echo
big_no_echo = shout_echo("Hey", 1,True)

# Print values
print(with_big_echo)
print(big_no_echo)
````

### **Functions with variable-length arguments (\*args)**
Instructions:
 - Complete the function header with the function name `gibberish`. It accepts a single flexible argument `*args`.
 - Initialize a variable `hodgepodge` to an empty string.
 - Return the variable `hodgepodge` at the end of the function body.
 - Call `gibberish()` with the single string, `"luke"`. Assign the result to `one_word`.
 - Hit the Submit button to call `gibberish()` with multiple arguments and to print the value to the Shell.

````
# Define gibberish
def gibberish(*args):
    """Concatenate strings in *args together."""

    # Initialize an empty string: hodgepodge
    hodgepodge = ""

    # Concatenate the strings in args
    for word in args:
        hodgepodge += word

    # Return hodgepodge
    return hodgepodge

# Call gibberish() with one string: one_word
one_word = gibberish("luke")

# Call gibberish() with five strings: many_words
many_words = gibberish("luke", "leia", "han", "obi", "darth")

# Print one_word and many_words
print(one_word)
print(many_words)
````

### **Function with variable-length keyword arguments (\*\*kwargs)**
Instructions:
 - Complete the function header with the function name `report_status`. It accepts a single flexible argument `**kwargs`.
 - Iterate over the key-value pairs of `kwargs` to print out the keys and values, separated by a colon ':'.
 - In the first call to `report_status()`, pass the following keyword-value pairs: `name="luke"`, `affiliation="jedi"` and `status="missing"`.
 - In the second call to `report_status()`, pass the following keyword-value pairs: `name="anakin"`, `affiliation="sith lord"` and `status="deceased"`.

````
# Define report_status
def report_status(**kwargs):
    """Print out the status of a movie character."""

    print("\nBEGIN: REPORT\n")

    # Iterate over the key-value pairs of kwargs
    for key, value in kwargs.items():
        # Print out the keys and values, separated by a colon ':'
        print(key + ": " + value)

    print("\nEND REPORT")

# First call to report_status()
report_status(name="luke", affiliation="jedi", status="missing")

# Second call to report_status()
report_status(name="anakin", affiliation="sith lord", status="deceased")
````

### **Bringing it all together (1)**
Instructions:
 - Complete the function header by supplying the parameter for a DataFrame `df` and the parameter `col_name` with a default value of `'lang'` for the DataFrame column name.
 - Call `count_entries()` by passing the `tweets_df` DataFrame and the column name `'lang'`. Assign the result to `result1`. Note that since `'lang'` is the default value of the `col_name` parameter, you don't have to specify it here.
 - Call `count_entries()` by passing the `tweets_df` DataFrame and the column name `'source'`. Assign the result to `result2`.

````
# Define count_entries()
def count_entries(df, col_name):
    """Return a dictionary with counts of occurrences as value for each key."""

    # Initialize an empty dictionary: cols_count
    cols_count = {}

    # Extract column from DataFrame: col
    col = df[col_name]
        
    # Iterate over the column in DataFrame
    for entry in col:

        # If entry is in cols_count, add 1
        if entry in cols_count.keys():
            cols_count[entry] += 1

        # Else add the entry to cols_count, set the value to 1
        else:
            cols_count[entry] = 1

    # Return the cols_count dictionary
    return cols_count

# Call count_entries(): result1
result1 = count_entries(tweets_df, "lang")

# Call count_entries(): result2
result2 = count_entries(tweets_df, "source")

# Print result1 and result2
print(result1)
print(result2)
````

### **Bringing it all together (2)**
Instructions:
 - Complete the function header by supplying the parameter for the DataFrame `df` and the flexible argument `*args`.
 - Complete the `for` loop within the function definition so that the loop occurs over the tuple `args`.
 - Call `count_entries()` by passing the `tweets_df` DataFrame and the column name `'lang'`. Assign the result to `result1`.
 - Call `count_entries()` by passing the `tweets_df` DataFrame and the column names `'lang'` and `'source'`. Assign the result to `result2`.

````
# Define count_entries()
def count_entries(df, *args):
    """Return a dictionary with counts of
    occurrences as value for each key."""
        
    #Initialize an empty dictionary: cols_count
    cols_count = {}
        
    # Iterate over column names in args
    for col_name in args:
        
        # Extract column from DataFrame: col
        col = df[col_name]
        
        # Iterate over the column in DataFrame
        for entry in col:
        
            # If entry is in cols_count, add 1
            if entry in cols_count.keys():
                cols_count[entry] += 1
        
            # Else add the entry to cols_count, set the value to 1
            else:
                cols_count[entry] = 1

    # Return the cols_count dictionary
    return cols_count

# Call count_entries(): result1
result1 = count_entries(tweets_df, "lang")

# Call count_entries(): result2
result2 = count_entries(tweets_df, "lang", "source")

# Print result1 and result2
print(result1)
print(result2)
````

## Chapter 3 - Lambda functions and error-handling
### **Writing a lambda function you already know**
Instructions:
 - Define the lambda function `echo_word` using the variables `word1` and `echo`. Replicate what the original function definition for `echo_word()` does above.
 - Call `echo_word()` with the string argument `'hey'` and the value `5`, in that order. Assign the call to `result`.

```
# Define echo_word as a lambda function: echo_word
echo_word = (lambda word1, echo: word1 * echo)

# Call echo_word: result
result = echo_word("hey", 5)

# Print result
print(result)
```

### **Map() and lambda functions**
Instructions:
 - In the `map()` call, pass a lambda function that concatenates the string `'!!!'` to a string `item`; also pass the list of strings, `spells`. Assign the resulting map object to `shout_spells`.
 - Convert `shout_spells` to a list and print out the list.

```
# Create a list of strings: spells
spells = ["protego", "accio", "expecto patronum", "legilimens"]

# Use map() to apply a lambda function over spells: shout_spells
shout_spells = map(lambda item: item + "!!!", spells)

# Convert shout_spells to a list: shout_spells_list
shout_spells_list = list(shout_spells)

# Print the result
print(shout_spells_list)
```

### **Filter() and lambda functions**
Instructions:
 - In the `filter()` call, pass a lambda function and the list of strings, `fellowship`. The lambda function should check if the number of characters in a string `member` is greater than 6; use the `len()` function to do this. Assign the resulting filter object to `result`.
 - Convert `result` to a list and print out the list.

```
# Create a list of strings: fellowship
fellowship = ['frodo', 'samwise', 'merry', 'pippin', 'aragorn', 'boromir', 'legolas', 'gimli', 'gandalf']

# Use filter() to apply a lambda function over fellowship: result
result = filter(lambda member: len(member) > 6, fellowship)

# Convert result to a list: result_list
result_list = list(result)

# Print result_list
print(result_list)
```

### **Reduce() and lambda functions**
Instructions:
 - Import the `reduce` function from the `functools` module.
 - In the `reduce()` call, pass a lambda function that takes two string arguments `item1` and `item2` and concatenates them; also pass the list of strings, `stark`. Assign the result to `result`. The first argument to `reduce()` should be the lambda function and the second argument is the list `stark`.

```
# Import reduce from functools
from functools import reduce

# Create a list of strings: stark
stark = ['robb', 'sansa', 'arya', 'brandon', 'rickon']

# Use reduce() to apply a lambda function over stark: result
result = reduce(lambda item1, item2: item1 + item2, stark)

# Print the result
print(result)
```

### **Error handling with try-except**
Instructions:
 - Initialize the variables `echo_word` and `shout_words` to empty strings.
 - Add the keywords `try` and `except` in the appropriate locations for the exception handling block.
 - Use the `*` operator to concatenate `echo` copies of `word1`. Assign the result to `echo_word`.
 - Concatenate the string `'!!!'` to `echo_word`. Assign the result to `shout_words`.

```
# Define shout_echo
def shout_echo(word1, echo=1):
    """Concatenate echo copies of word1 and three
    exclamation marks at the end of the string."""

    # Initialize empty strings: echo_word, shout_words
    echo_word = ""
    shout_words = ""    

    # Add exception handling with try-except
    try:
        # Concatenate echo copies of word1 using *: echo_word
        echo_word = word1 * echo

        # Concatenate '!!!' to echo_word: shout_words
        shout_words = echo_word + "!!!"
    except:
        # Print error message
        print("word1 must be a string and echo must be an integer.")

    # Return shout_words
    return shout_words

# Call shout_echo
shout_echo("particle", echo="accelerator")
```

### **Error handling by raising an error**
Instructions:
 - Complete the `if` statement by checking if the value of `echo` is less than 0.
 - In the body of the `if` statement, add a `raise` statement that raises a `ValueError` with message `'echo must be greater than or equal to 0'` when the value supplied by the user to `echo` is less than 0.

```
# Define shout_echo
def shout_echo(word1, echo=1):
    """Concatenate echo copies of word1 and three
    exclamation marks at the end of the string."""

    # Raise an error with raise
    if echo < 0:
        raise ValueError("echo must be greater than or equal to 0")

    # Concatenate echo copies of word1 using *: echo_word
    echo_word = word1 * echo

    # Concatenate '!!!' to echo_word: shout_word
    shout_word = echo_word + '!!!'

    # Return shout_word
    return shout_word

# Call shout_echo
shout_echo("particle", echo=5)
```

### **Bringing it all together (1)**
Instructions:
 - In the `filter()` call, pass a lambda function and the sequence of tweets as strings, `tweets_df['text']`. The lambda function should check if the first 2 characters in a tweet `x` are 'RT'. Assign the resulting filter object to `result`. To get the first 2 characters in a tweet `x`, use `x[0:2]`. To check equality, use a Boolean filter with `==`.
 - Convert `result` to a list and print out the list.

```
# Select retweets from the Twitter DataFrame: result
result = filter(lambda tweet: tweet.startswith('RT'), tweets_df['text'])

# Create list from filter object result: res_list
res_list = list(result)

# Print all retweets in res_list
for tweet in res_list:
    print(tweet)
```

### **Bringing it all together (2)**
Instructions:
 - Add a `try` block so that when the function is called with the correct arguments, it processes the DataFrame and returns a dictionary of results.
 - Add an `except` block so that when the function is called incorrectly, it displays the following error message: `'The DataFrame does not have a ' + col_name + ' column.'`.

```
# Define count_entries()
def count_entries(df, col_name='lang'):
    """Return a dictionary with counts of
    occurrences as value for each key."""

    # Initialize an empty dictionary: cols_count
    cols_count = {}

    # Add try block
    try:
        # Extract column from DataFrame: col
        col = df[col_name]
        
        # Iterate over the column in DataFrame
        for entry in col:
    
            # If entry is in cols_count, add 1
            if entry in cols_count.keys():
                cols_count[entry] += 1
            # Else add the entry to cols_count, set the value to 1
            else:
                cols_count[entry] = 1
    
        # Return the cols_count dictionary
        return cols_count

    # Add except block
    except:
        print("The DataFrame does not have a" + col_name + "column.")

# Call count_entries(): result1
result1 = count_entries(tweets_df, 'lang')

# Print result1
print(result1)
```

### **Bringing it all together (3)**
Instructions:
 - If `col_name` is not a column in the DataFrame `df`, raise a `ValueError 'The DataFrame does not have a ' + col_name + ' column.'`.
 - Call your new function `count_entries()` to analyze the `'lang'` column of `tweets_df`. Store the result in `result1`.
 - Print `result1`. This has been done for you, so hit 'Submit Answer' to check out the result. In the next exercise, you'll see that it raises the necessary `ValueErrors`.

```
# Define count_entries()
def count_entries(df, col_name='lang'):
    """Return a dictionary with counts of
    occurrences as value for each key."""
    
    # Raise a ValueError if col_name is NOT in DataFrame
    if col_name not in df.columns:
        raise ValueError('The DataFrame does not have a ' + col_name + ' column.')

    # Initialize an empty dictionary: cols_count
    cols_count = {}
    
    # Extract column from DataFrame: col
    col = df[col_name]
    
    # Iterate over the column in DataFrame
    for entry in col:

        # If entry is in cols_count, add 1
        if entry in cols_count.keys():
            cols_count[entry] += 1
            # Else add the entry to cols_count, set the value to 1
        else:
            cols_count[entry] = 1
        
        # Return the cols_count dictionary
    return cols_count

# Call count_entries(): result1
result1 = count_entries(tweets_df, "lang")

# Print result1
print(result1)
```