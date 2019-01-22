

```python
#Find the maximum in a list
def maxi(list):
    N=list[0]
    for num in list:
        if N < num:
            N=num
    return N
maxi([0,2,5,3,4,8])
```




    8




```python
#Remove duplication from a string
#First way
def rmovedup(str):
    dup=str[0]
    for c in str:
        if c not in dup:
            dup +=c
    return dup
rmovedup("ghhhuuyyjjjjg")
    
```




    'ghuyj'




```python
#Remove duplication from a string
#second way
##Change a string into a ls\ist of character

def stringtolist(str):
    st=[]
    for c in str:
        st.append(c)
    return st
liststring=stringtolist("abrakatabram")

def rmovedup(list):
    asc=[0]*256
    str=[]
    for c in list:
        if asc[ord(c)]==0:
            asc[ord(c)]=1
            str.append(c)
    return ''.join(str)
rmovedup(liststring)

```




    'abrktm'




```python
#Find pair of number that sum to n
#Simple method O(n^2)

def pairsimple(list, n):
    count=0
    for i in range(len(list)):
        for j in range(len(list)):
            if i<j and list[i]+list[j]==n:
                count+=1
                print (list[i], list[j])
    return count
pairsimple([1,2,5,6,3,4,8,9,10],10)
            
                
                
```

    1 9
    2 8
    6 4
    




    3




```python
#Find pair of number that sum to n
#medium method nlogn
def pairmedium(list,n):
    list.sort()
    count=0
    l=0
    r=len(list)-1
    while l<r:
        if list[l]+list[r]==n:
            count+=1
            print(list[l],list[r])
            l+=1
            r-=1
        elif list[l]+list[r]<n:
            l+=1
        else:
            r-=1
    return count

pairmedium([1,2,5,6,3,4,8,9,10,20],10)   
        
```

    1 9
    2 8
    4 6
    




    3




```python
#Find pair of number that sum to n
#higher method n
def pairhigher(list, n):
    list=set(list)
    count=0
    for num in list:
        if n-num in list and 2*num<n :
            count+=1
            print(num, abs(n-num))
            
    return count
pairhigher([1,2,5,6,3,4,8,9,-10,20],10)
```

    1 9
    2 8
    4 6
    -10 20
    




    4




```python
#Reverse an integer
def reverseit(n):
    reverse=0
    while n>0:
        remain=n%10
        n=n//10
        reverse=reverse*10+remain
    return reverse
reverseit(1235)
```




    5321




```python
#Count number of numbers
def cnumb(n):
    count=0
    while n>0:
        n//=10
        count+=1
    return count
cnumb(1234)
```




    4




```python
#Reverse a list
def reverselist(list):
    start=0
    end=len(list)-1
    while start<end:
        list[start],list[end]=list[end],list[start]
        start+=1
        end-=1
    return list
reverselist(["a", "b", "c"])
    
```




    ['c', 'b', 'a']




```python
#Find duplicate
def finddup(list):
    dup=[]
    for num in list:
        if list[abs(num)]>=0 :
            list[abs(num)]=-list[abs(num)]
        else:
            dup.append(abs(num))
    return dup
finddup([2,4,5,1,4,3,2])
            
```




    [4, 2]



