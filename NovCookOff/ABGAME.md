## NIM Game

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
		string s;
		cin>>s;
		ll len=s.size();
		vector< pair <ll,ll> > AA; 
		vector< pair <ll,ll> > BB; 
		vector <ll> prefixnum(len,0);
		ll count=0;
		for(ll i=0;i<len;i++){
			if((s[i]=='A')||(s[i]=='B')){
				count++;
				prefixnum[i]+=count;
			}
			else{
				if(i==0)
					prefixnum[0]=0;
				prefixnum[i]=prefixnum[i-1];
			}
		}
		for(ll i=0;i<len;i++){
			ll pos;
			if(s[i]=='A'){
				ll dir,move;
				pos=i;
				if((i%2)==0){
					while((s[i]=='A')||(s[i]=='.')){
						if(s[i]=='A')
							pos=i;
						i++;
					}
					if(prefixnum[pos]%2)
						dir=1;
					else
						dir=0;
					move=i-pos;
					i=pos;	
				}
				else{
					ll j=i;
					while((s[j]=='A')||(s[j]=='.')){
						if(s[j]=='A')
							pos=j;
						j--;
					}
					if(prefixnum[pos]%2)
						dir=1;
					else
						dir=0;
					move=pos-j;
				}
				AA.pb(make_pair(dir,move));
			}
		}
		///////////////////////////////////
		for(ll i=0;i<len;i++){
			ll pos;
			if(s[i]=='B'){
				ll dir,move;
				pos=i;
				if((i%2)==0){
					while((s[i]=='B')||(s[i]=='.')){
						if(s[i]=='B')
							pos=i;
						i++;
					}
					if(prefixnum[pos]%2)
						dir=1;
					else
						dir=0;
					move=i-pos;
					i=pos;	
				}
				else{
					ll j=i;
					while((s[j]=='B')||(s[j]=='.')){
						if(s[j]=='B')
							pos=j;
						j--;
					}
					if(prefixnum[pos]%2)
						dir=1;
					else
						dir=0;
					move=pos-j;
				}
				BB.pb(make_pair(dir,move));
			}
		}
		ll a=AA.size();
		ll b=BB.size();
		ll i=0;
		ll flag=1;
		while(a||b){
			if((i%2)==0){
				b--;
				a--;
			}
			else{
				flag=0;
				a--;
				b--;
			}
			i++;
		}
		if(flag)
		cout<<'A'<<endl;
		else
		cout<<'B'<<endl;
	}
	return 0;
}
```
