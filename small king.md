# SurverDevin
//Fing the three kings of shui,the amount of every king is at least 1/3 of sum. 20133048 黄山成 2016/5/27 
#include<iostream>
using namespace std;

void Find_King(int shui_ID[],int amount_ID)//寻找水王
{
	int king_1=0,king_2=0,king_3=0;//三个水王变量
	int Counts_1=0,Counts_2=0,Counts_3=0;//没一个计数器用来计数三个水王的出现次数
	int i=0;
	for(i=0;i<amount_ID;i++)
	{

        if(Counts_1==0 && shui_ID[i]!=king_2 && shui_ID[i]!=king_3)//第一个水王的默认ID
        {
            Counts_1=1;
            king_1=shui_ID[i];//第一个水王出现一次
        }
		else if(Counts_2==0 &&shui_ID[i]!=king_1 && shui_ID[i]!=king_3)//第二个水王的默认ID
        {
            Counts_2=1;
            king_2=shui_ID[i];
        }
        else if(Counts_3==0 &&shui_ID[i]!=king_1 && shui_ID[i]!=king_2)//第三个水王的默认ID
        {
            Counts_3=1;
            king_3=shui_ID[i];
        }
        else if(shui_ID[i]!=king_1 && shui_ID[i]!=king_2 && shui_ID[i]!=king_3)//如果下面三个ID都不是上面三个标记的水王id，那么意味着水王没有出现，出现次数减一
        {
            Counts_1--;
            Counts_2--;
            Counts_3--;
        }
        else if(shui_ID[i]==king_1)//第一个水王又出现一次，出现次数加一
        {
            Counts_1++;
        }
        else if(shui_ID[i]==king_2)
        {
            Counts_2++;
        }
        else if(shui_ID[i]==king_3)
        {
            Counts_3++;
        }       
	}
	cout<<king_1<<" "<<king_2<<" "<<king_3<<endl;

}

int main()
{
	int ID[10]={123,243,323,123,323,243,323,243,123,4123};
    //string ID[10] = {"波风水门","MVP","波风水门","波风水门","666666一水到底","MVP","要火火","MVP","666666一水到底","666666一水到底"};  
    cout<<"ID: "<<endl;
    for(int i=0;i<10;i++)
    {
        cout<<ID[i]<<" ";
    }
	cout<<endl;

    cout<<"The small kings of shui are:"<<" "<<endl;
    Find_King(ID,10);  
    
	return 0;
}


