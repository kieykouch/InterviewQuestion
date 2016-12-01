# Hired.com Sign Up Challenges

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
### Check if 2 lists same length have the anagram for each word
iterate the 2 lists at the same, sorted each words in lowercase, then compare both
```python
def AnagramValidation(list1, list2):
    for List1Word, List2Word in zip(list1, list2):
        if len(List1Word) != len(List2Word):
            print("" + List1Word + " is not Anagram with "+List2Word)
            continue
        if sorted(List1Word.lower()) != sorted(List2Word.lower()):
            print("" + List1Word + " is not Anagram with "+List2Word)
        else:
            print("" + List1Word + " is Anagram with "+List2Word)

def AnagramValidation2(list1, list2):
    print ([sorted(List1Word.lower()) == sorted(List2Word.lower()) for List1Word, List2Word in zip(list1, list2)])
    
a = ['cinema','host','aab','train']
b = ['iceman', 'shot', 'bab', 'rain']
AnagramValidation(a, b)
#AnagramValidation2(a, b)

```
