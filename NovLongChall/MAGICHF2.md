We can use the balance <b> k </b> times. If we have the same weight on both sides, it stays balanced, otherwise, it may tilt to any side.<br>
• Whenever we use balance, We divide the coins into 3 piles. One each lying on balance both sides, and the third pile which is not put on balance.<br>
• Optimal strategy is to divide coins into piles, so that the maximum of Number of coins on both sides combined, and Number of coins not on balance, is Minimized.<br>
• We can make cases on basis of Nmod4. <br>If Nmod4==0, divide into piles of side N/4, N/4 and N/2. <br> If Nmod4==1, divide into piles of size N/4, N/4 and N/2+1 and <br>if Nmod4==3, divide into piles of size N/4+1, N/4+1 and N/2. Here, the division is <b>floor</b> division.<br>
• Nmod4==2 is a special case. If there are any other fake coins, we can divide into piles of size N/4, N/4+1 and N/2+1 and use <b>one fake coin with the first pile</b>. This way, the problem gets reduced to N/2 coins for the next step. Otherwise, we have to make piles of size N/4+1, N/4+1 and the remaining in the third pile.<br>
• This way, we can use the balance optimally and in the end, after using balance K times, we would be left with a set of, say X coins. Now, the probability of picking the gold coin is 1/X, Since there is one gold coin and rest are fake.

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
