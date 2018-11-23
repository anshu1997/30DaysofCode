```
#include <bits/stdc++.h>
#define ll long long
using namespace std;

/*struct table{
	ll l,r,data;
};*/
ll isperf(ll x){
	if((x==0)||(x==1))
		return 1;
	long double y;
	y=sqrt(x);
	x=(int)y;
	if(y==x)
		return 1;
	return 0;
}
int main(){
ll t;
cin>>t;
while(t--){
	ll n,q;
	cin>>n>>q;
	vector <ll> v(n,0),l(q,0),r(q,0);
	for(ll i=0;i<n;i++){
		cin>>v[i];
	}
	ll a,b;
	for(ll i=0;i<q;i++){
		cin>>a>>b;
		l[i]=a-1;
		r[i]=b-1;
	}
	
	for(ll i=0;i<q;i++){
		ll count=0;
		for(ll j=l[i];j<=r[i];j++){
			ll sq=v[j];
			for(ll k=j;k<=r[i];k++){
				sq=sq&v[k];
				if(isperf(sq)){
					count++;
				}
			}
		}
		cout<<count<<endl;
	}
  }
}
```
