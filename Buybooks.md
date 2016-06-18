# SurverDevin
//书店针对《哈利波特》系列书籍进行促销活动，一共5卷，用编号0、1、2、3、4表示，单独一卷售价8元， 具体折扣如下所示：
//                                 本数                      折扣
//                                   2                        5%
//                                   3                       10%
//                                   4                       20%
//                                   5                       25%
//信1301-1 黄山成 20133048
#include<iostream>
using namespace std;

void book_Strategy(int n)
{

	int option;
	option=n%10;//总共有10种购书方法
	double volume=n/5;//购买书的卷数
	int other_Books=n%5;//剩余的书的个数
	double money;
	
	
	switch(option)
	{
	case 0:money=40*volume*0.75;
		break;
	case 1:money=40*volume*0.75+8;
		break;
	case 2:money=40*volume*0.75+8*2*0.95;
		break;
	case 3:money=40*volume*0.75+8*3*0.9;
		break;
	case 4:money=40*volume*0.75+8*4*0.8;
		break;
	case 5:money=40*volume*0.75;
		break;
	case 6:money=40*volume*0.75+8;
		break;
	case 7:money=40*volume*0.75+8*2*0.95;
		break;
	case 8:money=40*(volume-1)*0.75+8*4*0.8*2;
		break;
	case 9:money=40*volume*0.75+8*4*0.8;	
		break;
	}
	if(option!=8)
	{
		cout<<"购书方案： "<<volume<<"套全书"<<"和"<<other_Books<<"卷书"<<endl;
	}
	else
	{
		cout<<"购书方案： "<<volume-1<<"套全书"<<"和两套4卷书"<<endl;
	}
	cout<<"价格为："<<money<<"元";

}
void main()
{
	double m;
	cout<<"输入购书数量：";
	cin>>m;
	while(m<0||(m!=(int)m))
	{
		cout<<"购书数量错误，请重新输入";
		cin>>m;
	}
	
	 cout<<"购买"<<m<<"本书的";
	 book_Strategy(m);
	


}
