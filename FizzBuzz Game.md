## FizzBuzz Game
###### Task: Write a function to play the Game of FizzBuzz according to the following rules: for multiples of one number print "Fizz"; for multiples of the other number print "Buzz". For numbers which are multiples of both print "FizzBuzz".
```
def fizzbuzz(a, b, div1=3, div2=5):
    ''' 
    Rules: For multiples of first variable (div1) 
    prints "Fizz" instead of the number.  
    For the multiples of second variable (div2) 
    prints "Buzz".  
    For numbers which are multiples of both div1 and div2 prints "FizzBuzz".
    Runs in the given range (a,b).

    :param a: starting point  
    :type a: int 

    :param b: ending point  
    :type b: int 
    
    :param div1: first division variable (default value = 3)
    :type b: int 
    
    :param div2: second division variable (default value = 5)  
    :type b: int 

    :return: printing out the numbers in range (a, b) according to the game rules. 
    ''' 
    #Declare the range of numbers 
    for i in range(a, b+1): 

       #Condition for multiples of both div1 and div2 (checks if division remainder is 0)  
        if i%div1==0 and i%div2==0: 
            print('FizzBuzz')   

       #Condition only for multiples of div1  
        elif i%div1==0:   
            print('Fizz')  

       #Condition only for multiples of div2    
        elif i%div2==0:   
            print('Buzz')   

       #If none of the conditions are satisfied, print the number  
        else:   
            print(i)
```

