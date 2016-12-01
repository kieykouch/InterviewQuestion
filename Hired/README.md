# Hire Sign Up Challenges

### Check if the Braces is Valid, print 0 for invalid, 1 for valid.
Stack the open bracket. if the close appears, pop for the list, compare it, if it is not its pair, consider this string has invalid brace format.
```python
def ValidateBrace(Word):
    Stack = []
    for Char in Word:
        if Char == "(" or Char == "[" or Char == "{":
            Stack.append(Char)
        else:
            #If Stack is Empty, then it is invalid
            if len(Stack) == 0:
                print(0)
                return
            OpenBrace = Stack.pop()
            if (Char == ")" and OpenBrace != "(") or (Char == "}" and OpenBrace != "{") or (Char == "]" and OpenBrace != "[") :
                print(0)
                return
    print(1)

```
