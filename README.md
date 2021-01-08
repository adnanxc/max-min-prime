# max-min-prime
Write a C++ code with a function named “maxmin()” which takes 3 arguments from the main function and find the minimum, maximum among them. That means, numbers will be user input in main function which will be passed to the “maxmin()” function. After that the “maxmin()” function will call another function named ”prime()” which takes all these three arguments from the “maxmin()” function and find which numbers are prime only among them


#include <iostream>
using namespace std;

void prime(float a , float b , float c){
    int x = a;
    int y = b;
    int z = c;
    int aPrime = 1 , bPrime = 1 , cPrime = 1;

    if(a-x==0){
        if(a<0){
            aPrime = 0;
        }
        else{
            for(int i=2; i<a; i++){
                if(x%i==0){
                    aPrime = 0;
                    break;
                }
            }
        }
    }

    if(b-y==0){
        if (b<0){
            bPrime = 0;
        }
        else {
            for(int i=2; i<b; i++){
                if(y%i==0){
                    bPrime = 0;
                    break;
                }
            }
        }
    }

    if(c-z==0){
        if(c<0){
            cPrime = 0;
        }
        else{
            for(int i=2; i<c; i++){
                if(z%i==0){
                    cPrime = 0;
                    break;
                }
            }
        }
    }
    if(aPrime==1){
        cout << a << " is prime" << endl;
    }
    if(bPrime==1){
        cout << b << " is prime" << endl;
    }
    if(cPrime==1){
        cout << c << " is prime" << endl;
    }
}

void maxmin(float a , float b , float c){
    float max , min;
    max = a;
    if(b>a && b>c){
        max = b;
    }
    else if(c>b && c>a){
        max = c;
    }

    min = a;
    if(b<a && b<c){
        min = b;
    }
    else if(c<b && c<a){
        min = c;
    }

    cout << "Max: " << max << endl;
    cout << "Min: " << min << endl;
    prime(a , b , c);
}

int main(){
    float a , b , c;
    cout << "Enter the first number: ";
    cin >> a;
    cout << "Enter the second number: ";
    cin >> b;
    cout << "Enter the third number: ";
    cin >> c;
    maxmin(a , b , c);


    return 0;
}
