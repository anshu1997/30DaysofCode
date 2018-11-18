Since we have to sort each subsequence to find its median, we will sort our original sequence (i.e. A1,A2,…,AN) at first itself. The ordering won't change. 
For example, the good (desired) subsequences in the sequence [9,5,7,6,8,1] are same as that in the sequence [1,5,6,7,8,9].

The subsequences having odd length will definitely qualify to be one of our good subsequence.

### Even Length
The subsequences with even length will qualify as good subsequence if and only if the middle two elements are same. 
Let the repeating elements be found at index i and j Suppose, there are m elements at the left of the index i and n elements at the right of index j.
So, number of good subsequences: 1 (good subsequence of length 2) + mC1∗nC1 (good subsequences of length 4) + mC2∗nC2 (good subsequences of length 6) + ........... + mCmin(m,n)∗nC(min(m,n))
## (m+n)C(min(m,n))

```
#include <bits/stdc++.h>
#define ll long long
#define pb push_back
#define DIV 1000000007
using namespace std;
ll factorial(ll n)
{
	ll i;
	if((n==0)||(n==1))
		return 1;
	for(i = n-1; i > 0; i--)
		n=(n*i)%DIV;
	return n;
}
ll ncr(ll n,ll r){
	ll result = ((factorial(n)%DIV)/(((factorial(r)%DIV)*(factorial(n-r)%DIV))%DIV))%DIV;
	return result;
}

int main() {
	ll t;
	cin>>t;
	while(t--){
		ll n;
		cin>>n;
		vector <ll> v(n,0),temp;
		vector <vector<ll> > hash(2001,temp);
		for(ll i=0;i<n;i++){
			cin>>v[i];
			hash[v[i]].pb(i);
		}
		
		/*DISPLAY hash
		for(ll i=0;i<2001;i++){
			if(hash[i].size()){
				cout<<i<<":  ";
			  for(ll j=0;j<hash[i].size();j++){
			  	cout<<hash[i][j]<<" ";
			  }
			  cout<<endl;
		    }
		}*/
		ll sum=1;
		for(ll i=0;i<n-1;i++){
			sum=(sum*2)%DIV;
		}
		
		for(ll i=0;i<2001;i++){
			if(hash[i].size()>1){
				//cout<<i<<endl;
				for(ll j=0;j<hash[i].size();j++){
					ll lessno=hash[i][j];
					for(ll k=j+1;k<hash[i].size();k++){
						sum=(sum+1)%DIV;
						ll moreno=n-hash[i][k]-1;
						ll mini=min(lessno,moreno);
						for(ll h=1;h<=mini;h++){
							sum=(sum+(ncr(lessno,h)*ncr(moreno,h))%DIV)%DIV;
						}
					}
				}
			}
		}
		cout<<sum<<endl;
	}
	return 0;
}
```
Bonus: Calculating queries of the type nCr % 1000000007 can be solved by precalculating nCr upto n = whatever you need :p . Details of this can be found here: nCr % p in O(1)
