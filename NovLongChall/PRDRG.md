```
#include <bits/stdc++.h>
#define ll long long
#define pb push_back
using namespace std;

int main() {
	ll t;
	cin>>t;
	while(t--){
		ll n;
		vector <ll> v;
		cin>>n;
		if(n%2){
			if(n==1) v.pb(2);
			else{
				for(ll i=1;i<=n;i++){
					if(i==n){
						v.pb(pow(2,n));
					}
					else if((i%2)==0)
						v.pb(pow(2,i));
				}
			}
		}
		else{
			if(n==2) v.pb(4);
			else{
				for(ll i=1;i<=n;i++){
					if((i%2)==0)
						v.pb(pow(2,i));
				}
			}		
		}
		ll num=1,den=v[v.size()-1];
		if(v.size()>1){
			num=0;
			for(ll i=0;i<v.size();i++){
				num+=v[v.size()-1]/v[i];
			}
		}
		cout<<num<<" "<<den<<" ";
	}
	return 0;
}
```
