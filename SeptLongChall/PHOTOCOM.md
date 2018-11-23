```
#include <bits/stdc++.h>
#define ll long long
using namespace std;

int main(){
ll t;
cin>>t;
while(t--){
	ll h1,w1,h2,w2;
	string s1,s2;
	cin>>h1>>w1;
	cin>>s1;
	cin>>h2>>w2;
	cin>>s2;
	ll a=(h1*h2)/(__gcd(h1,h2));ll a1=a/h1;ll a2=a/h2;
	ll b=(w1*w2)/(__gcd(w1,w2));ll b1=b/w1;ll b2=b/w2;
	string ss1,ss2;
	ss1.clear();ss2.clear();
	//first do it b1 number of times and for the while row repeat it a1 number of times
	for(ll i=0;i<s1.size();i=i+w1){
		string tss;
		tss.clear();
		for(ll j=0;j<w1;j++){
			for(ll x=0;x<b1;x++){
				tss+=(s1[j+i]);
			}	
		}
		
		for(ll y=0;y<a1;y++){
				ss1.append(tss);
		}
	}
	for(ll i=0;i<s2.size();i=i+w2){
		string tss="";
		for(ll j=0;j<w2;j++){
			for(ll x=0;x<b2;x++){
				tss+=(s2[j+i]);
			}	
		}
		for(ll y=0;y<a2;y++){
				ss2.append(tss);
		}
	}
	//cout<<endl<<ss1<<endl<<ss2<<endl;
	ll count=0;
	for(ll i=0;i<a*b;i++){
		if(ss1[i]==ss2[i])
			count++;
	}
	cout<<count<<endl;
  }
}
```
