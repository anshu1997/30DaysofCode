```
#include <bits/stdc++.h>
using namespace std;
typedef long long ll;
int main()
{
	int T; ll n,k;
	cin>>T;
	while(T--)
	{
		cin>>n>>k;
		if(n<=2)
		{
			printf("%.10lf\n",1.0/n);
			continue;
		}
		if(k&&n>=3)
		{
			if(n%4==2)
				n=n/2+1;
			else 
				n-=n/2; 
			--k;
		}
		
		while(n>=3&&k){
			n-=n/2;
			--k;
		}
			
		if(n==2&&k) 
			n=1;
		
		printf("%.10lf\n",1.0/n);
	}
}

```
