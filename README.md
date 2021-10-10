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
