```
#include <bits/stdc++.h>
#define ll long long
#define pb push_back
#define DIV 1000000007
using namespace std;

ll fun(string x){
	if(x=="monday")
	 return 0;
	 if(x=="tuesday")
	 return 1;
	 if(x=="wednesday")
	 return 2;
	 if(x=="thursday")
	 return 3;
	 if(x=="friday")
	 return 4;
	 if(x=="saturday")
	 return 5;
	 if(x=="sunday")
	 return 6;
}
int main() 
{ 
	ll t;
	cin>>t;
	while(t--){
		string a,b;
		ll l,r;
		cin>>a>>b;
		cin>>l>>r;
		ll f,s;
		f=fun(a);
		s=fun(b);
		ll start=(f+l-1)%7;
		ll end=(f+r-1)%7;
		ll flag=0,pos=0;
		ll tot=r-l+1;
		if(tot>7)
			flag=1;
			
		//cout<<start<<" "<<end<<endl;
		ll i=start;
		ll count=0;
		while(tot){
			ll j=i%7;
			if(s==j){
				pos=j;
				count++;
				flag=1;
			}
			i++;
			tot--;
		}
		
		//cout<<pos<<endl;
		if(flag==1){
			if(count>1)
			cout<<"many"<<endl;
			else{
				ll x=pos-start;
				if(x<0)
				x=7+x;
				ll out=l+x;
				cout<<out<<endl;
			}
		}
		else
		cout<<"impossible"<<endl;
		
	}
    return 0; 
} 
```