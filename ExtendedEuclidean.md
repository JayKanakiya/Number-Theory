
# Extended Euclidean
GCD(A,B) has a special property that it can always be represented in the form of an equation, i.e., Ax + By = GCD(A, B).

This algorithm gives us the coefficients (x and y) of this equation which will be later useful in finding the Modular Multiplicative Inverse. These coefficients can be zero or negative in their value. This algorithm takes two inputs as A and B and returns GCD(A, B) and coefficients of the above equations as output.

```
#include < iostream >

int d, x, y;
void extendedEuclid(int A, int B) {
    if(B == 0) {
        d = A;
        x = 1;
        y = 0;
    }
    else {
        extendedEuclid(B, A%B);
        int temp = x;
        x = y;
        y = temp - (A/B)*y;
    }
}

int main( ) {
extendedEuclid(16, 10);
cout << ”The GCD of 16 and 10 is ” << d << endl;
return 0;   
}
```
