import sys
def minimumDif(arr,n,m):
    result=sys.maxsize
    arr.sort()
    for i in range(0,n-m):
        result=min(result,arr[i+m-1]-arr[i])
    return result

def findElement(arr,n,m,res):
    result=sys.maxsize
    for i in range(0,n-m):
        result= min(result,arr[i+m-1]-arr[i])
        if(res==result):
            return i
    return 0



arr=[7980,22349,999,2799,229900,11101,9999,2195,9800,4999]
items=["Fitbit Plus: 7980", "IPods: 22349"," MI Band: 999 ","Cult Pass: 2799"," Macbook Pro: 229900"," Digital Camera: 11101"," Alexa: 9999"," Sandwich Toaster: 2195"," Microwave Oven: 9800"," Scale: 4999"]
n=len(arr)
print("Number of the employees")
m=int(input())
res=minimumDif(arr,n,m)
startIndex=findElement(arr,n,m,res)
print(" Here the goodies that are selected for distribution are :")
for i in range(startIndex,startIndex+m):
    print(items[i])
print()
print(" And the diffrence between the chosen goodies with the highest price and lowest price is :",res)
