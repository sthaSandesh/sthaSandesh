- HI it's me Sandesh Shrestha (Sandy).
- Am a developer prefer to code in dark mode cause light attract bugs.



#include <stdio.h>

#define N 3
void gaussianElimination(float a[N][N + 1])
{
    int i, j, k;
    for (i = 0; i < N; i++)
    {
        for (j = i + 1; j < N; j++)
        {
            float ratio = a[j][i] / a[i][i];
            for (k = 0; k <= N; k++)
            {
                a[j][k] = a[j][k] - ratio * a[i][k];
            }
        }
    }
}

void printSolution(float a[N][N + 1])
{
    float sol[N];
    for (int i = N - 1; i >= 0; i--)
    {
        sol[i] = a[i][N];
        for (int j = i + 1; j < N; j++)
        {
            sol[i] = sol[i] - a[i][j] * sol[j];
        }
        sol[i] = sol[i] / a[i][i];
    }

    printf("\nSolution: ");
    for (int i = 0; i < N; i++)
    {
        printf("%f ", sol[i]);
    }
}

int main()
{
    float a[N][N + 1] = {{3.0, 2.0, -4.0, 3.0},
                         {2.0, 3.0, 3.0, 15.0},
                         {5.0, -3, 1.0, 14.0}};
    gaussianElimination(a);
    printSolution(a);
    return 0;
}

<!---
sthaSandesh/sthaSandesh is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
