#include<stdio.h>
#include<math.h>
void main()
{
    int i,j,n,a[10],count,evencount,oddcount,pcount,percount=0,palincount=0,armcount=0,rem,rev,fact,nopcount,num,ch,sum,tem,temp,r;
    printf("enter array size\t");
    scanf("%d",&n);
    printf("enter ele into array\t");
    for(i=0;i<n;i++)
    {
        scanf("%d",&a[i]);
    }
    printf("the array is\n");
    for(i=0;i<n;i++)
    {
        printf("%d\n",a[i]);
    }
    
    
    do
    {
        printf("1.no evens and odd in the array\n2.no of primes in the array\n3.no of perfect numbers in the array\n4.no of armstrong nnumbers in the array\n5.no of palindromes\n6.factorial of each element in the array\nenter an option\t");
        scanf("%d",&ch);
        switch(ch)
        {
            case 1:for(i=0;i<n;i++)
                {
                    if(a[i]%2==0)
                        evencount++;
                    else
                        oddcount++;
                }
                printf("no of evens are %d\n",evencount);
                printf("no of odds are %d\n",oddcount);
                break;
            case 2:for(i=0;i<n;i++)
                {
                    num=a[i];
                    pcount=0;
                    if(num==0||num==1)
                    pcount=1;
                    for(j=2;j<num/2;j++)
                    {
                        if(num%j==0)
                        {
                            pcount++;
                            break;
                        }
                    }
                    if(pcount==0)
                    nopcount++;
                }
                printf("no of primes are %d\n",nopcount);
                break;
            case 3:for(i=0;i<n;i++)
                {
                    num=a[i];
                    sum=0;
                    for(j=1;j<num;j++)
                    {
                        rem=num%j;
                        if(rem==0)
                            sum=sum+j;
                    }
                    if(sum==num)
                    percount++;
                }
                  printf("no of perfect numbers are %d\n",percount);  
                  break;
             case 4:for(i=0;i<n;i++)   
                {
                 sum=0;
                 tem=a[i];
                 temp=a[i];
                 count=0;
                 while(a[i]!=0)
                 {
                     count++;
                     rem=a[i]%10;
                     a[i]=a[i]/10;
                 }
                 while(tem!=0)
                 {
                     r=tem%10;
                     sum=sum+pow(r,count);
                     tem=tem/10;
                 }
                 if(temp=sum)
                    armcount++;
                }
                                printf("no of armstrong numbers are %d\n",armcount);
                break;
            case 5:for(i=0;i<n;i++)
                 {
                     rev=0;
                     num=a[i];
                    while(a[i]!=0)
                    {
                        rem=a[i]%10;
                        rev=(rev*10)+rem;
                        a[i]=a[i]/10;
                    }
                    if(num==rev)
                        palincount++;
                 }
                                 printf("no of palindromes are %d\n",palincount);
                break;
            case 6:for(i=0;i<n;i++)
                {
                    fact=1;
                    for(j=1;j<=a[i];j++)
                    {
                        fact=fact*j;
                    }
                    printf("factorial of %d=%d\n",a[i],fact);
                }
                break;    
         }
    }while((ch>0)&&(ch<7));
}
