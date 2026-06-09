<!-- Badges -->
![Author Mail](https://img.shields.io/badge/Email-github.py.coder%40gmail.com.-red?logo=github)
![Version](https://img.shields.io/Version-v0.0.1-red?logo=github)
![License](https://img.shields.io/badge/License-MIT-red?logo=github)
![regex size](https://img.shields.io/badge/size-45.5k--characters-orange)

# 1. Function Matcher Raw
## 1. Quick Look
1. from google.re2 import re   # recommended engine
2. pattern = open("FunctionMatcher/DoubleQuotes.txt").read()
3. result = re.findall(pattern, "[[ calc(name='embedded python code finder') ]]")

## 2. What is it?
A regex that parses Python‑like function calls inside double square brackets [[ ... ]] – supports nested structures, keyword arguments, and multiple string styles.

## 3. Why would anyone use this?

- Embedded DSLs in text files (configs, templates)

- Lightweight function calling without a full parser

- Educational: extreme regex design

## 4. How it works

- Matches [[, then function name, then (, then arguments, then ), then ]]

- Handles nested dicts, lists, tuples(depth 1)<a class='function_matcher' id='fm-lsd'></a>, and even function calls inside arguments (depth 1)

- Three string modes: double, single, triple‑double quotes

<div style='background-color: red; border-radius: 6;'>
## 5. Critical Warning
DO <strong>NOT</strong> USE WITH TRADITIONAL NFA ENGINES (Python re, PCRE, Perl).
Use Google RE2 only – otherwise <strong>catastrophic backtracking</strong> will freeze your program.
</div>

## 6. How to install?
1. Download the file and put it in e.g., ~/Desktop
2. Learn re2 if you don't know it yet.
3. Write code:
- import re2
- with open('/home/user/Desktop') as f:
-     regex = f.read()
- # Optional - change with your own pattern
- regex = regex.replace('calc|find_(chambers|users|items)', 'calc|step|search') # Use safe functions, not os.exec or eval
- pattern = re2.compile(regex)
- match = pattern.search('[[ calc(calculation='sqrt(911)') ]]')
## 7. What to avoid?
Here is an example of what to avoid:
- import re
- with open('/home/user/Desktop') as f:
-     regex = f.read()
- pattern_dangerous = re.compile(regex)
- GoodbyeMyAppILovedYou = pattern_dangerous.search('[[ calc(calculation='10 + 10) ]]') # Missed quote = crash.

# 2. [Contributing](CONTRIBUTING.md)
# 3. [License](LICENSE.md)
