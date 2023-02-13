// 백준 2239번 스도쿠 문제
// https://www.acmicpc.net/problem/2239

#define _CRT_SECURE_NO_WARNINGS

#include <iostream>

#include<stdbool.h>

using namespace std;

char s[11][11];

bool check(int n)
{
	char x = s[n / 9][n % 9];
	int count = 0;
	for (int i = 0;i < 9;i++)
	{
		if (s[n / 9][i] == x)
			count++;
	}
	//printf("%d count is %d %c\n\n", n, count,x);
	if (count > 1)
		return false;
	for (int i = 0;i < 9;i++)
	{
		if (s[i][n % 9] == x)
			count++;
	}
	//printf("%d count is %d %c\n\n", n, count, x);
	if (count > 2)
		return false;
	int a = ((n / 9) / 3) * 3;
	int b = ((n % 9) / 3) * 3;


	//printf("%d %d check\n\n", n / 9, n % 9);

	for (int i = 0;i < 3;i++)
	{
		for (int j = 0;j < 3;j++)
		{
			if (s[a + i][b + j] == x)
				count++;
			//printf("%c %c\n", s[a + i][b + j], x);
		}
	}
	//printf("\n");

	if (count > 3)
		return false;
	return true;
}

bool dt(int n)
{
	if (n == 81)
		return 1;
	if (s[n / 9][n % 9] != '0')
	{
		return dt(n + 1);
	}
	for (int i = 1;i < 10;i++)
	{
		s[n / 9][n % 9] = i + '0';
		if (check(n))
		{
			//printf("%d %d\n", n, i);
			if (dt(n + 1))
			{
				//printf("%d %d\n", n, i);
				return 1;
				
			
			}
		}
		
	}
	s[n / 9][n % 9] = '0';
	//printf("false%d %c\n", n, s[n / 9][n % 9]);
	return false;
}




int main()
{
	
	for (int i = 0;i < 9;i++)
	{
		scanf("%s", s[i]);
	}

	dt(0);
	//printf("\n");
	for (int i = 0;i < 9;i++)
	{
		printf("%s\n", s[i]);
	}

}
