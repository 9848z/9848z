- 👋 Hi, I’m @9848z
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
9848z/9848z is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
INSERTION SORT
#include <stdio.h>
int main()
{
    int n = 10;
    int a[] = {3,2,6,5,4,7,8,9,5,1};
    int min_index;
    for(int i = 0; i < n - 1; i++) {
        min_index = i;
        for(int j = i + 1; j < n; j++) {
            if(a[min_index] > a[j]) {
                min_index = j;
            }
        }
        if(min_index != i)
        {
            int temp = a[i];
            a[i] = a[min_index];
            a[min_index] = temp;
        }
    }
    printf("Sorted Array: ");
    for(int i = 0; i < n; i++)  {
        printf(" %d", a[i]);
    }
    return 0;
}
MERGESORT
#include <stdio.h>
#include<time.h>
int b[50000];
void Merge(int a[], int low, int mid, int high)
{ 
int i, j, k;
i=low; j=mid+1; k=low;
while ( i<=mid && j<=high )	{ if( a[i] <= a[j] )
b[k++] = a[i++] ;

else

}

b[k++] = a[j++] ;

while (i<=mid)
b[k++] = a[i++] ;
while (j<=high)
b[k++] = a[j++] ;
for(k=low; k<=high; k++) 
a[k] = b[k];

}
voidMergeSort(int a[], int low, int high)
{ int mid;
if(low >= high) return;
mid = (low+high)/2 ; 
MergeSort(a, low, mid);
MergeSort(a, mid+1, high); 
Merge(a, low, mid, high);
}
void main(){
int n, a[50000],k; 
clock_tst,et; doublets;
printf("\n Enter How many Numbers:"); 
scanf("%d", &n);
printf("\nThe Random Numbers are:\n"); 
for(k=1; k<=n; k++)	{
a[k]=rand(); 
printf("%d\t", a[k]);
}
st=clock(); MergeSort(a, 1, n); 
et=clock();
ts=(double)(et-st)/CLOCKS_PER_SEC;
printf("\n Sorted Numbers are : \n ");
for(k=1; k<=n; k++)
printf("%d\t", a[k]);
printf("\nThe time taken is %e",ts);
}



KNAPSACK
void knapsack(int n, float weight[], float profit[], float capacity) {
   float x[20], tp = 0;
   int i, j, u;
   u = capacity;
 
   for (i = 0; i < n; i++)
      x[i] = 0.0;
 
   for (i = 0; i < n; i++) {
      if (weight[i] > u)
         break;
      else {
         x[i] = 1.0;
         tp = tp + profit[i];
         u = u - weight[i];
      }
   }
 
   if (i < n)
      x[i] = u / weight[i];
 
   tp = tp + (x[i] * profit[i]);
 
   printf("\nThe result vector is:- ");
   for (i = 0; i < n; i++)
      printf("%f\t", x[i]);
 
   printf("\nMaximum profit is:- %f", tp);
 
}
 
int main() {
   float weight[20], profit[20], capacity;
   int num, i, j;
   float ratio[20], temp;
 
   printf("\nEnter the no. of objects:- ");
   scanf("%d", &num);
 
   printf("\nEnter the wts and profits of each object:- ");
   for (i = 0; i < num; i++) {
      scanf("%f %f", &weight[i], &profit[i]);
   }
 
   printf("\nEnter the capacityacity of knapsack:- ");
   scanf("%f", &capacity);
 
   for (i = 0; i < num; i++) {
      ratio[i] = profit[i] / weight[i];
   }
 
   for (i = 0; i < num; i++) {
      for (j = i + 1; j < num; j++) {
         if (ratio[i] < ratio[j]) {
            temp = ratio[j];
            ratio[j] = ratio[i];
            ratio[i] = temp;
 
            temp = weight[j];
            weight[j] = weight[i];
            weight[i] = temp;
 
            temp = profit[j];
            profit[j] = profit[i];
            profit[i] = temp;
         }
      }
   }
 
   knapsack(num, weight, profit, capacity);
   return(0);
}

SHORTEST PATH
#include<stdio.h>
#define infinity 999
void dij(int n, int v,int cost[20][20], int dist[]){



int i,u,count,w,flag[20],min; 
for(i=1;i<=n;i++)
flag[i]=0, dist[i]=cost[v][i];
count=2;
while(count<=n){
min=99; 
for(w=1;w<=n;w++)
if(dist[w]<min && !flag[w])
{ min=dist[w];
u=w;
}
flag[u]=1; count++;
for(w=1;w<=n;w++)
if((dist[u]+cost[u][w]<dist[w]) && !flag[w]) 
dist[w]=dist[u]+cost[u][w];
}
}
int main(){
int n,v,i,j,cost[20][20],dist[20];
printf("enter the number of nodes:");
scanf("%d",&n);
printf("\n enter the cost matrix:\n");
for(i=1;i<=n;i++)
for(j=1;j<=n;j++){
scanf("%d",&cost[i][j]); 
if(cost[i][j] == 0)
cost[i][j]=infinity;
}
printf("\n enter the source matrix:"); 
scanf("%d",&v);
dij(n,v,cost,dist);
printf("\n shortest path : \n"); 
for(i=1;i<=n;i++)
if(i!=v)
printf("%d->%d,cost=%d\n",v,i,dist[i]);
}


MINIMUM COST(KRUSKALS)
#include<stdio.h> #include<stdlib.h> inti,j,k,a,b,u,v,n,ne=1;
intmin,mincost=0,cost[9][9],parent[9]; int find(int);
intuni(int,int); void main() {
printf("\n Implementation of Kruskal's algorithm\n\n"); printf("\nEnter the no. of vertices\n");
scanf("%d",&n);
printf("\nEnter the cost adjacency matrix\n"); for(i=1;i<=n;i++){
for(j=1;j<=n;j++) { scanf("%d",&cost[i][j]);


if(cost[i][j]==0)
cost[i][j]=999;
}
}
printf("\nThe edges of Minimum Cost Spanning Tree are\n\n"); while(ne<n){
for(i=1,min=999;i<=n;i++) { for(j=1;j<=n;j++){
if(cost[i][j]<min){
min=cost[i][j]; a=u=i;
b=v=j;
}
}
}
u=find(u); v=find(v); if(uni(u,v)){
printf("\n%d edge (%d,%d) =%d\n",ne++,a,b,min); mincost +=min;
}
cost[a][b]=cost[b][a]=999;
}
printf("\n\tMinimum cost = %d\n",mincost);
}
int find(int i){
while(parent[i])
i=parent[i];
return i;
}
intuni(inti,int j){
if(i!=j) {
parent[j]=i; return 1;
}
return 0;
}
PRIMS ALGORITHM
#include<stdio.h> inta,b,u,v,n,i,j,ne=1;
int visited[10]={0},min,mincost=0,cost[10][10]; void main()
{
printf("\n Enter the number of nodes:"); scanf("%d",&n);
printf("\n Enter the adjacency matrix:\n"); for(i=1;i<=n;i++)
for(j=1;j<=n;j++){
scanf("%d",&cost[i][j]); if(cost[i][j]==0)
cost[i][j]=999;
}
visited[1]=1; printf("\n"); while(ne<n)
{
for(i=1,min=999;i<=n;i++)
for(j=1;j<=n;j++)
if(cost[i][j]<min)
if(visited[i]!=0)
{



}
if(visited[u]==0 || visited[v]==0)
{
min=cost[i][j]; a=u=i;
b=v=j;

printf("\n Edge %d:(%d %d) cost:%d",ne++,a,b,min); mincost+=min; visited[b]=1;
}
cost[a][b]=cost[b][a]=999;
}
printf("\n Minimun cost=%d",mincost);
}
