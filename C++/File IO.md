# Write and append file

```c++
#include <iostream>
#include <fstream>
using namespace std;

int main(){
    fstream myfile;
    myfile.open("file.txt", ios::out/*This is write mode*/); // myfile.open(name_of_file, mode)
    //The write mode overwrites everything previously written
    if(myfile.is_open()){
        myfile << "Hello\n";
        myfile << "This is second line\n";
        myfile.close();
    }

    myfile.open("file.txt", ios::app/*This is append mode*/); // myfile.open(name_of_file, mode)

    if(myfile.is_open()){
        myfile << "Hello2\n";
        myfile.close();

    }

}
```

# Read File
```c++
#include <iostream>
#include <fstream>
#include <string>
using namespace std;
int main(){
    fstream myfile;
    myfile.open("file.txt", ios::in); //read mode
    if(myfile.is_open()){
        string line;
        while(getline(myfile, line)){
            cout << line << endl;
        }
        myfile.close();
    }

}
```
