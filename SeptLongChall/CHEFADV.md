```
#include <bits/stdc++.h>
using namespace std;
#define ll long long
 
int main() {
	// your code goes here
	ll t;
	cin>>t;
	while(t--){
		ll n,m,x,y;
		cin>>n>>m>>x>>y;
		n=n-1;m=m-1;
		if((n==1)&&(m==1))
			cout<<"Chefirnemo"<<endl;
		else if((n==0)&&(m==0))
			cout<<"Chefirnemo"<<endl;
		else{
			ll a=n,b=m;
			// ShareChat
			a=a-1;b=b-1;
			if((a>=0)&&(b>=0)){
				a=a%x;b=b%y;	
			}
			
			n=n%x;m=m%y;
			
			if((a==0)&&(b==0)){
				cout<<"Chefirnemo"<<endl;
			}
			else if((n==0)&&(m==0)){
				cout<<"Chefirnemo"<<endl;
			}
			else{
				cout<<"Pofik"<<endl;	
			}	
		}
 
	}
 
	return 0;
}
```
