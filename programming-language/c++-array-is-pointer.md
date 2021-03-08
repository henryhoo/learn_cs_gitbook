# C++: Array is pointer

### Create array in two ways

Create an array in normal way VS use pointer to represent array. 

```cpp
#include <iostream>

using namespace std;

int main()
{
    int SIZE = 3;
    int array[SIZE] = {101,202,303};
    int* arrayUsingPointer = (int *) malloc(SIZE * sizeof(int));
    arrayUsingPointer[0] = 111;
    arrayUsingPointer[1] = 222;
    arrayUsingPointer[2] = 333;
    
    cout << "address of array: " << array << endl;
    cout << "value of array: " << &array << endl;
    cout << "content of array:" << endl;
    for (int i = 0; i < SIZE; i++) {
        cout << i << ": " << array[i] << endl;
    }
    cout << "==============================" << endl;
    cout << "address of arrayUsingPointer: " << arrayUsingPointer << endl;
    cout << "value of arrayUsingPointer: " << &arrayUsingPointer << endl;
    cout << "content of arrayUsingPointer:" << endl;
    for (int i = 0; i < SIZE; i++) {
        cout << i << ": " << arrayUsingPointer[i] << endl;
    }
    return 0;
}
```

Output:

```cpp
address of array: 0x7ffc230ac750                                                                                                                                                                                                           
value of array: 0x7ffc230ac750                                                                                                                                                                                                             
content of array:                                                                                                                                                                                                                          
0: 101                                                                                                                                                                                                                                     
1: 202                                                                                                                                                                                                                                     
2: 303                                                                                                                                                                                                                                     
==============================                                                                                                                                                                                                             
address of arrayUsingPointer: 0x20c6c20                                                                                                                                                                                                    
value of arrayUsingPointer: 0x7ffc230ac770                                                                                                                                                                                                 
content of arrayUsingPointer:                                                                                                                                                                                                              
0: 111                                                                                                                                                                                                                                     
1: 222                                                                                                                                                                                                                                     
2: 333 
```

Memory Visualization:

![](../.gitbook/assets/image%20%281%29.png)

[Try yourself in C++ Tutor](http://pythontutor.com/cpp.html#code=%23include%20%3Ciostream%3E%0A%0Ausing%20namespace%20std%3B%0A%0Aint%20main%28%29%0A%7B%0A%20%20%20%20int%20array%5B3%5D%20%3D%20%7B101,202,303%7D%3B%0A%20%20%20%20int*%20arrayUsingPointer%20%3D%20%28int%20*%29%20malloc%283%20*%20sizeof%28int%29%29%3B%0A%20%20%20%20arrayUsingPointer%5B0%5D%20%3D%20111%3B%0A%20%20%20%20arrayUsingPointer%5B1%5D%20%3D%20222%3B%0A%20%20%20%20arrayUsingPointer%5B2%5D%20%3D%20333%3B%0A%20%20%20%20%0A%20%20%20%20cout%20%3C%3C%20%22address%20of%20array%3A%20%22%20%3C%3C%20array%20%3C%3C%20endl%3B%0A%20%20%20%20cout%20%3C%3C%20%22value%20of%20array%3A%20%22%20%3C%3C%20%26array%20%3C%3C%20endl%3B%0A%20%20%20%20cout%20%3C%3C%20%22content%20of%20array%3A%22%20%3C%3C%20endl%3B%0A%20%20%20%20for%20%28int%20i%20%3D%200%3B%20i%20%3C%203%3B%20i%2B%2B%29%20%7B%0A%20%20%20%20%20%20%20%20cout%20%3C%3C%20i%20%3C%3C%20%22%3A%20%22%20%3C%3C%20array%5Bi%5D%20%3C%3C%20endl%3B%0A%20%20%20%20%7D%0A%20%20%20%20cout%20%3C%3C%20%22%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%22%20%3C%3C%20endl%3B%0A%20%20%20%20cout%20%3C%3C%20%22address%20of%20arrayUsingPointer%3A%20%22%20%3C%3C%20arrayUsingPointer%20%3C%3C%20endl%3B%0A%20%20%20%20cout%20%3C%3C%20%22value%20of%20arrayUsingPointer%3A%20%22%20%3C%3C%20%26arrayUsingPointer%20%3C%3C%20endl%3B%0A%20%20%20%20cout%20%3C%3C%20%22content%20of%20arrayUsingPointer%3A%22%20%3C%3C%20endl%3B%0A%20%20%20%20for%20%28int%20i%20%3D%200%3B%20i%20%3C%203%3B%20i%2B%2B%29%20%7B%0A%20%20%20%20%20%20%20%20cout%20%3C%3C%20i%20%3C%3C%20%22%3A%20%22%20%3C%3C%20arrayUsingPointer%5Bi%5D%20%3C%3C%20endl%3B%0A%20%20%20%20%7D%0A%20%20%20%20return%200%3B%0A%7D&curInstr=17&mode=display&origin=opt-frontend.js&py=cpp_g%2B%2B9.3.0&rawInputLstJSON=%5B%5D)

### Represent array using pointer 

Add following code to previous example, to use `arrayUsingPointer` to represent the original `array`

```cpp
    cout << "==============================" << endl;
    // point arrayUsingPointer to array
    arrayUsingPointer = array;
    cout << "address of arrayUsingPointer: " << arrayUsingPointer << endl;
    cout << "value of arrayUsingPointer: " << &arrayUsingPointer << endl;
    cout << "content of arrayUsingPointer:" << endl;
    for (int i = 0; i < SIZE; i++) {
        cout << i << ": " << arrayUsingPointer[i] << endl;
    }
```

Output:

```cpp
address of array: 0x7ffed9a54d20
value of array: 0x7ffed9a54d20
content of array:
0: 101
1: 202
2: 303
==============================
address of arrayUsingPointer: 0x1579c20
value of arrayUsingPointer: 0x7ffed9a54d40
content of arrayUsingPointer:
0: 111
1: 222
2: 333
==============================
address of arrayUsingPointer: 0x7ffed9a54d20
value of arrayUsingPointer: 0x7ffed9a54d40
content of arrayUsingPointer:
0: 101
1: 202
2: 303
```

Memory Visualization:

![](../.gitbook/assets/image%20%282%29.png)

[Try yourself in C++ Tutor](http://pythontutor.com/cpp.html#code=%23include%20%3Ciostream%3E%0A%0Ausing%20namespace%20std%3B%0A%0Aint%20main%28%29%0A%7B%0A%20%20%20%20int%20array%5B3%5D%20%3D%20%7B101,202,303%7D%3B%0A%20%20%20%20int*%20arrayUsingPointer%20%3D%20%28int%20*%29%20malloc%283%20*%20sizeof%28int%29%29%3B%0A%20%20%20%20arrayUsingPointer%5B0%5D%20%3D%20111%3B%0A%20%20%20%20arrayUsingPointer%5B1%5D%20%3D%20222%3B%0A%20%20%20%20arrayUsingPointer%5B2%5D%20%3D%20333%3B%0A%20%20%20%20%0A%20%20%20%20cout%20%3C%3C%20%22address%20of%20array%3A%20%22%20%3C%3C%20array%20%3C%3C%20endl%3B%0A%20%20%20%20cout%20%3C%3C%20%22value%20of%20array%3A%20%22%20%3C%3C%20%26array%20%3C%3C%20endl%3B%0A%20%20%20%20cout%20%3C%3C%20%22content%20of%20array%3A%22%20%3C%3C%20endl%3B%0A%20%20%20%20for%20%28int%20i%20%3D%200%3B%20i%20%3C%203%3B%20i%2B%2B%29%20%7B%0A%20%20%20%20%20%20%20%20cout%20%3C%3C%20i%20%3C%3C%20%22%3A%20%22%20%3C%3C%20array%5Bi%5D%20%3C%3C%20endl%3B%0A%20%20%20%20%7D%0A%20%20%20%20cout%20%3C%3C%20%22%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%22%20%3C%3C%20endl%3B%0A%20%20%20%20cout%20%3C%3C%20%22address%20of%20arrayUsingPointer%3A%20%22%20%3C%3C%20arrayUsingPointer%20%3C%3C%20endl%3B%0A%20%20%20%20cout%20%3C%3C%20%22value%20of%20arrayUsingPointer%3A%20%22%20%3C%3C%20%26arrayUsingPointer%20%3C%3C%20endl%3B%0A%20%20%20%20cout%20%3C%3C%20%22content%20of%20arrayUsingPointer%3A%22%20%3C%3C%20endl%3B%0A%20%20%20%20for%20%28int%20i%20%3D%200%3B%20i%20%3C%203%3B%20i%2B%2B%29%20%7B%0A%20%20%20%20%20%20%20%20cout%20%3C%3C%20i%20%3C%3C%20%22%3A%20%22%20%3C%3C%20arrayUsingPointer%5Bi%5D%20%3C%3C%20endl%3B%0A%20%20%20%20%7D%0A%20%20%20%20%0A%20%20%20%20cout%20%3C%3C%20%22%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%22%20%3C%3C%20endl%3B%0A%20%20%20%20//%20point%20arrayUsingPointer%20to%20array%0A%20%20%20%20arrayUsingPointer%20%3D%20array%3B%0A%20%20%20%20cout%20%3C%3C%20%22address%20of%20arrayUsingPointer%3A%20%22%20%3C%3C%20arrayUsingPointer%20%3C%3C%20endl%3B%0A%20%20%20%20cout%20%3C%3C%20%22value%20of%20arrayUsingPointer%3A%20%22%20%3C%3C%20%26arrayUsingPointer%20%3C%3C%20endl%3B%0A%20%20%20%20cout%20%3C%3C%20%22content%20of%20arrayUsingPointer%3A%22%20%3C%3C%20endl%3B%0A%20%20%20%20for%20%28int%20i%20%3D%200%3B%20i%20%3C%203%3B%20i%2B%2B%29%20%7B%0A%20%20%20%20%20%20%20%20cout%20%3C%3C%20i%20%3C%3C%20%22%3A%20%22%20%3C%3C%20arrayUsingPointer%5Bi%5D%20%3C%3C%20endl%3B%0A%20%20%20%20%7D%0A%20%20%20%20return%200%3B%0A%7D&curInstr=38&mode=display&origin=opt-frontend.js&py=cpp_g%2B%2B9.3.0&rawInputLstJSON=%5B%5D)



