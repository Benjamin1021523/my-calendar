my-calendar
===========

When I want to change the condition of standard year, some troubles will appear...








#include<stdio.h>
#include<iostream>

using namespace std;

int main()
{
    int i,m,n,q;
    int year, month, first_space, feb_days;
   
    cout << "請輸入西元";
    cin >> year;
      
    cout << "請輸入月份" ;
    cin >> month;
   
   
    if(month<=12 && month>=1){
      for(first_space=3,q=0;q<(year-1800);q++){
        if(q%4==0 && q%100!=0 || q%400==100)
          first_space=(first_space+366)%7;
        else
          first_space=(first_space+365)%7;
                }
           
    
      //計算2月天數
      if(year%4==0 && year%100!=0 || year%400==0)
       feb_days =29;
      else
       feb_days =28;
   
    
    int space[13]={0,first_space,0,0,0,0,0,0,0,0,0,0,0};  
    int days[13]={0,31,feb_days,31,30,31,30,31,31,30,31,30,31};
   


    for(i=1;i<month;i++)
    space[i+1]=(space[i]+days[i])%7;
   
   
     cout << "        " << year << "年" << month << "月\n";
     cout << "   日 一 二 三 四 五 六 \n   ";
        for(m=1;m<=space[i];m++)
             cout << "  ";
             
        for(n=1;n<=days[i];n++){
             if(n<=9)
               cout<< "  " << n;
             else  
               cout << " " << n;
         
             if(n%7==(7-space[i])%7)
               cout << "\n  ";
                      }
          
     cout << "\n";
     }
     return 0;
    
} 
