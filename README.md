#include <iostream>

using namespace std;

int main()
{
    int year,length=0,i,month,weekday,day,blank,today=1,change;
    cout<<"Please input which year you want to print:"<<endl;
    cin>>year;
    for(i=1970; i<year; i++)
    {
        if((i%4==0&&i%100!=0)||i%400==0)
            length+=366;
        else length+=365;
    }
    weekday=(length+4)%7;

    for (month=1; month<=12; month++)

    {

        change=0;
        if(month==1||month==3||month==5||month==7||month==8||month==10||month==12)
            day=31;
        else if(month==2)
            if((i%4==0&&i%100!=0)||i%400==0)
                day=29;
            else day=28;
        else day=30;


        cout<<"星期天\t\t"<<"星期一\t\t"<<"星期二\t\t"<<"星期三\t\t"<<"星期四\t\t"<<"星期五\t\t"<<"星期六\t\t"<<endl;
        for(blank=0; blank<=weekday-1; blank++)
        {
            cout<<"\t\t";
            change++;
        }
        for(today=1; today<=day; today++)
        {

            if(month>=10&&today>=10)
            {
                cout<<month<<"月"<<today<<"日"<<"\t";
                change++;
            }
            else

            {

                cout<<month<<"月"<<today<<"日"<<"\t"<<"\t";
                change++;
            }
            if (change%7==0)
                cout<<endl;
        }

        cout<<endl;
        weekday=change%7;
    }




}


