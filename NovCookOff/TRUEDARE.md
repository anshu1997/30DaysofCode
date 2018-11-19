```
#include <bits/stdc++.h>
#define ll long long
#define pb push_back
#define DIV 1000000007
using namespace std;

int main() {
	ll t;
	cin>>t;
	while(t--){
		ll tr,dr,ts,ds,x;
		cin>>tr;
		vector <ll> rt(101,0);
		for(ll i=0;i<tr;i++)
			{
				cin>>x;
				rt[x]++;
			}
		cin>>dr;
		vector <ll> rd(101,0);
		for(ll i=0;i<dr;i++){
				cin>>x;
				rd[x]++;
			}		
		cin>>ts;
		vector <ll> st(101,0);
		for(ll i=0;i<ts;i++){
				cin>>x;
				st[x]++;
			}
		cin>>ds;
		vector <ll> sd(101,0);
		for(ll i=0;i<ds;i++){
				cin>>x;
				sd[x]++;
			}
		ll flag=1;
		for(ll i=0;i<101;i++){
			if(st[i]){
				if(!rt[i]){
					flag=0;
					break;
				}
			}
			
			if(sd[i]){
				if(!rd[i]){
					flag=0;break;
				}
			}
			if(flag==0)
				break;
		}
		if(flag)
		cout<<"yes"<<endl;
		else
		cout<<"no"<<endl;
	}
	return 0;
}

```
