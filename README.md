
# Merge Sort
```
#include <cstdio>
#include <iostream>
#include <algorithm>
#include <cstring>
#define N 500000
#define M 1000000
using namespace std;
int unsort[N],in,arr[N];
void mergesort(int st,int l)
{
    int a=l/2;
    if(a>1)mergesort(st,a);
    if(l-a>1)mergesort(st+a,l-a);
    int i=st,j=st+a,k=0;
    while(i<=st+a-1&&j<=st+l-1)
    {
        if(unsort[i]<unsort[j]){arr[k]=unsort[i];i++;}
        else {arr[k]=unsort[j];j++;}
        k++;
    }
    while(i<=st+a-1){arr[k]=unsort[i];i++,k++;}
    while(j<=st+l-1){arr[k]=unsort[j];j++,k++;}
    for(i=0;i<l;i++)unsort[st+i]=arr[i];
}
int main()
{
    int n;cin>>n;
    for(int i=1;i<=n;i++)
        {scanf("%d",&in);unsort[++unsort[0]]=in;}
    mergesort(1,unsort[0]);
    for(int i=1;i<=unsort[0];i++)
        cout<<unsort[i]<<' ';
    printf("\n");
    return 0;
}
```
***edit on 2017/11/28***
![just look here](https://ss0.bdstatic.com/94oJfD_bAAcT8t7mm9GUKT-xh_/timg?image&quality=100&size=b4000_4000&sec=1511861212&di=81b66eb8df7d4dfafdfa1aaeb8fa533f&src=http://imglf1.nosdn.127.net/img/bFlkOUMvVWk2SWN3WksvanMvckVXTVc1V1A3Yy9UWGxtQzA4VjZwZnJkYkd5QnI1U3F2UW1RPT0.jpg?imageView&thumbnail=500x0&quality=96&stripmeta=0&type=jpg)
