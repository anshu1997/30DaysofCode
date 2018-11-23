```
// CPP program to check if k-th bit
// of a given number is set or not using
// right shift operator.
#include <bits/stdc++.h>
#define ll long long
using namespace std;

 
// Driver code
int main()
{
    ll t;
    cin>>t;
    while(t--){
    	ll n;
	    cin>>n;
	    vector <ll> v(n,0),temp(1000001,0);
	    ll numberone=0,numberzero=0;
	    for(ll i=0;i<n;i++){
	    	cin>>v[i];
	    	temp[v[i]]++;
	    	if(v[i]%2)
	    		++numberone;
	    	else
	    		++numberzero;
	    }
	    // Handling the case when XOR is 2
	    sort(v.begin(),v.end());
	    ll minus=0;
	    for(ll i=0;i<n;i++){
	    	ll h=v[i]^2;
		if(h>v[i]){
			if(temp[h]){
		   			
				minus+=temp[h];
			}
		}	
	    }
	    // Handling when a no. is present multiple times
	    ll minsum=0;
	    for(ll i=1;i<1000001;i++){
	    	if(temp[i]>1){
	    		minsum+=temp[i]*(temp[i]-1)/2;	
	    	}
	    }
	    ll sum=0;
	    sum=(numberone*(numberone-1)/2)+(numberzero*(numberzero-1)/2) - minus-minsum;
	    cout<<sum<<endl;
    }
    
    return 0;
}
```