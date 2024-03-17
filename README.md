# 30.0.0-SearchandSort

```
import random
import string

def sortedList(length):    # Generate a sorted list of specified length
    sorted_list = sorted(random.sample(range(1000), length))
    return sorted_list

def randomInt(length, minVal, maxVal):
    return [random.randint(minVal, maxVal) for _ in range(length)]


def randomChar(length):
    return [random.choice(string.ascii_lowercase) for _ in range(length)]


def  leanearSearch(items, target):
     for i in range(len(items)):
         if L[i] == target:
             return i
     return -1


def binarySearch(items, target): ## https://youtu.be/pRKPgAiY6-g?si=FhW-oWogqfz5xifR
    ## ivdeo is done in java, but  will work well to translate to Python
    low = 0
    high = len(items) - 1

    while low <= high:
        mid = (low + high) // 2
        if items[mid] == target:
            return mid
        elif target < items[mid]:
            high = mid - 1
        else:
            low = mid + 1
    return -1


def bubbleSort(items): #https://youtu.be/KLvH6yi5YYU?si=3K7pUt1jNHFIJQSV 
     for i in range(len(items)):
          already_sorted = True
          for j in range(len(items)-i-1):
               if items[j] > items[j+1]:
                    items[j], items[j+1] = items[j+1], items[j]
                    already_sorted= False
                    if already_sorted:
                         break
     return(items)                             


def selectionSort(items): #https://youtu.be/ee80YmiaSVQ?si=8oNM2GnoesfF4N-R
    for i in range(0,len(items)-1):
        curMin = i
        for j in range(i+1, len(items)):
            if items[j] < items[curMin]:
                curMin = j
        items[i],  items[curMin] = items[curMin], items[i]
    return(items)

                    
def insertionSort(items): #https://youtu.be/R_wDA-PmGE4?si=oyaegHPtKec7BX9y
    for i in range(1,len(items)):
        j = i
        while items[j-1]> items[j] and j>0:
            items[j-1],  items[j] = items[j], items[j-1]
            j -=1
    return(items)


##a = generate_random_list(1000, 0, 1000)
a = generate_random_letters(22)  
print(insertionSort(a))

```
