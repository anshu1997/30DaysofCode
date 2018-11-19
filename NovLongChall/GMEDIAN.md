Since we have to sort each subsequence to find its median, we will sort our original sequence (i.e. A1,A2,…,AN) at first itself. The ordering won't change.<br>
For example, the good (desired) subsequences in the sequence [9,5,7,6,8,1] are same as that in the sequence [1,5,6,7,8,9].

The subsequences having odd length will definitely qualify to be one of our good subsequence.

<b> Even Length </b>: The subsequences with even length will qualify as good subsequence if and only if the middle two elements are same. Let the repeating elements be found at index i and j Suppose, there are m elements at the left of the index i and n elements at the right of index j.<br>
So, number of good subsequences: 1 (good subsequence of length 2) + mC1∗nC1 (good subsequences of length 4) + mC2∗nC2 (good subsequences of length 6) + ........... + mCmin(m,n)∗nC(min(m,n)) = <b>(m+n)C(min(m,n))</b><br>

```
#include <bits/stdc++.h>
#define ll long long
#define pb push_back
#define DIV 1000000007
using namespace std;

//////////////////////////////////////////////////////////////////////////////////////////////////////////////////

const int N = 2001;
ll factorialNumInverse[N + 1];
// array to precompute inverse of 1! to N!
ll naturalNumInverse[N + 1];
// array to store factorial of first N numbers
ll fact[N + 1];
// Function to precompute inverse of numbers
void InverseofNumber(ll p)
{
    naturalNumInverse[0] = naturalNumInverse[1] = 1;
    for (long long  i = 2; i <= N; i++)
        naturalNumInverse[i] = naturalNumInverse[p % i] * (p - p / i) % p;
}
// Function to precompute inverse of factorials
void InverseofFactorial(ll p)
{
    factorialNumInverse[0] = factorialNumInverse[1] = 1;
    // precompute inverse of natural numbers
    for (long long  i = 2; i <= N; i++)
        factorialNumInverse[i] = (naturalNumInverse[i] * factorialNumInverse[i - 1]) % p;
}
// Function to calculate factorial of 1 to N
void factorial(ll p)
{
    fact[0] = 1;
    // precompute factorials
    for (long long  i = 1; i <= N; i++) {
        fact[i] = (fact[i - 1] * i) % p;
    }
}
// Function to return nCr % p in O(1) time
ll Binomial(ll N, ll R, ll p)
{
    // n C r = n!*inverse(r!)*inverse((n-r)!)
    ll ans = ((fact[N] * factorialNumInverse[R]) % p * factorialNumInverse[N - R]) % p;
    return ans;
}

////////////////////////////////////////////////////////////////////////////////////////////////////////////////

int main() {
	ll t;
	cin>>t;
    InverseofNumber(DIV);
    InverseofFactorial(DIV);
    factorial(DIV);
	while(t--){
		ll n;
		cin>>n;
		vector <ll> v(n,0);
		
		for(ll i=0;i<n;i++){
			cin>>v[i];
		}
		sort(v.begin(),v.end());
		
		ll sum=1;
		for(ll i=0;i<n-1;i++){
			sum=(sum*2)%DIV;
		}
		
		for(ll i=0;i<n-1;i++){
			ll j=i+1;
			while(v[i]==v[j]){
                 ll mini=min(i,n-j-1);
                 ll temp=Binomial(i+n-j-1,mini,DIV);
                 sum=(sum+temp)%DIV;
                 j++;
             }
			
		}
		cout<<sum<<endl;
	}
	return 0;
}
```
Bonus: Calculating queries of the type nCr % 1000000007 can be solved by precalculating nCr upto n = whatever you need. Details of this can be found here: nCr % p in O(1).
