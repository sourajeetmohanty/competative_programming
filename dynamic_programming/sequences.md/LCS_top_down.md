```cpp
#include <iostream>
#include<bits/stdc++.h>

using namespace std;
void lcs(string s1,string s2,int n,int m)
{
    int dp[n+1][m+1];
  for(int i=0;i<=m;i++)
  {
      dp[0][i]=0;
  }
  for(int i=0;i<=n;i++)
  {
      dp[i][0]=0;
  }
   
   for(int i=1;i<=n;i++)
   {
           for(int j=1;j<=m;j++)
       {
            if(s1[i-1]==s2[j-1])
            {
              dp[i][j]=1+dp[i-1][j-1];
                
            }
            else
            {
                dp[i][j]=max(dp[i-1][j],dp[i][j-1]);
            }
       }
   }
    cout<<"LCS ="<<dp[n][m];
}

int main()
{
    string s1,s2;
    cin>>s1>>s2;
    int n,m;
    n=s1.length();
    m=s2.length();
    lcs(s1,s2,n,m);
    return 0;
}
```
