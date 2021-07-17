**
num = abs(float(input("enter a number: ")))
print(f"num: {num}")
tests = []
i = 0
#exceptions
if num == 1:
    print("sqrt: 1")
#find 2 numbers
for i in range (0, round(num/2)):
    if num - i*i >= 0:
        #print(i)
        i += 1
    else:
        break
#store 2 numbers in list
tests.append(i-1)
tests.append(i)
print("lower bound: " + str(tests[0]))
print("upper bound: " + str(tests[1]))
#print(tests)
#check for perfect square
if tests[0] * tests[0] == num:
    sqrt = tests[0]
elif tests[1] * tests[1] == num:
    sqrt = tests[1]
#if not perfect square (modified)
else:
    while abs(tests[0]*tests[0]-num) > 0.00001:
        #if test = too small: 
        if tests[0] * tests[0] < num:
            tests[0] += (tests[1]-tests[0])/2

        #if test = too big: 
        elif tests[0] * tests[0] > num:
            tests[0] -= (tests[1]-tests[0])/2        
        
sqrt = tests[0]   
print(f"sqrt: {sqrt}")
print(f"srqt squared: " + str(sqrt*sqrt))
**

