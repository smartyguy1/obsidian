```C
#include <stdio.h>

int add(int x, int y) \\Function declaration

int main(){
	int a,b,c;
	scanf("%d %d",&a, &b);
	c= add(a,b); \\Parameters in function call are called actual parameters
	printf("%d", c);
}

int add(int x, int y){
	int z; \\local variable
	z = x+y;
	return z;
}
```
