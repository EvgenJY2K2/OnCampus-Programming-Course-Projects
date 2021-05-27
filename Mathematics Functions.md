## Mathematics Functions
###### Task 1: print out the Fibonacci sequence until a given finishing term. 
```
def fiban(n, a):
    '''
    Duties: Counts up to the number n in the Fibonacci sequence.
    Finds correcponding value for a term and 
    analyses sequence convergence.
    
    :param n: finishing term number 
    :type n: int
    
    :param a: searched term number 
    :type a: int
    
    :return: prints out the Fibonacci sequence until the finishing term n.
    Prints out the corresponding sequence number for the searched term. 
    Informs about anaysing convergence based on two consecutive numbers.
    Prints out the convergence value.
    '''        
    #import necessary math functions from sympy module
    from sympy import limit, oo
    
    #define the Fibonacci sequence 
    def f(n):    
       if n == 0:    
           return n    
       elif n == 1 or n == 2:    
           return 1    
       else:    
           return(f(n-1) + f(n-2))   
    
    #print out the Fibonacci sequence until that finishing term
    print("The Fibonacci sequence:")
    for i in range(n+1):
        print('n = ',i, '; x = ',f(i)) 
    print(' ')
    #print the corresponding number for that term
    print("Your term: n =", a, " The corresponding number: x =", f(a))
    print(' ')    
        
    #inform about analysing the consecutive numbers for the searched term
    print("The program analysed the fraction of two consecutive numbers, based on your input: x =",f(a))
    
    #print the convergence value
    print("The sequence converges to:", "{:.2f}".format(limit(f(a)/f(a-1), a, oo)))
```
###### Task 2: use a range and list comprehension to generate a list with 100 equidistantly spaced values between (and including) 0 and 1.
```
def f(a=0, b=100):
    
    '''
    Duties: Uses range and list comprehension to generate 
    a list with 100 equidistantly spaced values 
    between (and including) 0 and 1. 
    
    :param a: range starting value (default = 0)
    :type a: int
    
    :param b: range ending value (default = 100) 
    :type b: int
    
    :return: prints out a list with 100 equidistantly spaced values 
    between (and including) 0 and 1 and lists' length.
    '''
    #Creates a list with values in range [0,1] with iteration step equal to 100/99
    l= [i/99 for i in range(a, b)]
    
    #Prints the list and its length
    print(l, '\n', 'Number of items in the list:', len(l))
f()
```
###### Task 3: compute a fixed point of the function f(x)=x^2-3x+4 by the use of fixed point iteration. 
```
def fp(x=1, n=200, tol=10**(-8)):
    '''
    Duties: computes a fixed point of the function f(x)=x^2-3x+4
    by the use of fixed point iteration: x^(n+1)=x^2n-3x^n+4.
    The program performs 200 steps of this iteration and stops 
    if abs(x^(n+1)-x^n) < tolerance.
    
    :param x: starting variable (default value = 1)
    :type x: int
    
    :param n: iteration variable (default value = 200) 
    :type n: int
    
    :param tol: tolerance value (default value = 10**(-8))
    :type tol: float
    
    :return: prints out iteration variable n 
    and its corresponding function value x.
    Exits if the sequence has converged within the tolerance.
    '''
    
    #import the sys object for stopping code execution when needed
    import sys
    
    #iterate for the declared number of steps n
    for i in range (n):
        x1=x**2-3*x+4
        print ('n=', i, '; x =', x1)
        
        #stop if the absolute value of consecutive numbers is less than tolerance 
        if abs(x-x1) < tol:
            sys.exit('The sequence has converged to within the tolerance.')
        
        #else take on the last value and continue 
        else:
            x=x1
    return x1
fp()
```
###### Task 4: compute the numbers in the sequence up to the given term, check the convergence rate and any negative numbers in the sequence.
```
def conv(c, n=5, e = 10**-15):
    '''
    Duties: computes the numbers in the sequence 
    up to the given term (recursion value).
    Checks the convergence rate and 
    if there are any negative numbers in the sequence.
    
    :param c: constant of the function in range (-0.5; 0.25)
    :type c: float
    
    :param n: number of terms (recursion value) (default = 5)
    :type n: int
    
    :param e: the acceptable convergence value (default = 10**-15)
    :type e: float

    :return: prints out iteration variable n 
    and its corresponding function value x.
    Prints out if the sequence converges or diverges.
    Prints out if there are any negative numbers in the sequence.
    Raises error if the term input is not positive.
    '''  
    #define the sequence 
    def f(n):
        if n <= 1:  
           return n  
        else:
            return (0.2*f(n-1)-c*(f(n-1)**2-5))
    
    #if number of terms equals 0 raise an error
    if n<=0:
        print("Please enter a positive integer. ")
    
	#else print the iteration variable n and its corresponding value x
    else:
        print("Your sequence: ")
        for i in range (1, n+1):
            print('n =', i, '; x =', f(i))
        print(' ')
    
	#check if sequence converges      
    if abs(f(i+1)-f(i)) < e:
        print("The sequence converges. ")
    
	#else sequence diverges 
    else:
        print("The sequence diverges. ")
        
    
	#check for negative numbers in the sequence      
    if f(i) < 0:
        print("There are negative numbers in the sequence. ")
    else:
        print("There are no negative numbers in the sequence. ")
```
###### Task 5: plot the graph of the a**x function with additional features.
```
def pl(a = 2, c = 'blue'):
    '''
    Duties: plots the graph of the a**x function.
    
    :param a: argument of the function (base number) (default = 2)
    :type a: float
    
    :param c: colour of the graph (default = 'blue')
    :type c: string

    :return: plots the a**x function with labeled axis and caption.
    
    '''
    #import necessary libraries
    import matplotlib.pyplot as plt
    import numpy as np
    
    #create vectors 
    x = np.linspace(-2, 4, int(a))
    y = a**x

    #plot the function
    plt.plot(x,y,label='y = a**x', color=c)
    
    #give caption
    plt.title('The graph of {}**x function'.format(a))
    
    #label axis
    plt.xlabel('x axis')
    plt.ylabel('y axis')
    
    #show the plot
    plt.show()
pl()
```
