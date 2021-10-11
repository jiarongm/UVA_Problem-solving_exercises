# UVA_Problem-solving_exercises
## 判斷11的倍數
```c
#include <stdio.h>
int main()
{
	int n1,n2,count=0;
	while(scanf("%d %d",&n1,&n2)!=EOF){
		if(n1==0 && n2==0)break;
		int r1,r2,c=0;
		for(int i=0;;){
			if((n1+n2)<9)break;//避免0+9+可能的進位
			r1=n1%10;
			r2=n2%10;
			c+=r1+r2;
			if(c>=10){
				count++;
				c=1;
			}
			else c=0;
			n1/=10;
			n2/=10;
		}
		if(count>1)printf("%d carry operations.\n",count);
		if(count==0)printf("No carry operation.\n",count);
		if(count==1)printf("1 carry operation.\n");
		count=0;
		
	}
	
}
```

### UVA100 The 3n+1 problem
#### 輸入[a,b]兩數,A B之間由較小數開始,若是N是偶數則N=N/2,奇數N=3*N+1;至1為止停 計算此數列的長度length;
#### A B之間由較小數開始,尋找有最大length的N

```c

#include <stdio.h>
#include <stdlib.h>
int fun(int n);
int main()
{
	int x,y,max=0,star,end;
	while(scanf("%d %d",&x,&y)!=EOF){
		max=0;
		if(x<y){
			star=x;
			end=y;
		}else{
			star=y;
			end=x;
		}
		while(star<=end){
			int t_count=fun(star++);
			if(t_count>max)max=t_count;
		}
		printf("%d %d %d\n",x,y,max);
	}
}
int fun(int n){
	int count=1;
	while(n!=1){
		if(n%2==0)n/=2;
		else n=3*n+1;
		count++;
	}
	return count;
}
```
