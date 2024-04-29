# Check_Function_In_Class_cpp
A generic template that implements checks for the presence of a function in a class.



# Example

* Step2: Create example Class;

```c++
class objA
{
public:
    objA() {};
    void work() {};
    void test(int idx) {};
    void test() {};
private:
};

class objB
{
public:
    objB() {};
    void work() {};
    void test(int idx) {};
private:
};

class objC
{
public:
    objC() {};
    int test2() { return 0; };
private:
};
```

* Step2: Regist function name;

```c++
REGISTFUNCTIONFORCHECK(test)
REGISTFUNCTIONFORCHECK(work)
REGISTFUNCTIONFORCHECK(test2)
```

* Step3: Check function isExist;

```c++
	std::cout << "========work=========" << std::endl;
    std::cout << CHECKCLASSFUNCTION(objA, work, void) << std::endl;
    std::cout << CHECKCLASSFUNCTION(objB, work, void) << std::endl;
    std::cout << CHECKCLASSFUNCTION(objC, work, void) << std::endl;
 
    std::cout << "=========test param========" << std::endl;
    std::cout << CHECKCLASSFUNCTION(objA, test, void, int) << std::endl;
    std::cout << CHECKCLASSFUNCTION(objB, test, void, int) << std::endl;
    std::cout << CHECKCLASSFUNCTION(objC, test, void, int) << std::endl;

    std::cout << "=========test no param========" << std::endl;
    std::cout << CHECKCLASSFUNCTION(objA, test, void ) << std::endl;
    std::cout << CHECKCLASSFUNCTION(objB, test, void ) << std::endl;
    std::cout << CHECKCLASSFUNCTION(objC, test, void ) << std::endl;

    std::cout << "=========test2========" << std::endl;
    std::cout << CHECKCLASSFUNCTION(objA, test2, int) << std::endl;
    std::cout << CHECKCLASSFUNCTION(objB, test2, int) << std::endl;
    std::cout << CHECKCLASSFUNCTION(objC, test2, int) << std::endl;
```

