# Wednesday May 10

## Warm Up

* [Valid Braces](https://www.codewars.com/kata/valid-braces/train/python)

```
# ELIE'S SOLUTION

def validBraces(s):
    while '{}' in s or '[]' in s or '()' in s:
        s = s.replace('{}', '')
        s = s.replace('[]', '')
        s = s.replace('()', '')
    return s == ''
```

```
# TIM'S SOLUTION

def validBraces(string):
  stack = []
  matches = { '(': ')', '[': ']', '{': '}'}
  for c in string:
      if c == '(' or c == '{' or c == '[':
          stack.append(c)
      elif len(stack) == 0:
          return False
      else:
          last = stack.pop()
          if matches[last] != c:
              return False
  
  return len(stack) == 0
```

## Web Scraping

* make an HTTP Get request to get HTML data dump
* use BeautifulSoup to parse the HTML into readable data
* User Agent - [header with info about you](http://www.whoishostingthis.com/tools/user-agent/)

## SVGs 




************************************

## Questions 

* 

## Ideas & Notes

* 

## To Do

* 

## Coming up this week

* 

