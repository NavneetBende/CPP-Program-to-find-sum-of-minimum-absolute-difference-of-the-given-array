Sum of minimum absolute difference in C++
Here, in this page we will discuss sum with minimum absolute difference in C++. We will discuss the two different ways to solve the given problem and compare there time and space complexities.

sum of minimum absolute difference in C++
While loop in C
Here, we will discuss the following two different methods to solve this problem.
Method 1 : Naive Way
Method 2 : Efficient way
Method 1 :
Take a variable say result = INT_MAX, to hold the required minimum sum.
Run an outer loop from index 0 to n,
Create a variable say sum = 0,
Run an inner loop from index 0 to n,
Set, sum += abs(arr[i]-arr[j])
After complete iteration of inner loop set,
result = min(result, sum).
Print result.
Time and Space Complexity :
Time Complexity : O(n2)
Space Complexity : O(1)
Method 1 : Code in C++
//Write a program to find sum of minimum absolute difference of the given array in C++
#include<iostream>
#include<limits/h>
using namespace std;

int main()
{
    int arr[]={2, 4, 5, 3};
    int result = INT_MAX;

    int n = sizeof(arr)/sizeof(arr[0]);

    for(int i=0; i<n; i++){
        int sum =0 ; // variable to hold the sum
        for(int j=0; j<n; j++){
            int x=arr[i]-arr[j];
            if(x<0)
                sum += -x;

            else sum += x;
        }    
    
        if(sum<result)
            result = sum;
        
    }
    cout<<"Minimum Absolute Difference Sum is "<<result;
    return 0;
}
Output
Minimum Absolute Difference Sum is 4
Related Pages
Determine Array is a subset of another array or not

Determine can all numbers of an array be made equal

Sort an array according to the order defined by another array 

Replace each element of the array by its rank in the array

Finding equilibrium index of an array

Method 2 :
Sort the array using inbuilt sort function.
Create a variable say median that store the median of the array in it.
If the size of array is even then median= (a[n/2]+a[n/2+1])/2, otherwise median = a[n/2], here a [] is the array and n is the size of the array.
Create a variable say sum that holds the sum in it and initialize it with 0.
Iterate over the array and add the absolute difference in the sum.
Print the sum.
Time and Space Complexity :
Time Complexity : O(nlogn)
Space Complexity : O(1)
Method 2 : Code in C++
//Write a program to find sum of minimum absolute difference of the given array in C++
#include<bits/stdc++.h>
using namespace std;

int main()
{
    int arr[]={2, 4, 5, 3};

    int n = sizeof(arr)/sizeof(arr[0]);

    sort(arr, arr+n);  //sort array

    int median ; //variable to store the median

    if(n%2==0)
    median = ((arr[n/2]+arr[n/2+1])/2);

    else median = arr[n/2];

    int sum =0 ; // variable to hold the sum

    for(int i=0; i<n; i++){

        int x=arr[i]-median;
        if(x<0)
            sum += -x;

        else sum += x;
    }    
    cout<<"Minimum Absolute Difference Sum is "<<sum;
    return 0;
}
Output
Minimum Absolute Difference Sum is 4
