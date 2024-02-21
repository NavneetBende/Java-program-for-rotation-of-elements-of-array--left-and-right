Rotation of element of array – left and right
In this program we’ll be learning about Java program for rotation of elements of array- left and right to a specified number of times. An array is said to be right rotated if all the selected elements were  moved towards right by one position.

Rotation of element of array
In this section we will learn about basic knowledge which we need to know before coding the above Program. So we must have knowledge of what is an array? 

What is an array?
An array is a data structure, it is collection of similar data elements which is stored at contiguous memory locations in which each data element can be accessed directly by only using its index number.
 
How to declare an array?
To declare an array in C,a programmer specifies the type of the elements and the number of elements required by an array as follows − This is called a single-dimensional array. The arraySize must be an integer constant greater than zero and type can be any valid C data type. For example, to declare a 10-element array called balanceof type double, use this statement − Here balanceis a variable array which is sufficient to hold up to 10 double numbers.
 
About Java language:-
Java is class-based, object-oriented programming language and used for Internet-based applications. Java is a high-level
language.
Method Discussed :
Method 1 : Using Temporary array.
Method 2 : Rotate one by one.
Method 1 :
In this method we will declare an extra array to store some k elements. Here, k refers to number of rotations.

Declare a temporary array of size k.
Store the first k elements in temp[] array.
Now, shift the remaining elements.
After, shifting the elements add the elements of temp[] in the array.
Method 1 : Code in Java
//Write a program for array rotation in java
class Main {

    public static void main(String[] args)
    {
        int arr[] = { 10, 20, 30, 40, 50, 60, 70};
        int n = arr.length;
        int k = 3;
        
        int[] temp;
         
        temp =  new int[n];
        
        for(int i=0; i<k; i++)
            temp[i] = arr[i];
    
        int x = k;
        for(int i=0; x < n; i++){
            arr[i] = arr[x++];
        }
        
        x = 0;
    
        for(int i=n-k; i<n; i++)
            arr[i] = temp[x++];
    
   
        for (int i = 0; i < 7; i++)
            System.out.print(arr[i] + " ");
    }
}
Output
40 50 60 70 10 20 30
Method 2 :
In this method we will rotate the elements one by one by shifting them.

Time and Space Complexity :
Time Complexity : O(n*k)
Space Complexity : O(1)
Method 2 : Code in Java
//Write a program for array rotation in java
class Main {

    static void leftRotate(int arr[], int d, int n){
        for (int i = 0; i < d; i++)
            leftRotatebyOne(arr, n);
    }
 
    static void leftRotatebyOne(int arr[], int n){
        int i, temp;
        temp = arr[0];
        for (i = 0; i < n - 1; i++)
            arr[i] = arr[i + 1];
        arr[n-1] = temp;
    }
 
    public static void main(String[] args)
    {
        
        int arr[] = { 10, 20, 30, 40, 50, 60, 70 };
        
        leftRotate(arr, 3, 7);
        
        for (int i = 0; i < 7; i++)
            System.out.print(arr[i] + " ");
    }
}
Output
40 50 60 70 10 20 30
