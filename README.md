Heap-Sort-Implemented-In-C
==========================

Heap Sort Implementation In C
#include<bits/stdc++.h>
#include<iostream>
using namespace std;
void change(int a,int b)
{
    int temp=a;
    a=b;
    b=temp;
}

void siftdown(int a[],int start,int end )
{
    int root=start;
    while(2*root+1<=end)
    {   printf("loop starts");
        int child=2*root+1;
        int swap=root;
        if(a[child]>a[swap])
           {

            swap=child;
         //   printf("left child is greater than root\n");
           }
        if(a[child+1]>a[swap]&&child+1<=end)
            {swap=child+1;
           // printf("right child is greater than left chiild\n")
            }
        if(swap!=root)
            {int t=a[root];
            a[root]=a[swap];
            a[swap]=t;
            root=swap;
            }
           else return;
    }

}

void heapify(int a[],int count)
{
    int start=(count-2)/2;
    while(start>=0)
    {
        siftdown(a,start,count-1);
        start=start-1;
    }

}
void heapsort(int a[],int count)
{
    heapify(a,count);
    int end=count-1;
    while(end>0)
    {

cout<<endl;
        swap(a[0],a[end]);
        end=end-1;
        siftdown(a,0,end);

    }

}

int main()
{
    int n;
    printf("Enter the no. of numbers");
    cin>>n;
    int a[n];
    printf("Enter %d numbers",n);
    for(int i=0;i<n;i++)
{
    cin>>a[i];
}

heapsort(a,n);
for(int i=0;i<n;i++)
{
    cout<<a[i]<<" ";
}


}
