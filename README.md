# Regexes

## Function Matcher
### Quick Navigation
- How many lists/dicts/sets/tuples you can put in another list/dict/set/tuple is [here](#fm-lsd).
- How long the file with Single Quotes is [here](#fm-lcl)
### What is it?
- Function Matcher regex is a regex to find all regexes that look the same as a python function, but with double closing/opening Steep Brackets. This Matcher supports nested structures.
### Example(SingleQuotes):
- [[ calc() ]] - Correct
- [[ calc(       ) ]] - Correct
- [[ calc(name=' value ') ]] - Correct
- [[ calc(name=911) ]] - Correct
- [[ calc(name=True) ]] - Correct
- [[ calc(name=')') ]] - Correct
- [[ calc( , ) ]] - Incorrect (Syntax is wrong)
- [[ calc(,) ]] - Incorrect (Syntax is wrong)
- [[ calc('', ) ]] - Incorrect (Syntax is wrong)
- [[ eval() ]] - Incorrect (Functions are filtered)
### How to use:
1. Get the file, or copy paste it into a file.
2. To limit your own custom functions, use a script and call the replace method:
-  1 reader = open('my/file/path.anything', 'r')
-  2 writer = open('my/file/path.anything', 'w')
-  3 txt = reader.read()
-  4 writer.write(txt.replace('calc|find_(chambers|users|items)', 'myCustomFunctionsAsRegex'))
### Engine:
- Please never use this regex in any engine that is a NFA engine, such as python's built-in re library, as it can and will make catastrophic backtrackings.
### Last Supported Depth: 3 <a class="function_matcher" id='fm-lsd'></a>
### Last Captured Length: 1513390 <a class="function_matcher" id='fm-lcl'></a>
