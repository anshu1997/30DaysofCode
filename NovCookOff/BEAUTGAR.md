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
		s=s+s[0]; 
		ll count=0;
		vector <ll> pos;
		for(ll i=0;i<len;i++){
			if(s[i]==s[i+1]){
				count++;
				pos.pb((i+1)%len);
			}
		}
		if(count==0){
			cout<<"yes"<<endl;
		}
		else if((count>2)||(count==1)){
			cout<<"no"<<endl;
		}
		else{
			if(count==2){
				sort(pos.begin(),pos.end());
				//cout<<"pos: ";
				//cout<<pos[0]<<pos[1]<<endl;
				reverse(s.begin()+pos[0], s.begin()+pos[1]);
				s.pop_back();
				/*for(ll i=0;i<len;i++){
					cout<<s[i];
				}
				cout<<endl;*/
				s=s+s[0];
				ll flag=1;
				for(ll i=0;i<len;i++){
					if(s[i]==s[i+1]){
						flag=0;
						break;
					}
					if(flag==0)
						break;
				}
				if(flag)
				cout<<"yes"<<endl;
				else
				cout<<"no"<<endl;
			}		
		}	
	}
	return 0;
}

```
