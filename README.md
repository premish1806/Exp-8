# Exp-8 Matrix Operations Using C++

## Aim:
To write and understand C++ programs that perform basic matrix operations such as displaying a matrix, matrix addition, matrix multiplication, diagonal element summation, and matrix transposition.

## Software Used:
- Dev c++

## Theory:
These C++ programs demonstrate basic matrix operations, which are essential in various computational tasks. The first program teaches how to take user input to create and display a matrix, ensuring that data is organized correctly in rows and columns. This forms the foundation for more complex operations by ensuring that matrices are correctly initialized and displayed.

The subsequent programs explore operations like matrix addition, multiplication, diagonal element summation, and transposition. Matrix addition combines corresponding elements from two matrices, while multiplication involves a more intricate process of combining rows and columns. Summing diagonal elements helps in understanding the special properties of square matrices, and transposition flips a matrix over its diagonal, swapping rows with columns. Each of these operations builds on the previous one, helping to reinforce the concepts of matrix manipulation in C++.


## Program 1: Take number of rows, columns and elements from user and display it in the form of matrix. 
<br>

<strong> Code: </strong>
<br>
```cpp
// Premish Ninawe
// 23070123092
// ENTC B1
#include<iostream>
using namespace std;
int main()
{
    int r, c, i, j;
    cout<< " Enter number of rows: ";
    cin>> r;
    cout<<" Enter number of columns: ";
    cin>> c;
    int arr[r][c];
    for (i=0 ; i < r ; i++)
    {
        for(j = 0 ; j < c ; j++)
        {
            cout<< "Enter elements ("<<i<< "," <<j<<"): ";
            cin>>arr[i][j];
        }
    }
    for (i=0 ; i<r ; i++)
    {
        for(j = 0; j< c ; j++)
        { 
            cout<< " "<< arr[i][j];
        }
        cout<<endl;
    }
}
```
<strong> Output: </strong>
<br>
![image](https://github.com/user-attachments/assets/812d348b-be19-46a3-9205-bbd4dd1b1337)


## Program 2: Take two matrices from user and perform addition and multiplication.
<br>

<strong> Code: </strong>
<br>
```cpp
// Premish Ninawe
// 23070123092
// ENTC B1
#include<iostream>
using namespace std;
int main()
{
    int a, b, c, d, i, j, k;
    cout<< " Enter matrix-1 rows: ";
    cin>> a;
    cout<<" Enter matrix-1 columns: ";
    cin>> b;
    cout<< " Enter matrix-2 rows: ";
    cin>> c;
    cout<<" Enter matrix-2 columns: ";
    cin>> d;

    int mat1[a][b];
    int mat2[c][d];
    int add [a][b];
    int mul [a][d];

    if (a != c || b != d)
    {
        cout<< "Matrix cannot be added as dimensions do not match."<<endl;
    }
    else
    {
        for (i = 0; i < a; i++)
        {
            for (j = 0; j < b; j++)
            {
                cout<< "Enter elements ("<<i<< "," <<j<<"): ";
                cin>>mat1[i][j];
            }
        }

        for (i = 0; i < c; i++)
        {
            for (j = 0; j < d; j++)
            {
                cout<< "Enter elements ("<<i<< "," <<j<<"): ";
                cin>>mat2[i][j];
            }
        }

        for (i = 0; i < a; i++)
        {
            for (j = 0; j < b; j++)
            {
                add[i][j] = mat1[i][j] + mat2[i][j];
            }
        }

        cout<<"ADDITION OF MATRIX: "<<endl;
        for (i = 0; i < a; i++)
        {
            for (j = 0; j < b; j++)
            {
                cout<< " " <<add[i][j];
            }
            cout<<endl;
        }
    }

    if (b != c)
    {
        cout<< "Matrices cannot be multiplied as dimensions do not match." <<endl;
        return 1;
    }

    for(i = 0; i < a; i++)
    {
        for(j = 0; j < d; j++)
        {
            mul[i][j] = 0;
            for(k = 0; k < b; k++)
            {
                mul[i][j] += mat1[i][k] * mat2[k][j];
            }
        }
    }

    cout << "MULTIPLICATION OF MATRIX: "<<endl;
    for (i = 0; i < a; i++)
    {
        for (j = 0; j < d; j++)
        {
            cout<< " " <<mul[i][j];
        }
        cout<<endl;
    }
}
```
<strong> Output: </strong>
<br>
![image](https://github.com/user-attachments/assets/60b35c20-360c-448c-a253-5dae1b682f5e)



## Program 3: Take matrix elements from user and perform addition of diagonal elements.
<br>

<strong> Code: </strong>
<br>
```cpp
// Premish Ninawe
// 23070123092
// ENTC B1
#include<iostream>
using namespace std;
int main()
{
    int i, j, r1, c1, sum = 0, sum2 = 0;
    cout<<"Enter number of rows and columns of first matrix: ";
    cin>>r1>>c1;
    int mat1[r1][c1];

    if(r1 != c1)
    {
        cout<<"ONLY SQUARE MATRICES ARE TO BE ENTERED!"<<endl;
    }
    else
    {
        for(i = 0; i < r1; i++)
        {
            for(j = 0; j < c1; j++)
            {
                cout<<"Enter elements ("<<i<< "," <<j<<"): ";
                cin>>mat1[i][j];
            }
        }

        for(i = 0; i < r1; i++)
        {
            for(j = 0; j < c1; j++)
            {
                if(i == j)
                {
                    sum += mat1[i][j];
                }
                if(i + j == r1 - 1)
                {
                    sum2 += mat1[i][j];
                }
            }
        }
        cout<< "Sum of main diagonal elements is: "<<sum<<endl;
        cout<<"Sum of anti-diagonal elements is: "<<sum2<<endl;
    }
}
```
<strong> Output: </strong>
<br>
![image](https://github.com/user-attachments/assets/2d014868-61cb-4db2-9c39-3fc5f6369fb9)



## Program 4: Take matrix elements from user and perform transpose operation on the matrix.
<br>

<strong> Code: </strong>
<br>
```cpp
// Premish Ninawe
// 23070123092
// ENTC B1
#include<iostream>
using namespace std;
int main()
{
    int r, c, i, j;
    cout<< " Enter number of rows: ";
    cin>> r;
    cout<<" Enter number of columns: ";
    cin>> c;
    int arr[r][c], arr2[c][r];

    for (i=0 ; i < r ; i++)
    {
        for(j = 0; j < c; j++)
        {
            cout<< "Enter elements ("<<i<< "," <<j<<"): ";
            cin>>arr[i][j];
        }
    }

    for (i=0; i < r; i++)
    {
        for(j = 0; j < c; j++)
        { 
            cout<< " " << arr[i][j];
        }
        cout<<endl;
    }

    for (i=0; i < c; i++)
    {
        for(j = 0; j < r; j++)
        { 
            arr2[i][j] = arr[j][i];
        }
    }

    cout<<endl<<"TRANSPOSE OF MATRIX:"<<endl;
    for (i=0; i < c; i++)
    {
        for(j = 0; j < r; j++)
        { 
            cout<< " " << arr2[i][j];
        }
        cout<<endl;
    }
}
```
<strong> Output: </strong>
<br>
![image](https://github.com/user-attachments/assets/3a891ee8-5fd6-45bb-a33d-00c0607b6204)


## Conclusion:
Through these C++ programs, we learned how to perform essential matrix operations such as displaying a matrix, addition, multiplication, diagonal element summation, and transposition. These fundamental operations help in understanding how matrices work in programming, providing a strong foundation for more advanced computational tasks.
