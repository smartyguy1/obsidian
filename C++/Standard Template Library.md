
# `for_each()
For this we need to include the library `algorithm`. 
An illustration of this function:

```c++
#include <iostream>
#include <algorithm> // for_each, count_if, all_of
#include <vector>

using namespace std;

// for_each(starting, iterator, ending iterator, some function)
void triple_it(int& value){
    value = value*3;
}

void print(const vector<int>&v){
    for(auto n : v)
        cout << n << " ";
    cout << endl;
}

int main(){
    vector<int> v{8,6,7,5,3,0,9};
    print(v);
    
    vector<int>::iterator it_front= v.begin(), it_back = v.end();
    
    it_front += 2;
    it_back -= 2;
    
    for_each(it_front, it_back, triple_it);
    print(v);
}
```
# `count_if`
Need to import the `algorithm` library:
```c++
#include <iostream>
#include <algorithm> // for_each, count_if, all_of
#include <vector>
using namespace std;
// for_each(starting, iterator, ending iterator, some function)

bool is_even(int n){
    if (n%2 == 0)
        return true;
    else
        return false;
}

void print(const vector<int>&v){
    for(auto n : v)
        cout << n << " ";
    cout << endl;
}

int main(){
    vector<int> v{8,6,7,5,3,0,9};
    int count = count_if(v.cbegin(), v.cend(), is_even);
    cout << "The total number of evens: " << count << endl;
}
```


# `all_of()`

```c++
#include <iostream>
#include <algorithm> // for_each, count_if, all_of
#include <vector>
using namespace std;
// for_each(starting, iterator, ending iterator, some function)

bool is_even(int n){
    if (n%2 == 0)
        return true;
    else
        return false;
}

bool non_negative(int n){
    return n >= 0;
}

void print(const vector<int>&v){
    for(auto n : v)
        cout << n << " ";
    cout << endl;
}

int main(){

    vector<int> v{8,6,7,5,3,0,9};

    if (all_of(v.cbegin(), v.cend(), is_even))
        cout << "All are even\n";
    else
        cout << "Not all are even\n"; 

    if(all_of(v.cbegin(), v.cend(), non_negative))
        cout << "All are non-negative\n";
    else
        cout << "Not all are non-negative\n";
}
```
