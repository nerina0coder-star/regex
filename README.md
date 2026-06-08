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
- Please never use this regex in any engine that is a NFA engine, such as python's built-in re library, as it can and will make catastrophic backtrackings. I recommend you the google-re2 if you ever want to use this.
### Use Cases:
- Letting users call functions from files in one regex call. Tho a safer approach is to use this + google-re2, ast or carefully planned lexers/parsers.
### Last Supported Depth: 1 <a class="function_matcher" id='fm-lsd'></a>
### Last Captured Length: 45552 <a class="function_matcher" id='fm-lcl'></a>


### license

<strong>MIT License</strong>

Copyright (c) <strong>2026 nerina0coder-star</strong>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

<strong>THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.</strong>
