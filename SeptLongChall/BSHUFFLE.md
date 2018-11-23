```
#include <bits/stdc++.h>
using namespace std;
 
#define fo(i,n) for(i=0;i<n;i++)
#define Fo(i,k,n) for(i=k;i<n;i++)
#define ll long long
 
#define pb push_back
#define mp make_pair
#define F first
#define S second
#define all(v) v.begin(),v.end() 

#define fastIO ios_base::sync_with_stdio(false);cin.tie(0);cout.tie(0)
 
#define debug(x) cout<<#x<<" :: "<<x<<"\n";
#define debug2(x,y) cout<<#x<<" :: "<<x<<"\t"<<#y<<" :: "<<y<<"\n";
#define debug3(x,y,z) cout<<#x<<" :: "<<x<<"\t"<<#y<<" :: "<<y<<"\t"<<#z<<" :: "<<z<<"\n";
 
using namespace std;

/**************************************************************************/
int main()
{
	fastIO;
	ll t,i,j,k,n;
	cin>>n;
    t = 1;
    while(t--)
    {
    

    if(n==3)
    {
        cout<<"2 3 1"<<endl;
        cout<<"1 2 3"<<endl;
    }

    if(n==4)
    {
        cout<<"2 1 4 3"<<endl;
        cout<<"4 1 2 3"<<endl;
    }

    if(n==5)
    {
        cout<<"2 3 1 5 4"<<endl; 
        cout<<"5 1 2 3 4"<<endl;
    }

    if(n==6)
    {
        cout<<"2 3 1 5 6 4"<<endl;
        cout<<"6 1 2 3 4 5"<<endl;
    }

    if(n==7)
    {
        cout<<"2 3 4 1 6 7 5"<<endl;
cout<<"7 1 2 3 4 5 6"<<endl;
    }
    if(n==8)
    {
        cout<<"2 3 4 1 6 7 8 5\n"; 
cout<<"8 1 2 3 4 5 6 7\n";
    }
    if(n==9)
    {
        cout<<"2 3 4 5 1 7 8 9 6\n"; //- 2 3 4 1 6 7 8 9 5
cout<<"9 1 2 3 4 5 6 7 8\n";
    }
    if(n==10)
    {
        
        cout<<"2 3 4 5 1 7 8 9 10 6\n";
cout<<"10 1 2 3 4 5 6 7 8 9\n";
    }
    if(n==11)
    {
        
cout<<"2 3 4 5 6 1 8 9 10 11 7\n";
cout<<"11 1 2 3 4 5 6 7 8 9 10\n";
    }
    if(n==12)
    {
        
        cout<<"2 3 4 5 6 1 8 9 10 11 12 7\n";
cout<<"12 1 2 3 4 5 6 7 8 9 10 11\n";
    }
    if(n==13)
    {
        cout<<"2 3 4 5 6 7 1 9 10 11 12 13 8\n";
cout<<"13 1 2 3 4 5 6 7 8 9 10 11 12\n";
    }
    if(n==14)
    {
        
        cout<<"2 3 4 5 6 7 1 9 10 11 12 13 14 8\n";
cout<<"14 1 2 3 4 5 6 7 8 9 10 11 12 13\n";
    }
    if(n==15)
    {
        
        cout<<"2 3 4 5 6 7 8 1 10 11 12 13 14 15 9\n";
cout<<"15 1 2 3 4 5 6 7 8 9 10 11 12 13 14\n";
    }
    if(n==16)
    {
        
        cout<<"2 3 4 5 6 7 8 1 10 11 12 13 14 15 16 9\n";
cout<<"16 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15\n";
    }
    if(n==17)
    {
        cout<<"2 3 4 5 6 7 8 9 1 11 12 13 14 15 16 17 10\n";
cout<<"17 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16\n";
    }
    
    cout<<'\n';
    }
}
```
