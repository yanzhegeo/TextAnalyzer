# TextAnalyzer
Final Project of Python Developer certificate to make a tool to analyze text from url/.txt/string

In this project, you will create a TextAnalyzer class. The methods of the class are described below. You will do your work in the Analyzing Text IPython notebook included in the project in your Python class files. Be sure to comment your code well.


Create a TextAnalyzer class with the following methods:

**__init__()**
TextAnalyzer objects are instantiated by passing in one of the following to the src parameter:
-A valid URL beginning with "http"
-A path to a text file ending with the file extension "txt"
-A string of text
The __init__() method also includes a src_type parameter, which is used to specify the type of the src argument. Options are:

**discover (default)** - You must write code to discover the type of src.
If the src begins with "http", it is a url.
If the src ends in "txt", it is a path.
Otherwise, it is text.
-url
-path
-text
You should set self._src_type, self._content, and self._orig_content in the __init__() method.

**set_content_to_tag(self, tag, tag_id=None)**
Changes _content to the text within a specific element of an HTML document.
Keyword arguments:
-tag (str) -- Tag to read
-tag_id (str) -- ID of tag to read
It's possible the HTML does not contain the tag being searched. You should use exception handling to catch any errors.

**reset_content(self)**
Resets _content to full text that was originally loaded. Useful after a call to set_content_to_tag().

**_words(self, casesensitive=False):**
Returns words in _content as list.
Keyword arguments:
-casesensitive (bool) -- If False makes all words uppercase.
Hints
After splitting the text into words using the split() method, strip any leading and trailing punctuation using:
[word.strip(string.punctuation) for word in words]

**common_words(self, minlen=1, maxlen=100, count=10, casesensitive=False)**
Returns a list of 2-element tuples of the structure (word, num), where num is the number of times word shows up in _content.
Keyword arguments:
-minlen (int) - Minimum length of words to include.
-maxlen (int) - Maximum length of words to include.
-count (int) - Number of words to include.
-casesensitive (bool) -- If False makes all words uppercase

**char_distribution(self, casesensitive=False, letters_only=False)**
Returns a list of 2-element tuples of the format (char, num), where num is the number of times char shows up in _content. The list should be sorted by num in descending order.
Keyword arguments:
-casesensitive (bool) -- Consider case?
-letters_only (bool) -- Exclude non-letters?

**plot_common_words(self, minlen=1, maxlen=100, count=10, casesensitive=False)**
Plots most common words.
Keyword arguments:
-minlen (int) -- Minimum length of words to include.
-maxlen (int) -- Maximum length of words to include.
-count (int) -- Number of words to include.
-casesensitive (bool) -- If False makes all words uppercase.

**plot_char_distribution(self, casesensitive=False, letters_only=False)**
Plots character distribution.
Keyword arguments:
-casesensitive (bool) -- If False makes all words uppercase.
-letters_only (bool) -- Exclude non-letters?

*Properties*
In addition, the class must include these properties:

**avg_word_length(self)**
The average word length in _content rounded to the 100th place (e.g, 3.82).

**word_count(self)**
The number of words in _content.

**distinct_word_count(self)**
The number of distinct words in _content. This should not be case sensitive: "You" and "you" should be considered the same word.

**words(self)**
A list of all words used in _content, including repeats, in all uppercase letters.

**positivity(self)**
A positivity score calculated as follows:
Create local tally variable with initial value of 0.
Increment tally by 1 for every word in self.words found in positive.txt (in same directory)
Decrement tally by 1 for every word in self.words found in negative.txt (in same directory)
Calculate score as follows:
round( tally / self.word_count * 1000)
