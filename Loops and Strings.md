## Loops and Strings
###### Task 1: check if year is a leap year.
```
year = input('Please enter year: ')  
 try:  
     year = int(year)  
    if year <  0:  
         print('Please enter a positive number.') 
        quit() 
 except:  
     print('Invalid input. Please try again.')  
if year % 4 ==0:  
    if year % 100 ==0:  
         if year % 400 ==0:  
             print(str(year) + " is a leap year")  
         else:  
             print(str(year) + " is not a leap year")  
     else:  
         print(str(year) + " is a leap year")  
 else:  
    print(str(year) + " is not a leap year")
```
###### Task 2: count how many string objects there are in the list.
```
lst = list()
count = 0
while True:
    num = input("Input your object or type 'done' to break: ")
    if num == "done":
        break
    try:
        num = int(num)
        lst.append(num)
    except: 
        lst.append(num)
for num in lst:
    if type(num) is str:
        count = count + 1
    else: continue
print("Your list: ", lst)
print("There are {0} strings in the list.".format(count))
```

