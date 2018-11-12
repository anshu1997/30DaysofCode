#include <bits/stdc++.h>
#define ll long long
#define pb push_back
using namespace std;

int main() {
	ll t;
	cin>>t;
	while(t--){
		ll n;
		cin>>n;
		vector <ll> a(n,0),b(n,0),temp;
		vector <vector <ll> > v(n+1,temp);
		for(ll i=0;i<n;i++){
			cin>>a[i];
		}
		for(ll i=0;i<n;i++){
			b[i]=a[a[i]-1];
			v[b[i]].pb(i+1);
		}
		
		/*for(ll i=1;i<=n;i++){
			cout<<i<<" : ";
			for(ll j=0;j<v[i].size();j++){
				cout<<v[i][j]<<" ";
			}
			cout<<endl;
		}*/
		ll flag=0;
		for(ll i=1;i<=n;i++){
			set <ll> s;
			for(ll j=0;j<v[i].size();j++){
				s.insert(a[v[i][j]-1]);
			}
			if(s.size()>1){
				flag=1;
				break;
			}
		}
		if(flag){
			cout<<"Truly Happy"<<endl;
		}
		else{
			cout<<"Poor Chef"<<endl;
		}
	}
	return 0;
}