# Largest-product-in-a-series
Problem Statement
You are given a large number consisting of 
𝑁
N digits, and you need to find the greatest product of 
𝐾
K consecutive digits in that number for each test case.

Input Format
The first line contains 
𝑇
T, the number of test cases.
For each test case:
The first line contains two integers 
𝑁
N (the number of digits) and 
𝐾
K (the number of consecutive digits to multiply).
The second line contains an 
𝑁
N-digit integer.
Constraints
1
≤
𝑇
≤
100
1≤T≤100
1
≤
𝑁
≤
1000
1≤N≤1000
1
≤
𝐾
≤
13
1≤K≤13
Output Format
For each test case, print the greatest product of 
𝐾
K consecutive digits.
SOLUTION:
#include <cmath>
#include <cstdio>
#include <vector>
#include <iostream>
#include <algorithm>
using namespace std;


int main() 
{
    int t;
    cin >> t;
    
    while(t--)
    {
        int n, k;
        cin >> n >> k;
        
        string num;
        cin >> num;
        
        int largest = 0;
        
        for(int i=0; i<=n-k; i++)
        {
            int prod = 1;
            
            for(int j=0; j<k; j++)
            {
                if(num[i+j] == '0')
                {
                    prod = 0;        
                    break;
                }
                prod *= num[i+j] - '0';
            }
            if(prod > largest) 
            {
                largest = prod;
            }
        }     
        cout << largest << endl;
    }
    return 0;
}
