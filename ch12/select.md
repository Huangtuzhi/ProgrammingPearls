以下是从n中随机取m个样本的伪代码

```
select = m
remaining = n
for i = [0 ,n]
    if (bigrand() %remaining) < select
    print i
    select--
remaining--
``` 
 
 更简单的C++实现如下
 
```
 void genknuth(int m, int n)
 {
     for(int i=0; i<n; i++)
     {
     //select m of the remaining n-i
      if((bigrand() %(n-i)) < m){
          cout<< i << "\n";
          m--;
      }
     }

 }
 ```
