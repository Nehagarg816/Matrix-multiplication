# Matrix-multiplication
This is a program for multiplication of any order matrices if valid using arrays and loops in C programming.


#include <stdio.h>
#include <stdlib.h>

int main()
{
    int m, n, p, q;
    printf("Enter number of rows for first matrix:\n");
    scanf("%d", &m);
    printf("Enter number of columns for first matrix:\n");
    scanf("%d", &n);
    int a[m][n];
    printf("Enter number of rows for second matrix:\n");
    scanf("%d", &p);
    printf("Enter number of columns for second matrix:\n");
    scanf("%d", &q);
    int b[p][q];
    
    if (p == n)
    {
        printf("Enter %d numbers for first matrix:\n", m * n);
        for (int i = 0; i < m; i++)
        {
            for (int j = 0; j < n; j++)
            {
                printf("a[%d][%d]=", i, j);
                scanf("%d", &a[i][j]);
            }
        }
        printf("\n \n");
        printf("First matrix:\n");
        for (int i = 0; i < m; i++)
        {
            for (int j = 0; j < n; j++)
            {
                printf("%d\t", a[i][j]);
            }
            printf("\n");
        }

        printf("Enter %d numbers for second matrix:\n", p * q);
        for (int i = 0; i < p; i++)
        {
            for (int j = 0; j < q; j++)
            {
                printf("b[%d][%d]=", i, j);
                scanf("%d", &b[i][j]);
            }
        }
        printf("\n \n");
        printf("Second matrix:\n");
        for (int i = 0; i < p; i++)
        {
            for (int j = 0; j < q; j++)
            {
                printf("%d\t", b[i][j]);
            }
            printf("\n");
        }
        int c[m][q];
        int sum;
        for (int i = 0; i < m; i++)
        {
            for (int j = 0; j < q; j++)
            {
                sum = 0;
                for (int k = 0; k < n; k++)
                {
                    sum = sum + a[i][k] * b[k][j];
                }
                c[i][j] = sum;
                printf("c[%d][%d]= ", i, j);
                printf("%d\n", c[i][j]);
            }
        }
        printf("\n \n");
        printf("Multiplication matrix of a and b matrix is:\n");
        for (int i = 0; i < m; i++)
        {
            for (int j = 0; j < q; j++)
            {
                printf("%d \t", c[i][j]);
            }
            printf("\n");
        }
    }

    else
    {
        printf("MATRIX MULTIPLICATION WILL BE INVALID\n");
    }

    return 0;
}
