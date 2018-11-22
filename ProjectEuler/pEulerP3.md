```
#include <bits/stdc++.h>
#define ll long long
#define pb push_back
#define DIV 1000000007
using namespace std;
   
long long maxPrimeFactors(long long n) 
{ 
    long long maxPrime = -1; 
    //removing 2
    while (n % 2 == 0) { 
        maxPrime = 2; 
        n >>= 1;
    } 
  	// go on removing
    for (int i = 3; i <= sqrt(n); i += 2) { 
        while (n % i == 0) { 
            maxPrime = i; 
            n = n / i; 
        } 
    } 
    //IMPORTANT
    // This condition is to handle the case when n is a prime number greater than 2 
    if (n > 2) 
        maxPrime = n; 
  
    return maxPrime; 
} 
  
int main() 
{ 
    ll n = 600851475143; 
    printf("%lld", maxPrimeFactors(n)); 
  
    return 0; 
} 
```