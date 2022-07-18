#include<bits/stdc++.h>
const int base = 31;
const int q = 29;
void rabinkarp(string &pattern,string &text,vector<int> &ans)
   {
       int j;
       int h=1;
       int p=0; //hashvalue of string pattern
       int t=0; //hashvalue of string text
       int n=text.size();
       int m=pattern.size();
       
       // The value of h would be "pow(base, m-1)%q" 
       for(int i=0;i<m-1;i++)
           h=(h*base)%q;
       
        // Calculate hash value for pattern and text (first set of hashvalue of size m )
       for(int i=0;i<m;i++)
       {
           p=(base*p + pattern[i])%q;
           t=(base*t + text[i])%q;
       }
              
        // Slide the pattern over text one by one 
       for(int i=0;i<=n-m;i++)
       {
           if(p==t)
           {           
               for(j=0;j<m;j++)
               {
                   if(text[i+j]!=pattern[j])
                       break;
               }
               if(j==m)
                 ans.push_back(i);
           }
           
           if(i<n-m)
           {
               t=t-h*text[i];
               t=(base*t+text[i+m])%q;
               if(t<0)
                   t=t+q;
                   
           }
       }
   }
vector<int> stringMatch(string &str, string &pat) {
   // Write your code here
      
       vector<int> ans;       
       rabinkarp(pat,str,ans);
       return ans;
}
