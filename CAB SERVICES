#include<stdio.h>
#include<conio.h>
#include<string.h>
#include<math.h>
#include<stdlib.h>
 int distance(char *a,char *b);
 void taxiprint(int);
     int booking_id=1;
     int taxi1,taxi2,taxi3,taxi4;
     int taxi1_book,taxi2_book,taxi3_book,taxi4_book;
  int taxi_earning[4];
    struct taxi
    {
        int customer_id;
        char pickup_point[3];
        char drop_point[3];
        int pickup_time;
    }t[100];

    struct booking
    {
    // static int taxi_earning[4];
        int booking_id;
        int customer_id;
        char from[3];
        char to[3];
        int pickuptime;
        int droptime;
        int amount;
    }b[4][100];

void booking(struct booking *b,struct taxi t,int no)
{
b->customer_id=t.customer_id;
b->booking_id=booking_id++;
strcpy(b->from,t.pickup_point);
strcpy(b->to,t.drop_point);
b->pickuptime=t.pickup_time;
b->droptime =distance(t.pickup_point,t.drop_point)+t.pickup_time;
if(b->droptime>12)
{
 b->droptime-=12;
}
b->amount=100+((distance(t.pickup_point,t.drop_point)*15)-5)*10;
taxi_earning[no]+=b->amount;
}

int distance(char *a,char *b)
{
 char start=a[0];
 char stop=b[0];
 return (abs(start-stop));
}
void decrement()
{
 if(taxi1>0)
 taxi1--;
 if(taxi2>0)
 taxi2--;
 if(taxi3>0)
 taxi3--;
 if(taxi4>0)
 taxi4--;
}
void taxiprint(int taxino)
{
 printf("\n Taxi can be Allocated\n");
 printf("\n taxi- %d is allocated\n\n",taxino);
}
void display()
{
// printf("%d %d %d %d",taxi1_book,taxi2_book,taxi3_book,taxi4_book);
 if(taxi1_book>0)
 {
  printf("\nTaxi 1 \n total Earning= %d\n",taxi_earning[0]);
     printf("\n Booking_Id   Customer_Id   From  to  pickup_time  Drop_time  Amount\n");
  for(int i=0;i<taxi1_book;i++)
  {
   printf("%d     %d      %s      %s      %d     %d     %d\n",b[0][i].booking_id,b[0][i].customer_id,b[0][i].from,b[0][i].to,b[0][i].pickuptime,b[0][i].droptime,b[0][i].amount);
  }
 }
 if(taxi2_book>0)
 {
  printf("\nTaxi 2 \n total Earning= %d\n",taxi_earning[1]);
     printf("\n Booking_Id   Customer_Id   From  to  pickup_time  Drop_time  Amount\n");
  for(int i=0;i<taxi2_book;i++)
  {
   printf("%d     %d      %s      %s      %d     %d     %d\n",b[1][i].booking_id,b[1][i].customer_id,b[1][i].from,b[1][i].to,b[1][i].pickuptime,b[1][i].droptime,b[1][i].amount);
  }
 }if(taxi3_book>0)
 {
  printf("\nTaxi 3 \n total Earning= %d\n",taxi_earning[2]);
     printf("\n Booking_Id   Customer_Id   From  to  pickup_time  Drop_time  Amount\n");
  for(int i=0;i<taxi3_book;i++)
  {
   printf("%d     %d      %s      %s      %d     %d     %d\n",b[2][i].booking_id,b[2][i].customer_id,b[2][i].from,b[2][i].to,b[2][i].pickuptime,b[2][i].droptime,b[2][i].amount);
  }
 }if(taxi4_book>0)
 {
  printf("\nTaxi 1 \n total Earning= %d\n",taxi_earning[3]);
     printf("\n Booking_Id   Customer_Id   From  to  pickup_time  Drop_time  Amount\n");
  for(int i=0;i<taxi4_book;i++)
  {
   printf("%d     %d      %s      %s      %d     %d     %d\n",b[3][i].booking_id,b[3][i].customer_id,b[3][i].from,b[3][i].to,b[3][i].pickuptime,b[3][i].droptime,b[3][i].amount);
  }
 }
}
int main()
{

    while(1)
    {
        int user_choice,count,i;
        
        printf("\n...................Taxi_Booking..............................................\n");
        printf("\n 1.Booking  2.Details 3.exit \n");
        printf("Enter Choice:");
  scanf("%d",&user_choice);
        if(user_choice==1)
        {
            printf("\nnumber of Booking :");
            scanf("%d",&count);
            for(i=0;i<count;i++)
            {
                printf("\nInput %d:\n",i+1);
                printf("\nCustomer Id :");
                scanf("%d",&t[i].customer_id);
                printf("\npickup point :");
                scanf("%s",t[i].pickup_point);
                printf("\ndrop point :");
                scanf("%s",t[i].drop_point);
                printf("\npickup time :");
                scanf("%d",&t[i].pickup_time);
                if(taxi1==0)
                {
                booking(&b[0][taxi1_book++],t[i],0);
                taxi1=distance(t[i].pickup_point,t[i].drop_point);
                taxiprint(1);
                }
                else if(taxi2==0)
                {
                booking(&b[1][taxi2_book++],t[i],1);
                taxi2=distance(t[i].pickup_point,t[i].drop_point);
                taxiprint(2);
                }
                else if(taxi3==0)
                {
                 booking(&b[2][taxi3_book++],t[i],2);
                taxi3=distance(t[i].pickup_point,t[i].drop_point);
                taxiprint(3);
                }
                else if(taxi4==0)
                {
                 booking(&b[3][taxi4_book++],t[i],3);
                taxi4=distance(t[i].pickup_point,t[i].drop_point);
                taxiprint(4);
                }
                else
                {
                 printf("ALL Taxi Are Busy.. Please Try after Some time");
                }
                decrement();
            }
        }
        else if(user_choice==2)
        {
display();
        }
        else
        {
            return 0;
        }
    }
    
}
