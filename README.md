#include<iostream>
#include<math.h>
using namespace std;

struct Mathang
{
	string MaHang;
	string LoaiHang;
	string TenHang;
	int SoLuong;
	float DonGia;
	string Ga;
};
typedef struct Node
{
	Mathang data;
	Node *Next;	
};
typedef Node *Nodeptr;


Nodeptr CreateNode(Mathang x)
{
	Nodeptr p;
	p=new Node;
	p->data=x;
	p->Next=NULL;
	return p;
}
void InsertLast(Nodeptr &Head,Nodeptr &Tail,Nodeptr p)
{
	if(Head==NULL)
	{
		Head=p;
		Tail=p;
	}
	else
	{
		Tail->Next=p;
		Tail=p;
	}
}
void xuat(Mathang x)
{
	cout<<x.MaHang<<"\t"<<x.LoaiHang<<"\t"<<x.TenHang<<"\t";
	cout<<x.SoLuong<<"\t"<<x.DonGia<<"\t"<<x.Ga<<endl;
}
void Print(Nodeptr Head,Nodeptr Tail)
{
	Nodeptr p=Head;
	while(p!=NULL)
	{
		xuat(p->data);
		p=p->Next;
	}
}
int main()
{
	Nodeptr p,Head,Tail;
	Head=Tail=NULL;
	Mathang x[3]=
	{	{"MH01","Nuoc Ngot","pepsi",64,7,"Co"},
		{"MH02","Nuoc Suoi","aquafina",7,4,"Khong"},
		{"MH01","Nuoc Ngot","cocacola",16,7.5,"Co"}
	};
	for(int i=0;i<3;i++)
	{
	 
	p=CreateNode(x[i]);
	int k = sqrt(x[i].SoLuong);
	if(k *k == x[i].SoLuong)
	{InsertLast(Head,Tail,p);}
	};
	cout<<"\n Xuat mat hang "<<endl;
	Print(Head,Tail);
}
