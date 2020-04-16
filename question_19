#include<stdio.h>
int main()
{
int n;
printf("Enter no of Customers : ");
scanf("%d",&n);
int cid[n],arr[n],burst[n],tat[n],comp[n],waiting[n];
int i,j;
for(i=0;i<n;i++)
{
printf("Enter Customer ID : ");
scanf("%d",&cid[i]);
}
for(i=0;i<n;i++)
{
printf("Enter Arrival time of Customer %d : ",cid[i]);
scanf("%d",&arr[i]);
}
for(i=0;i<n;i++)
{
printf("Enter No of Gifts to be bought by Customer %d : ",cid[i]);
scanf("%d",&burst[i]);
}
printf("\nTime taken for billing of each gift is 1 second\n\n");
int comp_sum = 0;
int least_arr = arr[0];
static int update_count = 0;
for(i=0;i<n;i++)
{
if(least_arr>arr[i])
least_arr = arr[i];
}
comp_sum = comp_sum+least_arr;
int max_gift = burst[0];
for(i=0;i<n;i++)
{
if(max_gift<=burst[i]&&least_arr == arr[i])
max_gift = burst[i];
}
int dup_burst[n];
for(i=0;i<n;i++)
dup_burst[i]  = burst[i];
while(1)
{
if(update_count == n)
break;
else
{
for(i=0;i<n;i++)
{
if(update_count == n)
break;
else
{
if(least_arr >=arr[i] && max_gift == burst[i])
{
comp_sum = comp_sum + burst[i];
comp[i] = comp_sum;
least_arr = least_arr+burst[i];
dup_burst[i] = 0;
max_gift = 0;
update_count++;
int least_count = 0;
int new_least_arr;
for(j=0;j<n;j++)
{
if(j!=i)
{
new_least_arr = arr[j];
break;
}
}
for(j=0;j<n;j++)
{
if(j!=i)
{
if(new_least_arr>arr[j])
new_least_arr = arr[j];
}
}
if(least_arr<new_least_arr)
least_arr = new_least_arr;
for(j=0;j<n;j++)
{
if(least_arr>arr[j]&& i!=j && dup_burst[j]!=0)
{
if(max_gift<burst[j])
max_gift = burst[j];
}
}
}
}
}
}
}
printf("Customer ID\t Arrival Time\t No of Gifts\t Billing time\n");
for(i=0;i<n;i++)
printf(" %d\t\t %d\t\t %d\t\t %d\n",cid[i],arr[i],burst[i],comp[i]);
printf("\n");
printf("The order of billing the Customers is -\n\n");
int max_comp = comp[0];
for(i=0;i<n;i++)
{
if(max_comp<comp[i])
max_comp = comp[i];
}
int val;
for(i=0;i<=max_comp;i++)
{
if(i==0)
printf("__");
else
{
for(int j=0;j<n;j++)
{
if(comp[j] == i)
{
val = cid[j];
break;
}
else
val = -1;
}
if(val == -1)
printf("__");
else
printf("C%d",val);
}
}
printf("\n");
for(i=0;i<=max_comp;i++)
{
if(i==0)
printf("0  ");
else
{
for(int j=0;j<n;j++)
{
if(comp[j] == i)
{
val = comp[j];
break;
}
else
val = -1;
}
if(val == -1)
printf("  ");
else
printf("%d",val);
}
}
printf("\n");
}
