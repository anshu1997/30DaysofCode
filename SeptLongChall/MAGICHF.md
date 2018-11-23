```
#include <bits/stdc++.h>
using namespace std;
#define ll long long
void swap(ll &a,ll &b){
	ll temp;
	temp=a;
	a=b;
	b=temp;
}

int main() {
	// your code goes here
	ll t;
	cin>>t;
	while(t--){
		ll n,x,s,pos;
		cin>>n>>x>>s;
		vector <ll> v(n,0);
		v[x-1]=1;
		ll a,b;
		for(ll i=0;i<s;i++){
			cin>>a>>b;
			a=a-1;b=b-1;
			swap(v[a],v[b]);
			/*v[a]=v[a]^1;
			v[b]=v[b]^1;*/
		}
		for(ll i=0;i<n;i++){
			if(v[i]==1){
				pos=i+1;
				break;
			}
		}
		cout<<pos<<endl;	
	}
	
	return 0;
}
```