# Sum-square-difference
Problem Statement
You are given several test cases. For each test case, you are required to find the absolute difference between two values:

The sum of the squares of the first 
𝑁
N natural numbers.
The square of the sum of the first 
𝑁
N natural numbers.
Problem Definition
For a given integer 
𝑁
N, the two values are:

Sum of the squares of the first 
𝑁
N natural numbers:

Sum of squares
=
1
2
+
2
2
+
3
2
+
⋯
+
𝑁
2
Sum of squares=1 
2
 +2 
2
 +3 
2
 +⋯+N 
2
 
Square of the sum of the first 
𝑁
N natural numbers:

Square of the sum
=
(
1
+
2
+
3
+
⋯
+
𝑁
)
2
Square of the sum=(1+2+3+⋯+N) 
2
 
You need to find the absolute difference between these two values:

Absolute Difference
=
∣
Sum of squares
−
Square of the sum
∣
Absolute Difference=∣Sum of squares−Square of the sum∣
Input Format
The first line contains an integer 
𝑇
T, denoting the number of test cases.
The next 
𝑇
T lines each contain an integer 
𝑁
N, the number of natural numbers.
Output Format
For each test case, print the absolute difference between the sum of squares and the square of the sum.

Constraints
1
≤
𝑇
≤
1000
1≤T≤1000
1
≤
𝑁
≤
1
0
5
1≤N≤10 
5
 
Example
Input:
Copy code
2
3
10
Output:
yaml
Copy code
22
2640
Explanation:
For 
𝑁
=
3
N=3:

The sum of the squares of the first 3 natural numbers is:
1
2
+
2
2
+
3
2
=
1
+
4
+
9
=
14
1 
2
 +2 
2
 +3 
2
 =1+4+9=14
The square of the sum of the first 3 natural numbers is:
(
1
+
2
+
3
)
2
=
6
2
=
36
(1+2+3) 
2
 =6 
2
 =36
The absolute difference is:
∣
14
−
36
∣
=
22
∣14−36∣=22
For 
𝑁
=
10
N=10:

The sum of the squares of the first 10 natural numbers is:
1
2
+
2
2
+
⋯
+
1
0
2
=
1
+
4
+
9
+
16
+
25
+
36
+
49
+
64
+
81
+
100
=
385
1 
2
 +2 
2
 +⋯+10 
2
 =1+4+9+16+25+36+49+64+81+100=385
The square of the sum of the first 10 natural numbers is:
(
1
+
2
+
⋯
+
10
)
2
=
5
5
2
=
3025
(1+2+⋯+10) 
2
 =55 
2
 =3025
The absolute difference is:
∣
385
−
3025
∣
=
2640
∣385−3025∣=2640
Approach
Formulae:
Sum of squares of the first 
𝑁
N natural numbers:

Sum of squares
=
𝑁
(
𝑁
+
1
)
(
2
𝑁
+
1
)
6
Sum of squares= 
6
N(N+1)(2N+1)
​
 
Sum of the first 
𝑁
N natural numbers:

Sum
=
𝑁
(
𝑁
+
1
)
2
Sum= 
2
N(N+1)
​
 
Then, square the result to get the square of the sum:

Square of the sum
=
(
𝑁
(
𝑁
+
1
)
2
)
2
Square of the sum=( 
2
N(N+1)
​
 ) 
2
 
Steps:
Calculate the sum of squares using the first formula.
Calculate the square of the sum using the second formula.
Compute the absolute difference between the sum of the squares and the square of the sum.
Repeat for each test case.
Code Implementation:
python
Copy code
def sum_of_squares(n):
    # Return sum of squares of the first n natural numbers
    return n * (n + 1) * (2 * n + 1) // 6

def square_of_sum(n):
    # Return the square of the sum of the first n natural numbers
    sum_n = n * (n + 1) // 2
    return sum_n * sum_n

def main():
    t = int(input())  # Read the number of test cases
    for _ in range(t):
        n = int(input())  # Read each test case value N
        sum_squares = sum_of_squares(n)
        square_sum = square_of_sum(n)
        # Output the absolute difference
        print(abs(sum_squares - square_sum))

if __name__ == "__main__":
    main()
Explanation of the Code:
sum_of_squares(n):

This function uses the formula for the sum of squares of the first 
𝑁
N natural numbers:
Sum of squares
=
𝑁
(
𝑁
+
1
)
(
2
𝑁
+
1
)
6
Sum of squares= 
6
N(N+1)(2N+1)
​
 
square_of_sum(n):

This function first calculates the sum of the first 
𝑁
N natural numbers using:
Sum
=
𝑁
(
𝑁
+
1
)
2
Sum= 
2
N(N+1)
​
 
Then, it squares the result to compute the square of the sum.
main():

Reads the input for multiple test cases.
For each test case, it computes the required sum of squares, square of the sum, and their absolute difference.
Prints the result for each test case.
Time Complexity:
Each calculation (sum of squares, square of sum) takes constant time 
𝑂
(
1
)
O(1) due to the use of formulas.
Therefore, for 
𝑇
T test cases, the time complexity is 
𝑂
(
𝑇
)
O(T).
Space Complexity:
The space complexity is 
𝑂
(
1
)
O(1), as the space required for calculations does not depend on the size of 
𝑁
N.
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
for _ in range(int(input())):
    n = int(input())

   

    sq_sum = n ** 2 * (n + 1) ** 2 // 4
    sum_sq = n * (n + 1) * (2 * n + 1) // 6

    print(sq_sum - sum_sq)


    
