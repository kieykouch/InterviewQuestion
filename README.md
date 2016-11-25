# InterviewQuestions
## This is Computer Science Interview Questions I have solved/studied and wish to keep them available for everyone (Bear in mind, I'm still learning).

### Given 2 sorted array (n,m size), find all common integers.
go thru 2 lists at the same times, only increment one list if the value is less than the other, otherwise, keep the result and incrent both. O(n+m)
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
        
def findallcommon2(l1,l2):
    if not l1:
        return []
    if not l2:
        return []
    Result = []
    IndexL1 = 0
    IndexL2 = 0
    while(IndexL1 < len(l1) and IndexL2<len(l2)):
        if l1[IndexL1] == l2[IndexL2]:  
            Result.append(l2[IndexL2])
            IndexL2= IndexL2+1
            IndexL1= IndexL1+1
        elif l1[IndexL1] < l2[IndexL2]:
            IndexL1= IndexL1+1
        else:
            IndexL2= IndexL2+1
    return Result
```
### Given unsorted array (n size), find the largest different (arr[j] - arr[i]) where arr[i] < arr[j].
keep track of the lowest value as min, and only store the largest different if it can better value when subtract to the min and current largest different. O(n)
```python
a = [40, 60, 20, 85, 66, 10, 120]
def maxProfit(lst):
    maxvalue = float("-inf")
    minvalue = float("inf")
    for integer in lst:
        if integer < minvalue:
            minvalue = integer
        maxvalue = max(maxvalue, integer-minvalue)
    return maxvalue
```
