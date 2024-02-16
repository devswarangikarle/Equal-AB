# Equal-AB
Given two numbers a and b. In one operation you can pick any non negative integer x and either of a or b. Now if you picked a then replace a with a&amp;x else if you picked b then replace b with b&amp;x.  Return the minimum number of operation required to make a and b equal.  Note: Here &amp; represents bitwise AND operation. 


def min_operations(a, b):
    operations = 0
    while a != b:
        x = 1
        while (a & x) == (b & x):
            x <<= 1
        if a & x:
            a &= x - 1
        else:
            b &= x - 1
        operations += 1
    return operations


a = int(input())
b = int(input())


result = min_operations(a, b)
print(result)
