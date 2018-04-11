# Homework
// Kalin.cpp : Defines the entry point for the console application.
//

#include "stdafx.h"
#include <iostream>

using namespace std;

int main()
{
	int arr[5], br=0, br2=0;
	int i, moda=1, vremennamoda=1, oficialnamoda=1;
	double srednoaritmetichno=0, mediana;
	arr[0] = 5;
	arr[1] = 4;
	arr[2] = 2;
	arr[3] = 4;
	arr[4] = 3;
	br = arr[0];
	if (!(br % 2 == 0))
	{
		mediana = arr[br/2];
	}
	else
	{
		i = br / 2;
		mediana = (arr[i] + arr[i + 1]) / 2;
	}
	cout << "Medianata e: " << mediana << endl;

	for (i = 0; i < br; i++)
	{
		srednoaritmetichno = srednoaritmetichno + arr[i];
	}
	cout << "Sredno aritmetichnoto e: " << srednoaritmetichno /br << endl;

	for (int i = 0; i < br-1; i++)
	{
		for (int j = 0; j < br - 1; j++)
		{
			if (arr[j] > arr[j + 1])
			{
				int vremenna = arr[j];
				arr[j] = arr[j+1];
				arr[j+1] = vremenna;
			}
		}
	}
	for (int i = 0; i < br; i++)
	{
		if (arr[i] == arr[i + 1])
		{
			vremennamoda++;
			if (vremennamoda > moda)
			{
				moda = vremennamoda;
				oficialnamoda = arr[i];
			}
		}
	}
	cout << "Modata e: " << oficialnamoda << endl;

	if (mediana >= (srednoaritmetichno/br))
	{
		if (mediana >= oficialnamoda)
		{
			cout << "Reshenie na mnogo gadnata zadacha na Kalin e: " << mediana << "!" << endl;
		}
		else
		{
			cout << "Reshenie na mnogo gadnata zadacha na Kalin e: " << oficialnamoda << "!" << endl;
		}
	}
	else
	{
		if ((srednoaritmetichno / br) >= oficialnamoda)
		{
			cout << "Reshenie na mnogo gadnata zadacha na Kalin e: " << (srednoaritmetichno / br) << "!" << endl;
		}
		else
		{
			cout << "Reshenie na mnogo gadnata zadacha na Kalin e: " << oficialnamoda << "!" << endl;
		}
	}
    return 0;
}

