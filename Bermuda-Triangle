#include "stdafx.h"
#include <iostream>
#include <cstdlib>
#include <string>

using namespace std;

struct player
{
	string name;
	int marks[13];
	int wynik;
};

player** inicjalizacja(int n)
{
	player** zawodnicy=new player*[n];
	for (int i=0;i<n;i++)
	{
		zawodnicy[i]=new player;
		cout<<"Podaj ksywe gracza nr. "<<i+1<<"   Ksywa: ";
		cin>>zawodnicy[i]->name;
		zawodnicy[i]->wynik=0;

		for(int j=0;j<13;j++)
		{
			zawodnicy[i]->marks[j]=0;
		};
	};
	return zawodnicy;
};

void wyswietlanie(player** zawodnicy,int n)
{
	for(int i=0;i<n;i++)
	{
		cout<<"Zawodnik: "<<zawodnicy[i]->name<<endl;
	};
};

void rzut(player** zawodnicy, int n, int sektor)
{
	cout<<"Wpisz ilosc rzuconych ("<<sektor<<")"<<endl;
	for(int i=0;i<n;i++)
	{
		cout<<zawodnicy[i]->name<<": ";
		cin>>zawodnicy[i]->marks[sektor-12];
		if (zawodnicy[i]->marks[sektor-12]!=0)	zawodnicy[i]->wynik+=zawodnicy[i]->marks[sektor-12] * sektor;
		else zawodnicy[i]->wynik=zawodnicy[i]->wynik/2;
		cout<<"Wynik: "<<zawodnicy[i]->wynik<<endl;

	};
};

void o_rzut(player** zawodnicy,int n,int o,int sektor)
{
	cout<<"Wpisz ilosc rzuconych (suma singli) (x"<<o<<")"<<endl;
	for(int i=0;i<n;i++)
	{
		cout<<zawodnicy[i]->name<<": ";
		cin>>zawodnicy[i]->marks[sektor];
		if (zawodnicy[i]->marks[sektor]!=0)	zawodnicy[i]->wynik+=zawodnicy[i]->marks[sektor] * o;
		else zawodnicy[i]->wynik=zawodnicy[i]->wynik/2;
		cout<<"Wynik: "<<zawodnicy[i]->wynik<<endl;

	};
};

void obsluga(player** zawodnicy,int n)
{
	for(int k=12;k<15;k++) rzut(zawodnicy,n,k);
	o_rzut(zawodnicy,n,2,3);

	for(int k=15;k<18;k++) rzut(zawodnicy,n,k);
	o_rzut(zawodnicy,n,3,7);

	for(int k=15;k<21;k++) rzut(zawodnicy,n,k);
	
};




int _tmain(int argc, _TCHAR* argv[])
{

	int n=4;
	player** zawodnicy=inicjalizacja(n);
	obsluga(zawodnicy,n);

	system("pause");


	
}

