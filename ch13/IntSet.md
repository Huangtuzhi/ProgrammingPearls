此程序用于生成[0,maxval]范围内的m个随机整数的有序序列。

```
class IntSetImp{
  IntSetImp(int maxelements, int maxval);
	void insert(int t);
	int size();
	void report(int *v);
};

void gensets(int m, int maxval)
{
	int *v = new int[m];
	IntSetImp S(m, maxval);
	while(S.size() < m)
	  S.insert(bigrand() % maxval);
	S.report(v);
	for(int i = 0; i<m; i++)
	  cout<< v[i]<< "\n";
}
```


下面STL实现的set模板。

```
class IntSetSTL {
private:
	set<int> S;
public:
	IntSetSTL(int maxelements, int maxval){}
	int size(){ return S.size();}
	void insert(int t){S.insert(t);}
	void report(int *v)
	{
		int j = 0;
		set<int>::iterator i;
		for(i = S.begin();i != S.end(); ++i)
			v[j++] = *i;
	}
}
```
