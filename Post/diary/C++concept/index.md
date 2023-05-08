# itnext [C++20 Concepts — Complete Guide](https://itnext.io/c-20-concepts-complete-guide-42c9e009c6bf)

## A function that doesn't like an int.

```c++
#include <string>

void function_without_concept(const auto &x) {
    std::string v = x;
}

int main() {
    function_without_concept(1);
}
```



```
function_that_doesnt_like_int.cc:4:14: error: no viable conversion from 'const int' to 'std::string' (aka 'basic_string<char>')
        std::string v = x;
                    ^   ~
function_that_doesnt_like_int.cc:8:2: note: in instantiation of function template specialization 'function_without_concept<int>' requested here
        function_without_concept(1);
- shortened - 
```



## Using concepts

```c++
#include <string>
#include <concepts>

void func_with_auto_inline(const std::convertible_to<std::string> auto &x) {
    std::string v = x;
}

int main() {
    func_with_auto_inline(1);
}
```

```
function_with_concept.cc:9:5: error: no matching function for call to 'func_with_auto_inline'
    func_with_auto_inline(1);
    ^~~~~~~~~~~~~~~~~~~~~function_with_concept.cc:4:6: note: candidate template ignored: constraints not satisfied [with x:auto = int]
void func_with_auto_inline(const std::convertible_to<std::string> auto& x) {
     ^
function_with_concept.cc:4:39: note: because 'std::convertible_to<int, std::string>' evaluated to false
void func_with_auto_inline(const std::convertible_to<std::string> auto& x) {- shortened -
```



You might notice in the output that `std::convertible_to` actually takes two parameters. With **inline syntax**, the first parameter is automatically filled in from context. We can see that more clearly when considering all the other syntax variants:



```c++
void func_with_auto_inline(const std::convertible_to<std::string> auto& x) {
    std::string v = x;
}void func_with_auto_postfix(const auto& x)
    requires std::convertible_to<decltype(x), std::string> {
    std::string v = x;
}template <std::convertible_to<std::string> T>
void func_with_template_inline(const T& x) {
    std::string v = x;
}template <typename T>
    requires std::convertible_to<T, std::string>
void func_with_template_postfix(const T& x) {
    std::string v = x;
}
```



We can omit the first parameter when using the inline syntax (either with auto or a template). When using the postfix requires-based syntax, we need to supply it either through `decltype` or by passing in the template parameter.





Concepts can also be combined using logical operators. Here is a convoluted example of a function template that accepts integrals or invocable that returns an integral. Notice that we also use a concept inside of an `constexpr` conditional statement.

```c++
#include <string>
#include <concepts>
#include <iostream>template <typename T>
    requires std::integral<T> ||
    (std::invocable<T> &&
     std::integral<typename std::invoke_result<T>::type>)
void function(const T& x) {
    if constexpr (std::invocable<T>) {
        std::cout << "Result of call is " << x() << "\n";
    } else {
        std::cout << "Value is " << x << "\n";
    }
}int main() {
    function(1); // OK, integral
    function([]() { return 2; }); // OK, invocable, returns integral
    function(2.0); // Fails
}
```



