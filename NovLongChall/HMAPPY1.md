```
#include <bits/stdc++.h>
#define ll long long
#define pb push_back
using namespace std;

int main() {
	ll n,q,k;
	cin>>n>>q>>k;
	string s;
	vector <ll> v;
	set <ll> ss;
	for(ll i=0;i<n;i++){
		ll y;
		cin>>y;
		v.pb(y);
		ss.insert(y);
	}
	//concat
	v.insert(v.end(),v.begin(), v.end());
	cin>>s;
	/*DISPLAY
	for(ll i=0;i<v.size();i++){
		cout<<v[i]<<" ";
	}*/
	
	//Check if only 1s or 0s
	if(ss.size()==1){
		ll ans=0;
		if(v[0])
			ans=n;
		for(ll i=0,j=n;i<s.size();i++){
			if(s[i]=='?'){
				cout<<min(ans,k)<<endl;
			}
		}
	}
	else{
	vector <ll> start(v.size(),0);
	vector <ll> temp;
	vector < vector<ll> > count(n+1,temp);
	//store consecutiveness in respective indices
	for(ll i=0;i<v.size();i++){
		if(v[i]){
			ll j=i+1;
			while((v[j])&&(j<v.size())&&(j<(i+n))){
				j++;
			}
			//keep upper limit of consecutive 1s as n
			ll no=j-i;
			while(i<j){
				start[i]=no;
				no--;
				i++;
			}
			i=i-1;
		}
	}
	//MAKE count array
	for(ll i=0;i<start.size();i++){
		if(start[i])
			count[start[i]].pb(i);
	}
	/*DISPLAY
	cout<<endl<<"DISPLAY start: "<<endl;
	for(ll i=0;i<start.size();i++){
		cout<<"For "<<i<<" index: "<<start[i];
		cout<<"\n";
	}*/
	//FINDING CURRENT STATE MAX
	ll maxi=-1,endpos,endposstart,maxstart;
	for(ll i=n;i<start.size();i++){
		if(start[i]>maxi){
					maxi=start[i];
					endpos=i+start[i]-1;
		}
	}
	//cout<<"MAX: "<<maxi<<" Endpos: "<<endpos<<endl;
	endposstart=endpos;
	maxstart=maxi;
    //Getting contiguous array
	for(ll i=0,j=n;i<s.size();i++){
		if(s[i]=='?'){
			cout<<min(maxi,k)<<endl;
		}
		else if(s[i]=='!'){
			if(j==1){
				j=n;
				endpos=endposstart;
				maxi=maxstart;
			}	
			else{
				j--;
				ll x=j+n-1;
				if(endpos==(x+1)){//Checking if max consecutive is at the edge
					maxi=maxi-1;
					endpos=x;
					ll stpos=x-maxi+1;
					for(ll g=0;g<count[maxi].size();g++){
						if((count[maxi][g]>=j)&&(count[maxi][g]<stpos)){
							endpos=count[maxi][g]+maxi-1;
							break;
						}	
					}
					//cout<<"enters this: ";
					if(start[j]>=maxi){
							maxi=start[j];
							endpos=j+start[j]-1;
					}	
				}
				else{
					if(start[j]>=maxi){
							maxi=start[j];
							endpos=j+start[j]-1;
					}			
				}
			}				
		}
	}
  }
	return 0;
}
```
