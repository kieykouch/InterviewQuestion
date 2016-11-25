# InterviewQuestion
Given 2 sorted array, find all common integers.
```python
def findallcommon(l1, l2):
    if not l1:
        return []
    if not l2:
        return []
    if l1[0] == l2[0]:
        return [l1[0]] + findallcommon(l1[1:], l2[1:])
    if l1[0] < l2[0]:
        return [] + findallcommon(l1[1:], l2)
    if l1[0] > l2[0]:
        return [] + findallcommon(l1, l2[1:])
```
