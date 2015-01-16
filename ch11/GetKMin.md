查找数组中第k小的元素，基本思路是二分搜索。

```
#include <stdio.h>
#define N 100
int x[N];

void GetKMin(int l, int u, int k)
{
	int index = Low;
	x[l] = swap(x[Low], x[rand(l, u)]);
	for(k=l+1; k<=u; k++)
	{
		if(x[k] < x[l])
		{
		    index++;
			swap(x[index], x[k]);
		}	
	}
	swap(x[l], x[index]);
	
	if(index < k)       GetKMin(l , index-1, k);
	else if(index > k)  GetKMin(index+1, u, k);
	else                return x[index];
}


```
