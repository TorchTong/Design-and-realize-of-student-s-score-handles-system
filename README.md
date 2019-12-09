# Design-and-realize-of-student-s-score-handles-system
成绩处理
#include <stdio.h>

int main()
{
	int n, ch;
	int sn1 = 0, sn2 = 0, sn3 = 0;
	scanf("%d", &n);
	int a[60][3];
	int sum_c = 0;
	int sum_eng = 0;
	int sum_math = 0;
	int max1 = 0, min1 = 0;
	int max2 = 0, min2 = 0;
	int max3 = 0, min3 = 0;
	for (int i = 0; i < n; i++)
	{
		scanf("%d %d %d", &a[i][1], &a[i][2], &a[i][3]);
	}
	printf("请输入需要的功能：\n");
	printf("1.输出每个学生的各科成绩及个人平均分\n");
	printf("2.输出每科目的平均分\n");
	printf("3.输出每科目的最高分与最低分\n");
	printf("4.输出每科目的及格率：\n");
	scanf("%d", &ch);
	switch (ch)
	{
	case 1:
		for (int j = 0; j < n; j++)
		{
			int sum = a[j][1] + a[j][2] + a[j][3];
			int ave = sum / 3;
			printf("学生%d的成绩为：%d %d %d\n", j + 1, a[j][1], a[j][2], a[j][3]);
			printf("学生%d的个人平均分为：%d\n", j + 1, ave);
		}
		break;
	case 2:
		
		for (int j = 0; j < n; j++)
		{
			sum_c += a[j][1];
			sum_eng += a[j][2];
			sum_math += a[j][3];
		}
		printf("程序设计的平均分为：%d", sum_c / n);
		printf("英语的平均分：%d", sum_eng / n);
		printf("数学的平均分：%d", sum_math / n);
		break;
	case 3:
		for (int i = 0; i < n; i++)
		{
			if (a[i][1] > max1)
			{
				max1 = a[i][1];
			}
			if (min1 > a[i][1])
			{
				min1 = a[i][1];
			}
		}
		for (int i = 0; i < n; i++)
		{
			if (a[i][2] > max2)
			{
				max2 = a[i][2];
			}
			if (min2 > a[i][2])
			{
				min2 = a[i][2];
			}
		}
		for (int i = 0; i < 10; i++)
		{
			if (a[i][3] > max3)
			{
				max3 = a[i][3];
			}
			if (min3 > a[i][3])
			{
				min3 = a[i][3];
			}
		}
		printf("程序设计的最高分和最低分为：%d\n", max1, min1);
		printf("英语的最高分和最低分为：%d\n", max2, min2);
		printf("数学的最高分和最低分为：%d\n", max3, min3);
		break;
	case 4:
		for (int i=0;i<n;i++)
		{
			if (a[i][1]>60)
			{
				sn1++;
			}
			else
				continue;
		}
		for (int i = 0; i < n; i++)
		{
			if (a[i][2] > 60)
			{
				sn2++;
			}
			else
				continue;
		}
		for (int i = 0; i < n; i++)
		{
			if (a[i][3] > 60)
			{
				sn3++;
			}
			else
				continue;
		}
		printf("程序设计的及格率为：%d", sn1 / n);
		printf("英语的及格率为：%d", sn2 / n);
		printf("数学的及格率为：%d", sn3 / n);
		break;
	}
	getchar();
	getchar();
}
