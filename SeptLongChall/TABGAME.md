```
#include <bits/stdc++.h>
#define ll long long
#define pb push_back
using namespace std;

int main(){
ll t;
scanf ("%d",&t);
while(t--){
	ll q;
	string m,n,res;
	res="";
	cin>>m; 
	cin>>n; 
	ll mm=m.size()+1;
	ll nn=n.size()+1;
	//ll dp[101][101][2];
	vector< vector<int> > va(mm, vector<int>(nn, -1));
	vector< vector<int> > vb(mm, vector<int>(nn, -1));
	
	scanf ("%d",&q);
	vector <ll>x(q,0);
	vector <ll>y(q,0);
	for(ll i=0;i<q;i++){
		scanf ("%d",&x[i]);
		scanf ("%d",&y[i]);
	}
	//fill dp[1][0] dp[2][0] dp[3][0] with m
	for(ll i=0;i!=m.size();i++){
		if(m[i]=='0'){
			va[i+1][0]=1;
			vb[i+1][0]=1;
		}
		else if(m[i]=='1'){
			va[i+1][0]=0;
			vb[i+1][0]=0;
		}			
	}
	//fill dp[0][1] dp[0][2] with m
	for(ll i=0;i!=n.size();i++){
		if(n[i]=='0'){
			va[0][i+1]=1;
			vb[0][i+1]=1;
		}		
		else if(n[i]=='1'){
			va[0][i+1]=0;
			vb[0][i+1]=0;
		}			
	}
	
	va[1][1]=va[0][1]||va[1][0];
	vb[1][1]=vb[0][1]||vb[1][0];
	//Now construct dp[2][1],dp[3][1],dp[4][1]
	//cout<<endl<<"first COL: ";
	for(ll i=1;i!=m.size();i++){
		va[i+1][1]=(va[i+1][0])||(!vb[i][1]);
		vb[i+1][1]=(vb[i+1][0])||(!va[i][1]);
	//	cout<<dp[i+1][1][0]<<" ";			
	}
	//cout<<endl<<"first ROW: ";
	//Now construct dp[1][2],dp[1][3],dp[1][4]
	for(ll i=1;i!=n.size();i++){
		va[1][i+1]=(va[0][i+1])||(!vb[1][i]);
		vb[1][i+1]=(vb[0][i+1])||(!va[1][i]);
		//cout<<dp[1][i+1][0]<<" ";			
	}
	
	//PRINT for debug
	
	for(ll k=0;k<q;k++){
		//got x[k] and y[k]
		for(ll i=2;i<=y[k];i++){
			for(ll j=2;j<=x[k];j++){
				if(va[i][j]==-1){
					va[i][j]=(!vb[i][j-1])||(!vb[i-1][j]);
					vb[i][j]=(!va[i][j-1])||(!va[i-1][j]);
				}	
			}	
		}
		
		res+=va[y[k]][x[k]]+48;
	}
	cout<<res<<endl;
  }
}
```
