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
