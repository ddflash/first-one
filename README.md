# first-one
nothing
#include<bits/stdc++.h>
#include<windows.h>
using namespace std;
int main()
{
	int x,a;
	srand((unsigned int)time(NULL));
	x=rand()%1000+1;
	int t=1,w=0;
	while(t)
	{
		if(w==11)
		{
			cout<<"you lose";
			return 0;
		}
		cin>>a;
		w++;
		if(a==x)
		t=0;
		if(a<x)
		cout<<"small"<<endl;
		if(a>x)
		cout<<"big"<<endl;
	}
	cout<<"you win!"<<endl;
	cout<<"you guess "<<w<<" times";
}
