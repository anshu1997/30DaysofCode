```
#include <bits/stdc++.h>
#define ll long long
#define pb push_back
#define DIV 1000000007
using namespace std;

///////////////////////////////////////////////////////////////////////////////////////////////////////////////////

vector <ll> fib(ll n) 
{ 
  /* Declare an array to store Fibonacci numbers. */
  vector <ll> f(n+2,0);   // 1 extra to handle case, n = 0 
  ll i; 
  
  /* 0th and 1st number of the series are 0 and 1*/
  f[0] = 0; 
  f[1] = 1; 
  
  for (i = 2; i <= n; i++) 
  { 
      /* Add the previous 2 numbers in the series 
         and store it */
      f[i] = f[i-1] + f[i-2]; 
  } 
  
  return f; 
} 
  
int main () 
{ 
  ll n=33; //term 33 is the last term which does not exceed 4Mill, find through formula of fibonacci
  vector <ll> ff=fib(n);
  ll sum=0;
  for(ll i=0;i<=33;i++){
  	if(ff[i]%2==0)
  	sum+=ff[i];
  }
  cout<<sum;
  return 0; 
}
```