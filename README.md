# SurverDevin
//姓名：黄山成 班级：信1301-1 功能：随机产生30道四则运算题，数字为整数或真分数。
#include<iostream>
using namespace std;
#include <time.h>

void proper(int a,int b)//显示真分数的函数
{
if(a>b)
 {
	 cout<<b<<"/"<<a;
 }
 else if(a<b)
 {
	 cout<<a<<"/"<<b;
 }
 else
 {
	 cout<<1;
 }

}
void main()
{
 int figure_1,figure_2,figure_3,figure_4,c;
 char operators;
 
 srand((unsigned)time(NULL));  
 for(int i=0;i<30;i++)
 {
 figure_1=rand()%100+1;
 figure_2=rand()%100+1;
 figure_3=rand()%100+1;
 figure_4=rand()%100+1;

 c=rand()%4;
 switch(c)
 {
 case 0:operators='+';break;
 case 1:operators='-';break;
 case 2:operators='*';break;
 case 3:operators='/';break;
 }
 switch(c){
  
	 case 0:cout<<figure_1<<" "<<operators<<" "<<figure_2<<" ="<<endl;break;
	 case 1:
			    proper(figure_1,figure_2);
				cout<<" "<<operators<<" ";
				proper(figure_3,figure_4);
				cout<<" ="<<endl;
		 break;
	 case 2:
			 cout<<figure_1<<" "<<operators<<" (";
			 proper(figure_3,figure_4);
			 cout<<") ="<<endl;
		 break;
	 case 3 :
			 cout<<"(";
		     proper(figure_3,figure_4);
			 cout<<")";
			 cout<<" "<<operators<<" "<<figure_1<<" ="<<endl;
		break;
        
 }
 }
 
}
