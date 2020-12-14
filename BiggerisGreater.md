```
# Complete the biggerIsGreater function below.
def biggerIsGreater(w):
    s = list(w)
    # find non-increasing suffix
    i = len(s)-1
    while i>0 and s[i] < s[i-1]:
        i=i-1
    if i<=0:
        return "no answer"

    # find replacement to pivot
    j = len(s)-1
    while j>0 and s[j] < s[i-1]:
        j=j-1
    if s[j] == s[i-1]:
        return "no answer"
    else:
        s[j], s[i-1] = s[i-1], s[j]

    # reverse the suffix
    s[i:]=s[len(s)-1 : i-1 : -1]

    return ''.join(s)
```

Reference: [Link](https://www.nayuki.io/page/next-lexicographical-permutation-algorithm)
